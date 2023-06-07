---
description: Il file Access Control.cfg gestisce l’accesso a determinate funzioni di Insight Server.
title: Aggiornamento del file di controllo di accesso
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: 5ce5b8f8b35d2d4f319076f54347e300e5f133df
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 3%

---

# Aggiornamento del file di controllo di accesso{#updating-the-access-control-file}

{{eol}}

Il file Access Control.cfg gestisce l’accesso a determinate funzioni di Insight Server.

Definisce entità denominate AccessGroups. Un AccessGroup identifica un gruppo di utenti che dispongono dell&#39;autorizzazione per utilizzare determinate funzionalità del server.

Prima di connettersi a [!DNL Insight Server] con [!DNL Insight], è necessario aggiornare il gruppo di accesso Amministratori per includere uno dei [!DNL Insight] le licenze rilasciate dall&#39;Adobe alla tua organizzazione. Questo AccessGroup identifica gli utenti autorizzati a eseguire funzioni amministrative tramite [!DNL Insight].

Nella procedura seguente viene descritto come aggiungere una licenza al gruppo di accesso Amministratori. Per completare questa attività, è necessario determinare quale [!DNL Insight] la licenza dispone dei privilegi di amministratore per la tua organizzazione. (Per la configurazione iniziale è sufficiente concedere privilegi amministrativi a una singola licenza. In seguito è possibile concedere privilegi amministrativi a licenze aggiuntive.) È inoltre necessario conoscere il &quot;nome comune&quot; assegnato a questa licenza.

Lo scopo di questa procedura è semplicemente identificare una copia autorizzata di [!DNL Insight] che puoi utilizzare per impostare e configurare inizialmente [!DNL Insight Server]. Una volta identificata questa licenza, è possibile eseguire tutte le successive configurazioni del server (inclusa la configurazione di AccessGroup aggiuntiva) utilizzando la copia con licenza di [!DNL Insight]. Per ulteriori informazioni sul controllo dell&#39;accesso al server tramite AccessGroups, vedere [Configurazione del controllo di accesso](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**Per aggiornare il file di controllo di accesso**

1. Accedi a [!DNL Access Control] cartella nella directory in cui è stato installato [!DNL Insight Server].

   Esempio: [!DNL C:\Adobe\Server\Access Control]

1. Apri [!DNL Access Control.cfg] in un editor di testo, ad esempio Blocco note.
1. Individuare la voce CN nel gruppo di accesso Amministratori e sostituire il valore esistente di questa voce con il nome comune che identifica [!DNL Insight] che utilizzerai per impostare e amministrare inizialmente [!DNL Insight Server]. Il seguente frammento di file illustra la posizione in cui viene inserito il nome comune nel [!DNL Access Control.cfg] file.

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

   * O (ID organizzazione): questa voce rappresenta l&#39;ID dell&#39;organizzazione. Esempio: `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Questo ID si trova nell’Admin Console.
   * PLC: questa voce consente di accedere agli utenti per i quali è stato eseguito il provisioning per una particolare configurazione di prodotto. Può essere utilizzato in formato `Organization_Id-PLC`. Esempio: `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Utenti per i quali è stato eseguito il provisioning per la Data Workbench utilizzando il PLC `DataworkbenchAdminUsers` otterranno l’accesso sui loro server.
   * E-mail: questa voce consente l’accesso a qualsiasi singolo utente. Il valore deve essere l’indirizzo e-mail dell’utente con provisioning. Esempio: `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Le voci fanno distinzione tra maiuscole e minuscole. Assicurati che i valori specificati per O, PLC e E-mail siano esattamente gli stessi di quelli mostrati nell’Admin Console.
   >    * Digita il nome comune esattamente come appare sul certificato.
   >    * Non utilizzare il tasto TAB per generare spazi vuoti nel [!DNL Access Control.cfg] (o in qualsiasi altro file di configurazione per un componente di Adobe). Utilizzare solo spazi per creare spazi. Un carattere di tabulazione impedisce al sistema di leggere correttamente il file.


1. Salva e chiudi il file.
