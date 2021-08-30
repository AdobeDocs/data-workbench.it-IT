---
description: Nuove funzioni, correzioni e problemi noti in Data Workbench 6.7.
title: Note sulla versione di Data Workbench 6.7
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
exl-id: e5ec3224-66d1-47a6-9bf3-8be9f6568b8d
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 34%

---

# Note sulla versione di Data Workbench 6.7{#data-workbench-release-notes}

Nuove funzioni, correzioni e problemi noti in Data Workbench 6.7.

## Note sulla versione di Data Workbench 6.7 {#topic-7655534554ac4a4b816af1bd73b06aad}

Nuove funzioni, correzioni e problemi noti in Data Workbench 6.7.

## Nuove funzioni nella versione 6.7 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Nuovo modello di autenticazione per Data Workbench Workstation (integrazione IMS)**

Data Workbench Workstation ora supporta l’autenticazione degli utenti tramite nome utente e password. Con questo nuovo metodo, gli amministratori possono creare e gestire direttamente gli account utente, senza dover contattare l’Assistenza clienti.

Per ulteriori informazioni, vedi [Self-Provisioning of Users](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html) (Provisioning autonomo degli utenti).

**Ricerca di file Flat**

Data Workbench Workstation ora supporta l’autenticazione degli utenti tramite nome utente e password. Con questo nuovo metodo, gli amministratori possono creare e gestire direttamente gli account utente, senza dover contattare l’Assistenza clienti.

La funzione di ricerca dei file Flat prima caricava l’intero file nei buffer della memoria, con conseguente utilizzo eccessivo della stessa e problemi di prestazioni per altri sottosistemi. Ora i file possono essere mappati nella memoria e memorizzati nella cache di Windows ottimizzando l’utilizzo della memoria, con l’impostazione di *Memory Mapped Lookup Files* (File di ricerca mappati in memoria) su true in [!DNL MemorySettings.cfg].

Per ulteriori informazioni, vedi [Self-Provisioning of Users](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html) (Provisioning autonomo degli utenti).

**Utilizzo della memoria**

È ora possibile disattivare l’utilizzo di pagine grandi impostando *Use Large Pages* su false in [!DNL MemorySettings.cfg]. Per ulteriori informazioni, consulta [Monitoring Memory Usage](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html) (Monitoraggio dell’utilizzo della memoria).

**Cifratori di sicurezza**

È stato aggiunto il supporto per ECDHE e DHE.

Supporto di e-mail in [!DNL User List.cfg]

È stato aggiunto il supporto per l’attributo Email in [!DNL User List.cfg]. Per ulteriori informazioni, consulta [User Administration of Group Members](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html?lang=en) (Amministrazione utenti per membri di gruppi).

**Menu Aiuto**

Il menu Aiuto ora permette di accedere alla directory Open Certificates.

**`TargetBulkUpload`esportare**

Alla fine del file di traccia dell’esportazione e del file `targetbulkuploadexportname.log.completed` verranno forniti gli URL necessari per tenere traccia di eventuali batch con problemi.

È stato fornito il nuovo file [!DNL TargetBulkUpload.cfg] per configurare l’intervallo di timeout massimo (in minuti). Il file si trova in [!DNL Server\Admin\Export\].

## Correzioni {#section-160baf6ea04c45a993777ee4260691ed}

* È stato risolto un problema che causava la visualizzazione di valori gonfiati nella dimensione Clickthrough di Campaign.
* È stato risolto un problema relativo alla generazione di file excel dal server di report.
* La crittografia RC4 è ora disabilitata per impostazione predefinita.
* È stato risolto un problema che causava l’arresto anomalo della workstation Data Workbench quando si aggiungeva un elemento dimensione a una tabella di legenda del valore.
* È stato risolto un problema relativo alla Data Workbench AAM esportazioni che causava timeout.
* È stato risolto un problema che causava l’arresto anomalo della workstation Data Workbench quando un utente senza un livello di accesso sufficiente salvava l’area di lavoro sul server.
* È stato risolto un problema a causa del quale il formato della data in [!DNL report.cfg] non era corretto o non era localizzato.
* È stato risolto un problema relativo alle righe mobili e di prodotto nel feed AVRO che causava la visualizzazione di informazioni confuse.
* È stato risolto un problema che impediva l&#39;ordine dei file `*.1cd` e `*.1ad` in [!DNL order.txt].

* L&#39;opzione Invia al server è stata disabilitata per l&#39;algoritmo di ottimizzazione delle aspettative durante l&#39;esecuzione del clustering.
* È stato risolto un problema che causava lo stallo dell&#39;eseguibile `TargetBulkUpload` e la sua esecuzione non era completa.

## Problemi noti {#section-d76322bdac5043f087ab303dc68b8fff}

* Al momento della disconnessione, il file [!DNL user cache.db] viene pulito.
* Gli indirizzi e-mail degli utenti IMS contenenti caratteri &#39;+&#39; o &#39;%&#39; non sono supportati.
* L&#39;utente non è in grado di disconnettersi durante un errore nello stato della connessione. Come soluzione alternativa, disconnettiti in modalità offline.
* La finestra di accesso IMS non viene riprodotta correttamente su alcuni hardware ad alta risoluzione e con valore DPI elevato. Come soluzione alternativa, fai clic con il pulsante destro del mouse su [!DNL Insight.exe] e passa a **[!UICONTROL Properties]** > **[!UICONTROL Compatability]**, quindi seleziona la casella **[!UICONTROL Override high DPI scaling behavior]**.

## Requisiti di aggiornamento {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. Aggiorna [!DNL trust_ca_cert.pem] su Insight Server che fa parte del pacchetto di compilazione.
1. Aggiorna il certificato del server e del server di rapporto scaricando nuovi certificati da [https://aap.adobe.com](https://aap.adobe.com).
1. Per aggiornare automaticamente Workstation e Report Server, aggiorna manualmente [!DNL trust_ca_cert.pem] per entrambi scaricandoli dal License Server.
1. La funzione di aggiornamento automatico del sensore richiede la versione 5.0 per comunicare con Insight Server versione 6.70. Inoltre, la versione [!DNL trust_ca_cert.pem] del sensore deve essere aggiornata manualmente scaricandola dal server licenze.

## Aggiornamenti del sistema {#section-c1b4949ea734440aa62658ac313261db}

I nuovi file includono:

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

I file aggiornati includono:

1. [!DNL trust_ca_cert.pem] per tutti i componenti.
1. [!DNL Access Control.cfg] per supportare la configurazione IMS.
1. [!DNL Base\Context\meta.cfg] per supportare i formati Data inizio e Data fine in  [!DNL Report.cfg]

1. Aggiunte a [!DNL Insight.cfg] per supportare il proxy per l’autenticazione IMS:

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

Consulta le [note sulla versione archiviate](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) per Data Workbench da 5.3 a 5.52.
