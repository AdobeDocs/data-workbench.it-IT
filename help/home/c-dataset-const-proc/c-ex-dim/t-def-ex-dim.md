---
description: Passaggi per definire le dimensioni estese.
title: Definizione delle dimensioni estese
uuid: 25946998-54ca-4595-a2f9-9c593917643a
exl-id: e1664548-e2b4-47bb-8bec-155c16873e08
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 9%

---

# Definizione delle dimensioni estese{#defining-extended-dimensions}

Passaggi per definire le dimensioni estese.

1. Quando lavori nel profilo del set di dati, apri il [!DNL Profile Manager] e fai clic su **[!UICONTROL Dataset]** per visualizzarne il contenuto.
1. Apri il file [!DNL Transformation.cfg] o il file [!DNL Transformation Dataset Include] in cui desideri definire la dimensione estesa.

   * (Consigliato) Per aprire un file di inclusione di un set di dati, consulta [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md) (File inclusi nel set di dati).

      >[!NOTE]
      >
      >Adobe consiglia di definire dimensioni estese in uno o più nuovi file [!DNL Transformation Dataset Include]. Per ulteriori informazioni, consulta [Creazione di nuovi Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e) (Creazione di nuovi Dataset Include Files).

   * Per aprire il file [!DNL Transformation.cfg], consulta [Modifica del file di configurazione delle trasformazioni](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Transformations]** e fai clic su **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]**>*.
1. Immetti le informazioni appropriate per la dimensione estesa. Per una descrizione dei tipi di trasformazione e informazioni sui relativi parametri, vedere le sezioni seguenti:

   * [Dimensioni conteggiate](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [Dimensioni semplici](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [Dimensioni Many-to-Many (Da molte-a-molte)](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [Dimensioni numeriche](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [Dimensioni anomale](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [Dimensioni temporali](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      Per qualsiasi dimensione estesa definita, è possibile aggiungere una o più righe di commento al parametro Comments per descrivere ulteriormente la dimensione o aggiungere note sul suo utilizzo. Per aggiungere un commento, fai clic con il pulsante destro del mouse sull’etichetta **[!UICONTROL Comments]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

1. Dopo aver definito le dimensioni estese nel file di configurazione, salva il file localmente e salvalo nel profilo del set di dati sul server di Data Workbench.
