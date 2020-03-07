---
description: Nuove funzioni, problemi risolti e problemi noti in Workbench dati 6.7.
title: Note sulla versione di Workbench dati 6.7
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.7 Release Notes{#data-workbench-release-notes}

Nuove funzioni, problemi risolti e problemi noti in Workbench dati 6.7.

## Data Workbench 6.7 Release Notes {#topic-7655534554ac4a4b816af1bd73b06aad}

Nuove funzioni, problemi risolti e problemi noti in Workbench dati 6.7.

## Nuove funzioni nella release 6.7 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Nuovo modello di autenticazione per Workbench dati Workstation (integrazione IMS)**

Workbench dati Workstation ora supporta l’autenticazione degli utenti tramite nome utente e password. Con questo nuovo metodo, gli amministratori possono creare e gestire direttamente gli account utente, senza dover contattare l’Assistenza clienti.

Per ulteriori informazioni, vedi [Self-Provisioning of Users](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html) (Provisioning autonomo degli utenti).

**Ricerca di file Flat**

Workbench dati Workstation ora supporta l’autenticazione degli utenti tramite nome utente e password. Con questo nuovo metodo, gli amministratori possono creare e gestire direttamente gli account utente, senza dover contattare l’Assistenza clienti.

La funzione di ricerca dei file Flat prima caricava l’intero file nei buffer della memoria, con conseguente utilizzo eccessivo della stessa e problemi di prestazioni per altri sottosistemi. Ora i file possono essere mappati nella memoria e memorizzati nella cache di Windows ottimizzando l’utilizzo della memoria, con l’impostazione di *Memory Mapped Lookup Files* (File di ricerca mappati in memoria) su true in [!DNL MemorySettings.cfg].

Per ulteriori informazioni, vedi [Self-Provisioning of Users](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html) (Provisioning autonomo degli utenti).

**Utilizzo della memoria**

Large Page usage can now be disabled by setting *Use Large Pages* to false in [!DNL MemorySettings.cfg]. Per ulteriori informazioni, consulta [Monitoring Memory Usage](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html) (Monitoraggio dell’utilizzo della memoria).

**Cifratori di sicurezza**

È stato aggiunto il supporto per ECDHE e DHE.

Email support in [!DNL User List.cfg]

Added support for Email attribute in [!DNL User List.cfg]. Per ulteriori informazioni, consulta [User Administration of Group Members](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html) (Amministrazione utenti per membri di gruppi).

**Menu Aiuto**

Il menu Aiuto ora permette di accedere alla directory Open Certificates.

**`TargetBulkUpload`export **

Alla fine del file di traccia dell’esportazione e del file `targetbulkuploadexportname.log.completed` verranno forniti gli URL necessari per tenere traccia di eventuali batch con problemi.

È stato fornito il nuovo file [!DNL TargetBulkUpload.cfg] per configurare l’intervallo di timeout massimo (in minuti). Il file si trova in [!DNL Server\Admin\Export\].

## Problemi risolti {#section-160baf6ea04c45a993777ee4260691ed}

* È stato risolto un problema che causava la visualizzazione di valori gonfiati nella dimensione ClickThrough della campagna.
* È stato risolto un problema relativo alla generazione di file Excel dal server di report.
* La crittografia RC4 è ora disabilitata per impostazione predefinita.
* È stato risolto un problema che causava l&#39;arresto anomalo della workstation Workbench dati durante l&#39;aggiunta di un elemento dimensione alla tabella di legenda di un valore.
* È stato risolto un problema con Workbench dati alle esportazioni AAM che causava timeout.
* È stato risolto un problema che causava l&#39;arresto anomalo della workstation Workbench dati quando un utente senza un livello di accesso sufficiente salvava l&#39;area di lavoro sul server.
* È stato corretto un problema a causa del quale il formato della data [!DNL report.cfg] risultava errato o non localizzato.
* È stato risolto un problema con le righe di dispositivi mobili e prodotti nel feed AVRO che causava la visualizzazione di informazioni confuse.
* È stato risolto un problema che impediva l&#39;ordine di `*.1cd` e `*.1ad` i file in [!DNL order.txt].

* L&#39;opzione Invia al server è stata disabilitata per l&#39;algoritmo di ottimizzazione delle aspettative durante l&#39;esecuzione del clustering.
* È stato risolto un problema con l&#39; `TargetBulkUpload` eseguibile che si bloccava e che non riusciva a eseguire completamente.

## Problemi noti {#section-d76322bdac5043f087ab303dc68b8fff}

* Al momento della disconnessione, il [!DNL user cache.db] file viene pulito.
* Gli indirizzi e-mail utente IMS contenenti caratteri &#39;+&#39; o &#39;%&#39; non sono supportati.
* L&#39;utente non è in grado di disconnettersi durante un errore nello stato della connessione. Come soluzione alternativa, disconnettetevi in modalità offline.
* La finestra di accesso IMS non viene visualizzata correttamente su alcuni hardware con alta risoluzione e alta risoluzione DPI. Per risolvere il problema, fare clic con il pulsante destro del mouse [!DNL Insight.exe] e passare a **[!UICONTROL Properties]** > **[!UICONTROL Compatability]**, quindi selezionare la casella **[!UICONTROL Override high DPI scaling behavior]**.

## Requisiti per l&#39;aggiornamento {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. Aggiornate [!DNL trust_ca_cert.pem] i server Insight che fanno parte del pacchetto di build.
1. Aggiornate il certificato del server e del server di report scaricando nuovi certificati da [https://aap.adobe.com](https://aap.adobe.com).
1. Per aggiornare automaticamente Workstation e Report Server, eseguire l&#39;aggiornamento manuale [!DNL trust_ca_cert.pem] per entrambi scaricandoli dal server licenze.
1. La funzione di aggiornamento automatico del sensore richiede la versione 5.0 per comunicare con Insight Server versione 6.70. Inoltre, i sensori [!DNL trust_ca_cert.pem] devono essere aggiornati manualmente scaricandoli dal server licenze.

## Aggiornamenti del sistema {#section-c1b4949ea734440aa62658ac313261db}

I nuovi file includono:

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

I file aggiornati includono:

1. [!DNL trust_ca_cert.pem] per tutti i componenti.
1. [!DNL Access Control.cfg] per supportare la configurazione IMS.
1. [!DNL Base\Context\meta.cfg] per supportare i formati Data inizio e Data fine in [!DNL Report.cfg]

1. Aggiunta [!DNL Insight.cfg] al supporto del proxy per l&#39;autenticazione IMS:

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

Vedere [le note](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) di rilascio archiviate per Workbench dati da 5.3 a 5.52.
