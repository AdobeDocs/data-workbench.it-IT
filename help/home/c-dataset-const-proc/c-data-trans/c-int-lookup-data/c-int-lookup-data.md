---
description: Data Workbench fornisce un set di trasformazioni che consentono al server workbench dati di incorporare dati di ricerca nel dataset.
solution: Analytics
title: Integrazione dei dati di ricerca
topic: Data workbench
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Integrazione dei dati di ricerca{#integrating-lookup-data}

Data Workbench fornisce un set di trasformazioni che consentono al server workbench dati di incorporare dati di ricerca nel dataset.

I dati di ricerca sono dati esterni provenienti da database aziendali o file di ricerca che è possibile combinare con i dati dell&#39;evento per creare il dataset. In generale, i dati di ricerca vengono utilizzati per aumentare i dati dell&#39;evento dalle origini del registro. Concettualmente, è possibile utilizzare i dati di ricerca per compilare i record di dati evento con colonne di informazioni aggiuntive.

Quando si utilizzano i dati di ricerca, si caricano i dati in una tabella di ricerca residente nella memoria. Una colonna della tabella deve contenere una chiave comune che esiste anche nei record di dati dell&#39;evento. I dati nella tabella di ricerca stessa possono essere caricati da un file semplice o da un&#39;origine dati ODBC. I dati di ricerca possono essere incorporati nel dataset durante la fase di elaborazione del log o di trasformazione del processo di costruzione del dataset.

Per includere i dati di ricerca, è innanzitutto necessario generare un file di ricerca o disporre delle informazioni necessarie per accedere a un database SQL, quindi definire una o più delle seguenti trasformazioni nei file di configurazione del dataset per l&#39;elaborazione e la trasformazione del registro.

**Per integrare i dati di ricerca nel dataset**

1. Generare il file di ricerca. Vedere [Compilazione della tabella](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8)di ricerca.
1. Definite uno dei seguenti tipi di trasformazioni nel parametro Trasformazioni nel file di configurazione del dataset appropriato:

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>La [!DNL ODBCLookup] trasformazione funziona solo se definita nel [!DNL Transformation.cfg] file o in un [!DNL Transformation Dataset Include] file.

