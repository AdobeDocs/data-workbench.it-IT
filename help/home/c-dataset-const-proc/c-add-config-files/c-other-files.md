---
description: La directory Dataset include file aggiuntivi necessari per il funzionamento del software o fornisce funzionalità aggiuntive per l'implementazione del tuo Adobe.
title: Altri file
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---

# Altri file{#other-files}

La directory Dataset include file aggiuntivi necessari per il funzionamento del software o fornisce funzionalità aggiuntive per l&#39;implementazione del tuo Adobe.

* **[!DNL Client.cfg:]** Il  [!DNL Client.cfg] file all&#39;interno della directory Dataset per il  [!DNL Base] profilo è necessario per il funzionamento del software. Non eliminare o modificare nessuno dei parametri nel file [!DNL Client.cfg].

* **[!DNL Cluster.cfg:]** Il  [!DNL Cluster.cfg] file all&#39;interno della directory Dataset per il  [!DNL Base] profilo è necessario per il funzionamento del software. Nel file [!DNL Cluster.cfg], devi modificare solo il parametro Normalize Server se configuri un set di dati da elaborare in un cluster di server di Data Workbench. Per istruzioni su come modificare il parametro Normalize Server, vedere [Creazione di un server di normalizzazione centralizzato per un cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]e  [!DNL Insight Transform Mode.cfg]:** se utilizzi la funzionalità di trasformazione, nella directory Dataset per il  [!DNL Transform.cfg] profilo sono presenti due file di configurazione aggiuntivi, Data Workbench  [!DNL TransformMode.cfg]e Data Workbench  [!DNL Transform] . Per informazioni su questi file e sui relativi parametri, vedere [Funzionalità di trasformazione](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* Il file **PAServer.cfg**. Se desideri inviare i lavori di clustering Predictive Analytics a Insight Server, dovrai configurare il file [!DNL PAServer.cfg] per la gestione degli invii di clustering lato server.
Il profilo personalizzato deve ereditare il valore [!DNL PAServer.cfg] dal profilo Predictive Analytics ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Imposta un *server principale* in questo file e salva il [!DNL PAServer.cfg] nel sito di implementazione.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
