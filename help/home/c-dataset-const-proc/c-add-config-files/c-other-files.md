---
description: La directory Dataset include file aggiuntivi richiesti per il funzionamento del software o che forniscono funzionalità aggiuntive per l'implementazione Adobe.
solution: Analytics
title: Altri file
topic: Data workbench
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Altri file{#other-files}

La directory Dataset include file aggiuntivi richiesti per il funzionamento del software o che forniscono funzionalità aggiuntive per l&#39;implementazione Adobe.

* **[!DNL Client.cfg:]** Il [!DNL Client.cfg] file all&#39;interno della directory Dataset per il [!DNL Base] profilo è richiesto per il funzionamento del software. Non eliminare o modificare nessuno dei parametri nel [!DNL Client.cfg] file.

* **[!DNL Cluster.cfg:]** Il [!DNL Cluster.cfg] file all&#39;interno della directory Dataset per il [!DNL Base] profilo è richiesto per il funzionamento del software. Nel [!DNL Cluster.cfg] file, è necessario modificare solo il parametro Normalize Server se si sta configurando un dataset da elaborare in un cluster di server workbench dati. Per istruzioni su come modificare il parametro Normalize Server, vedere [Creazione di un server di normalizzazione centralizzato per un cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]e[!DNL Insight Transform Mode.cfg]:**Se si utilizza la funzionalità di trasformazione, nella directory Dataset per il[!DNL Transform.cfg]profilo sono presenti due file di configurazione aggiuntivi, workbench dati[!DNL TransformMode.cfg]e workbench dati[!DNL Transform]. Per informazioni su questi file e sui relativi parametri, vedere[Funzionalità](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html)di trasformazione.

* Il file **PAServer.cfg** . Se si desidera inviare i processi di clustering Predictive Analytics ai server Insight, sarà necessario configurare il [!DNL PAServer.cfg] file per la gestione degli invii del clustering lato server.
Il profilo personalizzato deve ereditare il profilo [!DNL PAServer.cfg] dal profilo Predictive Analytics ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Impostate un server ** principale in questo file e salvate il file [!DNL PAServer.cfg] nel sito di implementazione.   >
   >
   >
   ```>
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```  >
   >



