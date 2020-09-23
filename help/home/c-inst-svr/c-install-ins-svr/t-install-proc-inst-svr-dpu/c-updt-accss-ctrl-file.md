---
description: Il file Access Control.cfg gestisce l'accesso ad alcune funzionalità di Insight Server.
solution: Analytics
title: Aggiornamento del file di controllo di accesso
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---


# Aggiornamento del file di controllo di accesso{#updating-the-access-control-file}

Il file Access Control.cfg gestisce l&#39;accesso ad alcune funzionalità di Insight Server.

Definisce le entità denominate AccessGroups. Un AccessGroup identifica un gruppo di utenti che dispongono dell&#39;autorizzazione per utilizzare determinate funzionalità del server.

Prima di collegarsi [!DNL Insight Server] con [!DNL Insight], è necessario aggiornare il gruppo di accesso amministratori in modo da includere una delle [!DNL Insight] licenze rilasciate  Adobe all&#39;organizzazione. Questo AccessGroup identifica gli utenti ai quali è consentito eseguire funzioni amministrative tramite [!DNL Insight].

Nella procedura seguente viene descritto come aggiungere una licenza al gruppo di Access Administrators. Per completare questa attività, è necessario determinare quale [!DNL Insight] licenza dispone dei privilegi amministrativi per l&#39;organizzazione. (Per la configurazione e la configurazione iniziali, è sufficiente concedere privilegi amministrativi a una singola licenza. Potete concedere privilegi amministrativi a licenze aggiuntive in un secondo momento. È inoltre necessario conoscere il &quot;nome comune&quot; assegnato a questa licenza. Per ottenere questo valore, potete esaminare i certificati di licenza per il vostro account all&#39;indirizzo [https://aap.adobe.com](https://aap.adobe.com).

Lo scopo di questa procedura è semplicemente identificare una copia con licenza di [!DNL Insight] cui è possibile utilizzare per configurare e configurare inizialmente [!DNL Insight Server]. Una volta identificata questa licenza, potete eseguire tutte le configurazioni server successive (inclusa la configurazione aggiuntiva di AccessGroup) utilizzando la copia con licenza di [!DNL Insight]. Per ulteriori informazioni sul controllo dell&#39;accesso al server tramite AccessGroups, vedere [Configurazione del controllo](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)di accesso.

**Per aggiornare il file di controllo di accesso**

1. Andate alla [!DNL Access Control] cartella nella directory in cui avete installato [!DNL Insight Server].

   Esempio: [!DNL C:\Adobe\Server\Access Control]

1. Aprite il [!DNL Access Control.cfg] file in un editor di testo come Blocco note.
1. Individuate la voce CN in Administrators AccessGroup e sostituite il valore esistente di questa voce con il nome comune che identifica l&#39; [!DNL Insight] impostazione iniziale e l&#39;amministrazione da utilizzare [!DNL Insight Server]. Il frammento di file seguente illustra la posizione in cui è possibile inserire il nome comune nel [!DNL Access Control.cfg] file.

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

   Se utilizzate l&#39;autenticazione basata sulle credenziali, saranno disponibili alcune voci aggiuntive per la configurazione. Le voci seguenti sono:

   * O (ID organizzazione): Questa voce rappresenta l&#39;ID dell&#39;organizzazione. Ad esempio, `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Questo ID si trova nel Admin Console .
   * PLC - Questa voce consente di accedere agli utenti per una particolare configurazione di prodotto. Può essere utilizzato in formato `Organization_Id-PLC`. Ad esempio, `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Gli utenti predisposti per l’Data Workbench tramite PLC `DataworkbenchAdminUsers` avranno accesso ai propri server.
   * E-mail - Questa voce consente l&#39;accesso a qualsiasi singolo utente. Il valore deve essere l&#39;indirizzo e-mail dell&#39;utente con provisioning. Ad esempio, `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Le voci sono con distinzione tra maiuscole e minuscole. È necessario assicurarsi che i valori specificati per O, PLC e E-mail siano esattamente identici a quelli mostrati nel Admin Console .
   >    * Digitate il nome comune esattamente come appare sul certificato.
   >    * Non utilizzate il tasto Tab per generare spazi bianchi nel [!DNL Access Control.cfg] file (o in qualsiasi altro file di configurazione per un componente Adobe ). Utilizzate solo gli spazi per creare spazi bianchi. Un carattere di tabulazione impedisce al sistema di leggere correttamente il file.


1. Salvate e chiudete il file.

