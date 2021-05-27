---
description: Informazioni importanti da considerare durante la modifica del file Transformation.cfg.
title: Considerazioni per il file di configurazione delle trasformazioni
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 5%

---

# Considerazioni per il file di configurazione delle trasformazioni{#considerations-for-the-transformation-configuration-file}

Informazioni importanti da considerare durante la modifica del file Transformation.cfg.

* La modifica di uno qualsiasi dei parametri in questo file richiede la riconversione dei dati.
* Se rielabora i dati, puoi controllare il parametro [!DNL Transformation Progress] nel [!DNL Processing Legend] di Data Workbench.

   Per informazioni sulla rielaborazione dei dati o sulla [!DNL Processing Legend,] vedere [Rielaborazione e ritrasformazione](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows],  [!DNL ODBCLookup],  [!DNL Sessionize] e  [!DNL AppendURI] le trasformazioni funzionano solo quando sono definite in un  [!DNL Transformation Dataset Configuration] file . Per informazioni su queste trasformazioni, consulta [Trasformazioni dati](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >L’Adobe consiglia di definire le trasformazioni per la fase di trasformazione della costruzione del set di dati in uno o più file [!DNL Transformation Dataset Include]. Per informazioni, consulta [Dataset Include Files (File inclusi nel set di dati di trasformazione)](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* È possibile aggiungere uno qualsiasi dei parametri descritti sopra al file [!DNL Transformation.cfg] aprendo e modificando il file in Blocco note. Le modifiche apportate e salvate vengono visualizzate quando riapri il file in Data Workbench. Quando si aggiunge un nuovo parametro, utilizzare il tasto Space (non il tasto Tab) per far rientrare due (2) spazi a destra del livello di intestazione precedente.

   Eventuali errori che si verificano durante la fase di trasformazione del processo di costruzione del set di dati per un profilo di set di dati vengono visualizzati nel nodo [!DNL Profiles] dell’interfaccia [!DNL Detailed Status] in Data Workbench. Per informazioni sull&#39;interfaccia [!DNL Detailed Status], vedere la *Guida utente Data Workbench*.
