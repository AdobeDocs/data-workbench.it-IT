---
description: Crea intestazioni personalizzate per l’esportazione di colonne per i file di esportazione dei segmenti, per aggiungere descrizioni facilmente comprensibili per i segmenti esportati. Questa funzione di esportazione consente inoltre di trasmettere i dati come file TSV e CSV.
title: Esportazione segmento con intestazioni personalizzate
uuid: 186e7868-13b2-42e1-b83f-5a752ee9b407
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Esportazione segmento con intestazioni personalizzate{#segment-export-with-custom-headers}

Crea intestazioni personalizzate per l’esportazione di colonne per i file di esportazione dei segmenti, per aggiungere descrizioni facilmente comprensibili per i segmenti esportati. Questa funzione di esportazione consente inoltre di trasmettere i dati come file TSV e CSV.

Sono state aggiunte nuove funzionalità a Segment Export (Esportazione segmenti), inclusa la possibilità di esportare con un’intestazione, oppure nei formati CSV e TSV.

Potete creare intestazioni di colonna per i file di esportazione.

## Creazione di una nuova esportazione di segmenti {#section-cffff55855f8467ea468b71393ab7676}

1. Aprite un’area di lavoro e fate clic con il pulsante destro del mouse **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]**.

1. Fare clic con il pulsante destro del mouse e selezionare **[!UICONTROL Add Level > Extended]** > Scegli un elemento.
1. Fare clic con il pulsante destro del mouse sul titolo e selezionare **[!UICONTROL Add Attribute.]** Selezionare una dimensione dal menu.

1. Fai clic con il pulsante destro del mouse sul titolo e seleziona **[!UICONTROL Add Metric.]** Seleziona una metrica dal menu.

1. Fare clic con il pulsante destro del mouse sul titolo e selezionare **[!UICONTROL New Segment Export]**.

   ![](assets/segment_export_headers.png)

   **[!UICONTROL New Segment Export with Header]** compila automaticamente il Nome colonna con il nome della metrica. **[!UICONTROL New Segment Export]** richiede di impostare un nome personalizzato. ![](assets/segment_export_with_headers.png)

   >[!NOTE]
   >
   >Il campo Nome colonna non può essere lasciato vuoto o l’intestazione non sarà presente.

1. Fai clic con il pulsante destro del mouse e assegna un nome al segmento, quindi fai clic su **[!UICONTROL Save Export File]**.

   Viene aperta una finestra di esportazione.

1. Fate clic con il pulsante destro del mouse sul nome dell’esportazione e fate clic su **[!UICONTROL Salva con nome<export filename>]**.

   ![](assets/segment_export_headers_7.png)

1. Right-click [!DNL Admin] > [!DNL Profile Manager] > [!DNL Expand Export]. Individuate il file di esportazione appena creato e salvatelo in un profilo esistente.

   ![](assets/segment_export_headers_8.png)

