---
description: Il file Access Control.cfg gestisce l’accesso ad alcune funzioni di Insight Server.
title: Aggiornamento del file di controllo di accesso
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# Aggiornamento del file di controllo di accesso{#updating-the-access-control-file}

{{eol}}

Il file Access Control.cfg gestisce l’accesso ad alcune funzioni di Insight Server.

Definisce le entità denominate AccessGroups. Un AccessGroup identifica un gruppo di utenti che dispongono dell&#39;autorizzazione per utilizzare determinate funzionalità del server.

Prima di poterti connettere a [!DNL Insight Server] con [!DNL Insight], è necessario aggiornare Administrators AccessGroup per includere uno dei [!DNL Insight] le licenze che Adobe ha rilasciato alla tua organizzazione. Questo AccessGroup identifica gli utenti autorizzati a eseguire funzioni amministrative attraverso [!DNL Insight].

Nella procedura seguente viene descritto come aggiungere una licenza al gruppo di accesso amministratori. Per completare questa attività, è necessario determinare quale [!DNL Insight] la licenza dispone di privilegi amministrativi per la tua organizzazione. (Per la configurazione e la configurazione iniziali, è sufficiente concedere privilegi amministrativi a una singola licenza. Puoi concedere privilegi amministrativi a licenze aggiuntive in un secondo momento.) È inoltre necessario conoscere il &quot;nome comune&quot; assegnato a questa licenza. Per ottenere questo valore, puoi esaminare i certificati di licenza per il tuo account all&#39;indirizzo [https://aap.adobe.com](https://aap.adobe.com).

Lo scopo di questa procedura è semplicemente quello di identificare una copia autorizzata di [!DNL Insight] che puoi utilizzare per configurare e configurare inizialmente [!DNL Insight Server]. Una volta identificata questa licenza, puoi eseguire tutte le configurazioni server successive (inclusa la configurazione aggiuntiva di AccessGroup) utilizzando la copia in licenza di [!DNL Insight]. Per ulteriori informazioni sul controllo dell&#39;accesso al server tramite AccessGroups, vedere [Configurazione del controllo di accesso](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**Per aggiornare il file di controllo di accesso**

1. Passa a [!DNL Access Control] nella directory in cui è stata installata [!DNL Insight Server].

   Esempio: [!DNL C:\Adobe\Server\Access Control]

1. Apri [!DNL Access Control.cfg] in un editor di testo come Blocco note.
1. Individuare la voce CN nel gruppo di accesso Amministratori e sostituire il valore esistente di questa voce con il nome comune che identifica il [!DNL Insight] che utilizzerai per configurare e amministrare inizialmente [!DNL Insight Server]. Il frammento di file seguente illustra la posizione in cui viene inserito il nome comune [!DNL Access Control.cfg] file.

   ```
   Access Control Groups = vector: 5 items 
     0 = AccessGroup: 
       Members = vector: 2 items 
         0 = string: IP:127.0.0.1 
         1 = string: CN: CommonName 
       Name = string: Administrators 
       Read-Only Access = vector: 0 items 
       Read-Write Access = vector: 1 items 
         0 = string: / 
     1 = AccessGroup: 
     . . . 
   ```

   Se utilizzi l’autenticazione basata sulle credenziali, saranno disponibili alcune voci aggiuntive per la configurazione. Queste voci sono:

   * O (ID organizzazione): Questa voce rappresenta l&#39;ID dell&#39;organizzazione. Esempio: `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Questo ID si trova nell&#39;Admin Console.
   * PLC - Questa voce consente l’accesso agli utenti per i quali è stato effettuato il provisioning per una particolare configurazione di prodotto. Può essere utilizzato in formato `Organization_Id-PLC`. Esempio: `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Utenti per cui è stato effettuato il provisioning per la Data Workbench utilizzando il PLC `DataworkbenchAdminUsers` otterrà l&#39;accesso sui loro server.
   * E-mail : questa voce consente l’accesso a qualsiasi singolo utente. Il suo valore deve essere l’indirizzo e-mail dell’utente predisposto. Esempio: `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Le voci distinguono tra maiuscole e minuscole. È necessario assicurarsi che i valori specificati per O, PLC e E-mail siano esattamente gli stessi mostrati nell’Admin Console.
   >    * Digita il nome comune esattamente come appare sul certificato.
   >    * Non utilizzare il tasto Tab per generare spazi bianchi nel [!DNL Access Control.cfg] (o in qualsiasi altro file di configurazione per un componente di Adobe). Per creare spazi bianchi, utilizzare solo spazi. Un carattere di tabulazione impedisce al sistema di leggere correttamente il file.


1. Salva e chiudi il file.
