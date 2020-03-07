---
description: È possibile definire le trasformazioni dei dati da applicare durante l'elaborazione del registro o la fase di trasformazione della costruzione del set di dati.
solution: Analytics
title: Definizione di una trasformazione
topic: Data workbench
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Definizione di una trasformazione{#defining-a-transformation}

È possibile definire le trasformazioni dei dati da applicare durante l&#39;elaborazione del registro o la fase di trasformazione della costruzione del set di dati.

>[!NOTE]
>
>Adobe consiglia di definire le trasformazioni in [!DNL Log Processing] o [!DNL Transformation Dataset Include] file anziché in [!DNL Log Processing.cfg] o [!DNL Transformation.cfg].

Le seguenti trasformazioni funzionano solo se definite nel [!DNL Transformation.cfg] file o in un [!DNL Transformation Dataset Include] file:

* [](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)AppendURII
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [Origini dati ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessionizza](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**Definizione di una trasformazione**

1. Utilizzare [!DNL Profile Manager] per aprire il file di configurazione del dataset in cui si desidera definire la trasformazione.

   * (Consigliato) Per aprire un file di inclusione di un set di dati, vedere [Set di dati Includi file](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).
   * Per aprire il [!DNL Log Processing.cfg] file, vedere [Modifica del file](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)di configurazione dell&#39;elaborazione del registro.

   * Per aprire il [!DNL Transformation.cfg] file, vedere [Modifica del file](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)di configurazione delle trasformazioni.

1. Fare clic con il pulsante destro del mouse **[!UICONTROL Transformations]**, quindi scegliere **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]**>*.
1. Inserite le informazioni appropriate per la trasformazione. Per una descrizione dei tipi di trasformazione e informazioni sui relativi parametri, vedere le sezioni seguenti:

   * [Trasformazioni standard](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [Trasformazioni URI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [Integrazione dei dati di ricerca](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. Dopo aver definito le trasformazioni nel file di configurazione, salvate il file localmente e salvatelo nel profilo del dataset sul server workbench dati.

       Suggerimenti per definire e modificare le trasformazioni:
   
   * Quando si modifica la configurazione di una trasformazione all&#39;interno di una finestra del workbench dati, è possibile utilizzare i tasti di scelta rapida per le funzioni di modifica di base, inclusi Taglia (Ctrl+x ), Copia (Ctrl+c), Incolla (Ctrl+v), Annulla (Ctrl+z ), Ripristina (Ctrl+Maiusc+Z ), Seleziona la sezione (Clic+trascinamento) e seleziona tutto (Ctrl+a ). Inoltre, è possibile utilizzare i collegamenti per copiare e incollare testo o intere definizioni di trasformazione da un file di configurazione ( [!DNL .cfg]) a un altro.
   * Per qualsiasi trasformazione definita, potete aggiungere una o più righe di commento al parametro Commenti per descrivere ulteriormente la trasformazione o aggiungere note sul suo utilizzo. Per aggiungere un commento utilizzando il workbench dati, fare clic con il pulsante destro del mouse sull&#39; **[!UICONTROL Comments]** etichetta, quindi scegliere **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

   * È possibile aprire la configurazione di qualsiasi trasformazione da un [!DNL Transformation Dependency Map]. Dopo aver aperto la configurazione, potete modificarla e salvare le modifiche. Per informazioni su [!DNL Transformation Dependency Maps], vedere Strumenti [di configurazione](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)DataSet.

   * Un output di stringa vuoto da una trasformazione può sovrascrivere una stringa non vuota nel campo di output.

