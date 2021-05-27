---
description: Puoi definire le trasformazioni di dati da applicare durante la fase di elaborazione del registro o di trasformazione della costruzione del set di dati.
title: Definizione di una trasformazione
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
exl-id: 61ce8093-9e64-419a-bddc-dc2225c0eaab
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 5%

---

# Definizione di una trasformazione{#defining-a-transformation}

Puoi definire le trasformazioni di dati da applicare durante la fase di elaborazione del registro o di trasformazione della costruzione del set di dati.

>[!NOTE]
>
>Adobe consiglia di definire le trasformazioni nei file [!DNL Log Processing] o [!DNL Transformation Dataset Include] anziché in [!DNL Log Processing.cfg] o [!DNL Transformation.cfg].

Le seguenti trasformazioni funzionano solo se definite nel file [!DNL Transformation.cfg] o in un file [!DNL Transformation Dataset Include] :

* [](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)AppendURII
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [Origini dati ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessionize](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**Per definire una trasformazione**

1. Utilizza il [!DNL Profile Manager] per aprire il file di configurazione del set di dati in cui desideri definire la trasformazione.

   * (Consigliato) Per aprire un file di inclusione di un set di dati, consulta [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md) (File inclusi nel set di dati).
   * Per aprire il file [!DNL Log Processing.cfg], vedere [Modifica del file di configurazione dell&#39;elaborazione del registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * Per aprire il file [!DNL Transformation.cfg], consulta [Modifica del file di configurazione delle trasformazioni](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Transformations]**, quindi fai clic su **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]**>*.
1. Immetti le informazioni appropriate per la tua trasformazione. Per una descrizione dei tipi di trasformazione e informazioni sui relativi parametri, vedere le sezioni seguenti:

   * [Trasformazioni standard](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [Trasformazioni URI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [Integrazione dei dati di ricerca](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. Dopo aver definito le trasformazioni nel file di configurazione, salva il file localmente e salvalo nel profilo del set di dati sul server di Data Workbench.

       Suggerimenti per definire e modificare le trasformazioni:
   
   * Quando modifichi la configurazione di una trasformazione all’interno di una finestra di Data Workbench, puoi utilizzare i tasti di scelta rapida per le funzioni di modifica di base, tra cui Taglia (Ctrl+x ), Copia (Ctrl+c) , Incolla (Ctrl+v ), Annulla (Ctrl+z ), Ripristina (Ctrl+Maiusc+Z ), seleziona la sezione (Clic+trascina) e seleziona tutto (Ctrl+a ). Inoltre, è possibile utilizzare le scelte rapide per copiare e incollare testo o intere definizioni di trasformazione da un file di configurazione ( [!DNL .cfg]) a un altro.
   * Per qualsiasi trasformazione definita, è possibile aggiungere una o più righe di commento al parametro Comments per descrivere ulteriormente la trasformazione o aggiungere note sul suo utilizzo. Per aggiungere un commento utilizzando Data Workbench, fai clic con il pulsante destro del mouse sull’etichetta **[!UICONTROL Comments]**, quindi fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

   * Puoi aprire la configurazione di qualsiasi trasformazione da un [!DNL Transformation Dependency Map]. Dopo aver aperto la configurazione, puoi modificarla e salvare le modifiche. Per informazioni su [!DNL Transformation Dependency Maps], consulta [Strumenti di configurazione del set di dati](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

   * Un output di stringa vuota da una trasformazione può sovrascrivere una stringa non vuota nel campo di output.
