---
description: Il file Access Control.cfg gestisce l’accesso ad alcune funzioni di Insight Server.
title: Aggiornamento del file di controllo di accesso
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# Aggiornamento del file di controllo di accesso{#updating-the-access-control-file}

Il file Access Control.cfg gestisce l’accesso ad alcune funzioni di Insight Server.

Definisce le entità denominate AccessGroups. Un AccessGroup identifica un gruppo di utenti che dispongono dell&#39;autorizzazione per utilizzare determinate funzionalità del server.

Prima di connettersi a [!DNL Insight Server] con [!DNL Insight], è necessario aggiornare il gruppo di accesso amministratori per includere una delle licenze [!DNL Insight] rilasciate da Adobe all&#39;organizzazione. Questo AccessGroup identifica gli utenti autorizzati a eseguire funzioni amministrative tramite [!DNL Insight].

Nella procedura seguente viene descritto come aggiungere una licenza al gruppo di accesso amministratori. Per completare questa attività, è necessario determinare quale licenza [!DNL Insight] dispone di privilegi amministrativi per la propria organizzazione. (Per la configurazione e la configurazione iniziali, è sufficiente concedere privilegi amministrativi a una singola licenza. Puoi concedere privilegi amministrativi a licenze aggiuntive in un secondo momento.) È inoltre necessario conoscere il &quot;nome comune&quot; assegnato a questa licenza. Per ottenere questo valore, è possibile esaminare i certificati di licenza per il proprio account all&#39;indirizzo [https://aap.adobe.com](https://aap.adobe.com).

Lo scopo di questa procedura è semplicemente quello di identificare una copia con licenza di [!DNL Insight] che è possibile utilizzare per configurare e configurare inizialmente [!DNL Insight Server]. Una volta identificata questa licenza, puoi eseguire tutte le configurazioni server successive (inclusa la configurazione aggiuntiva di AccessGroup) utilizzando la copia in licenza di [!DNL Insight]. Per ulteriori informazioni sul controllo dell&#39;accesso al server tramite AccessGroups, vedere [Configurazione del controllo di accesso](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**Per aggiornare il file di controllo di accesso**

1. Passa alla cartella [!DNL Access Control] nella directory in cui hai installato [!DNL Insight Server].

   Esempio: [!DNL C:\Adobe\Server\Access Control]

1. Apri il file [!DNL Access Control.cfg] in un editor di testo come Blocco note.
1. Individua la voce CN nel gruppo di accesso Amministratori e sostituisci il valore esistente di questa voce con il nome comune che identifica il [!DNL Insight] che verrà utilizzato per configurare e amministrare inizialmente [!DNL Insight Server]. Il seguente frammento di file illustra la posizione in cui è stato inserito il nome comune nel file [!DNL Access Control.cfg].

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

   * O (ID organizzazione): Questa voce rappresenta l&#39;ID dell&#39;organizzazione. Ad esempio, `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Questo ID si trova nell&#39;Admin Console.
   * PLC - Questa voce consente l’accesso agli utenti per i quali è stato effettuato il provisioning per una particolare configurazione di prodotto. Può essere utilizzato nel formato `Organization_Id-PLC`. Ad esempio, `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Gli utenti per i quali è stato effettuato il provisioning per la Data Workbench utilizzando il PLC `DataworkbenchAdminUsers` avranno accesso ai loro server.
   * E-mail : questa voce consente l’accesso a qualsiasi singolo utente. Il suo valore deve essere l’indirizzo e-mail dell’utente predisposto. Ad esempio, `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Le voci distinguono tra maiuscole e minuscole. È necessario assicurarsi che i valori specificati per O, PLC e E-mail siano esattamente gli stessi mostrati nell’Admin Console.
   >    * Digita il nome comune esattamente come appare sul certificato.
   >    * Non utilizzare il tasto Tab per generare spazi bianchi nel file [!DNL Access Control.cfg] (o in qualsiasi altro file di configurazione per un componente di Adobe). Per creare spazi bianchi, utilizzare solo spazi. Un carattere di tabulazione impedisce al sistema di leggere correttamente il file.


1. Salva e chiudi il file.
