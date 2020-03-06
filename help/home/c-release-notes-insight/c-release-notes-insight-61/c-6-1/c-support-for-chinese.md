---
description: L'applicazione client workbench dati ora supporta il cinese semplificato.
solution: Analytics
title: Localizzazione semplificata in cinese
topic: Data workbench
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Localizzazione semplificata in cinese{#simplified-chinese-localization}

L&#39;applicazione client workbench dati ora supporta il cinese semplificato.

**Per installare il cinese** semplificato:

Prima di configurare [!DNL Insight.exe] e supportare i file, è necessario uscire dall&#39;applicazione client.

1. Creare una scelta rapida che consenta di passare l&#39;impostazione della riga di comando al [!DNL insight.exe] file.

   ```
   Insight.exe -zh-cn
   ```

1. Configurare [!DNL Insight.cfg] per supportare i caratteri di font a byte singolo e doppio.

   Data Workbench supporta attualmente sia l&#39;inglese che il cinese semplificato. È possibile selezionare i font per supportare entrambe le lingue:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Riavviate [!DNL Insight.exe].

