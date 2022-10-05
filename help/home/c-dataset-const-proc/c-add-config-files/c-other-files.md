---
description: La directory Dataset include file aggiuntivi necessari per il funzionamento del software o fornisce funzionalità aggiuntive per l'implementazione del tuo Adobe.
title: Altri file
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---

# Altri file{#other-files}

{{eol}}

La directory Dataset include file aggiuntivi necessari per il funzionamento del software o fornisce funzionalità aggiuntive per l&#39;implementazione del tuo Adobe.

* **[!DNL Client.cfg:]** La [!DNL Client.cfg] nella directory Dataset per [!DNL Base] per il funzionamento del software è necessario un profilo. Non eliminare o modificare nessuno dei parametri nel [!DNL Client.cfg] file.

* **[!DNL Cluster.cfg:]** La [!DNL Cluster.cfg] nella directory Dataset per [!DNL Base] per il funzionamento del software è necessario un profilo. In [!DNL Cluster.cfg] file, è necessario modificare solo il parametro Normalize Server se si sta configurando un set di dati da elaborare in un cluster di server di Data Workbench. Per istruzioni su come modificare il parametro Normalize Server, vedi [Creazione di un server di normalizzazione centralizzato per un cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]e [!DNL Insight Transform Mode.cfg]:** Se utilizzi la funzionalità di trasformazione, disponi di due file di configurazione aggiuntivi, Data Workbench [!DNL Transform.cfg] e Data Workbench [!DNL TransformMode.cfg], nella directory Dataset per [!DNL Transform] profilo. Per informazioni su questi file e sui relativi parametri, vedi [Funzionalità di trasformazione](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* La **PAServer.cfg** file. Se desideri inviare i processi di clustering Predictive Analytics a Insight Server, dovrai configurare la [!DNL PAServer.cfg] file per la gestione degli invii di clustering lato server.
Il profilo personalizzato deve ereditare il [!DNL PAServer.cfg] dal profilo Predictive Analytics ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Imposta un *Server principale* in questo file e salva il [!DNL PAServer.cfg] al sito di implementazione.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
