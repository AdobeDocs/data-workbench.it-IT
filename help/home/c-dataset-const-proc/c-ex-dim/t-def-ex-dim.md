---
description: Passaggi per definire le dimensioni estese.
solution: Analytics
title: Definizione delle dimensioni estese
topic: Data workbench
uuid: 25946998-54ca-4595-a2f9-9c593917643a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Definizione delle dimensioni estese{#defining-extended-dimensions}

Passaggi per definire le dimensioni estese.

1. Quando lavori nel profilo del set di dati, apri il set di dati [!DNL Profile Manager] e fai clic **[!UICONTROL Dataset]** per visualizzarne il contenuto.
1. Aprire il [!DNL Transformation.cfg] file o il [!DNL Transformation Dataset Include] file in cui si desidera definire la dimensione estesa.

   * (Consigliato) Per aprire un file di inclusione di un set di dati, vedere [Set di dati Includi file](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

      >[!NOTE]
      >
      >Adobe consiglia di definire le dimensioni estese in uno o più nuovi [!DNL Transformation Dataset Include] file. Per ulteriori informazioni, vedere [Creazione di nuovi set di dati con file](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e)di inclusione.

   * Per aprire il [!DNL Transformation.cfg] file, vedere [Modifica del file](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)di configurazione delle trasformazioni.

1. Fare clic con il pulsante destro del mouse **[!UICONTROL Transformations]** e scegliere **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]**>*.
1. Inserite le informazioni appropriate per la dimensione estesa. Per una descrizione dei tipi di trasformazione e informazioni sui relativi parametri, vedere le sezioni seguenti:

   * [Dimensioni numerabili](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [Dimensioni semplici](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [Dimensioni molte-molte](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [Dimensioni numeriche](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [Dimensioni standard](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [Dimensioni tempo](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      Per qualsiasi dimensione estesa definita, potete aggiungere una o più righe di commento al parametro Commenti per descrivere ulteriormente la dimensione o aggiungere note sul suo utilizzo. Per aggiungere un commento, fare clic con il pulsante destro del mouse sull’ **[!UICONTROL Comments]** etichetta e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

1. Dopo aver definito le dimensioni estese nel file di configurazione, salvare il file localmente e salvarlo nel profilo del dataset sul server workbench dati.
