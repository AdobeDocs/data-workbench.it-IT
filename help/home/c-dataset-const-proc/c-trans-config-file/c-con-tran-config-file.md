---
description: Informazioni importanti da tenere in considerazione durante la modifica del file Transformation.cfg.
solution: Analytics
title: Considerazioni per il file di configurazione delle trasformazioni
topic: Data workbench
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Considerazioni per il file di configurazione delle trasformazioni{#considerations-for-the-transformation-configuration-file}

Informazioni importanti da tenere in considerazione durante la modifica del file Transformation.cfg.

* La modifica di uno qualsiasi dei parametri in questo file richiede la riconversione dei dati.
* Se si rielaborano i dati, è possibile controllare il [!DNL Transformation Progress] parametro nel workbench dati [!DNL Processing Legend].

   Per informazioni sulla rielaborazione dei dati o per [!DNL Processing Legend,] vedere [Rielaborazione e](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)Trasformazione.

* [!DNL CrossRows], [!DNL ODBCLookup][!DNL Sessionize]e [!DNL AppendURI] le trasformazioni funzionano solo se definite in un [!DNL Transformation Dataset Configuration] file. Per informazioni su queste trasformazioni, consultate Trasformazioni [dati](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe consiglia di definire le trasformazioni per la fase di trasformazione della creazione di set di dati in uno o più [!DNL Transformation Dataset Include] file. Per informazioni, consultate [DataSet di trasformazioni Includi file](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* Potete aggiungere al [!DNL Transformation.cfg] file uno qualsiasi dei parametri precedentemente descritti aprendo e modificando il file in Blocco note. Eventuali modifiche apportate e salvate vengono visualizzate quando si riapre il file nel workbench dati. Quando si aggiunge un nuovo parametro, utilizzate il tasto Space (non il tasto Tab) per applicare un rientro di due (2) spazi a destra del livello di intestazione precedente.

   Eventuali errori che si verificano durante la fase di trasformazione del processo di costruzione del set di dati per un profilo di set di dati sono mostrati nel [!DNL Profiles] nodo dell&#39;interfaccia nel workbench dati [!DNL Detailed Status] . Per informazioni sull&#39; [!DNL Detailed Status] interfaccia, vedere la Guida *utente di Workbench* dati.

