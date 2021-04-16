---
description: Data Workbench fornisce un set di trasformazioni che consente al server di Data Workbench di incorporare i dati di ricerca nel set di dati.
title: Integrazione dei dati di ricerca
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
exl-id: 150d3aae-4431-488f-8f19-b522637ee935
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 2%

---

# Integrazione dei dati di ricerca{#integrating-lookup-data}

Data Workbench fornisce un set di trasformazioni che consente al server di Data Workbench di incorporare i dati di ricerca nel set di dati.

I dati di ricerca sono dati esterni provenienti da database aziendali o da file di ricerca che è possibile combinare con i dati dell’evento per creare il set di dati. In generale, puoi utilizzare i dati di ricerca per migliorare i dati dell’evento dalle origini di registro. Concettualmente, è possibile utilizzare i dati di ricerca per popolare i record di dati evento con colonne di informazioni aggiuntive.

Quando si utilizzano i dati di ricerca, questi vengono caricati in una tabella di ricerca residente nella memoria. Una colonna della tabella deve contenere una chiave comune presente anche nei record dei dati dell’evento. I dati nella tabella di ricerca stessa possono essere caricati da un file flat o da un&#39;origine dati ODBC. I dati di ricerca possono essere incorporati nel set di dati durante la fase di elaborazione del registro o di trasformazione del processo di costruzione del set di dati.

Per incorporare i dati di ricerca, è innanzitutto necessario generare un file di ricerca o disporre delle informazioni necessarie per accedere a un database SQL, quindi definire una o più delle seguenti trasformazioni nei file di configurazione del set di dati per l’elaborazione e la trasformazione del registro.

**Per integrare i dati di ricerca nel set di dati**

1. Genera il file di ricerca. Consultare [Compilazione della tabella di ricerca](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8).
1. Definisci uno dei seguenti tipi di trasformazioni nel parametro Transformations nel file di configurazione del set di dati appropriato:

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>La trasformazione [!DNL ODBCLookup] funziona solo se definita nel file [!DNL Transformation.cfg] o in un file [!DNL Transformation Dataset Include].
