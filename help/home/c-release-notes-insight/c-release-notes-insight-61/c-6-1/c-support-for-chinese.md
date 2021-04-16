---
description: L’applicazione client di Data Workbench ora supporta il cinese semplificato.
title: Localizzazione semplificata in cinese
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 0%

---


# Localizzazione cinese semplificata{#simplified-chinese-localization}

L’applicazione client di Data Workbench ora supporta il cinese semplificato.

**Per installare il cinese** semplificato:

Prima di configurare [!DNL Insight.exe] e i file di supporto, è necessario uscire dall&#39;applicazione client.

1. Crea una scelta rapida che passa l&#39;impostazione della riga di comando al file [!DNL insight.exe].

   ```
   Insight.exe -zh-cn
   ```

1. Configura [!DNL Insight.cfg] per supportare i caratteri di font a byte singolo e doppio.

   Data Workbench supporta attualmente sia l’inglese che il cinese semplificato. È possibile selezionare i font per supportare entrambe le lingue seguenti:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Riavvia [!DNL Insight.exe].

