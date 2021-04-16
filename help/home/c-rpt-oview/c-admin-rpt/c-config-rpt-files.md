---
description: Nel Report Portal (Portale dei rapporti) è possibile visualizzare i rapporti generati da Report Server come file Excel (.xls o .xlsx) o file .png.
title: Configurazione dei file Report.cfg
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# Configurazione dei file Report.cfg{#configuring-report-cfg-files}

Nel Report Portal (Portale dei rapporti) è possibile visualizzare i rapporti generati da Report Server come file Excel (.xls o .xlsx) o file .png.

Per visualizzare un set di rapporti in [!DNL Report Portal], è necessario impostare i seguenti parametri nel file [!DNL Report.cfg] per tale set di rapporti:

* Nel parametro **[!UICONTROL Output Root]** , specifica la directory principale del documento del server web utilizzato per il portale.
* Nel parametro **[!UICONTROL Report Types]** , specifica Excel, png e/o miniatura come tipi di rapporto che desideri generare.

Quando [!DNL Report Server] genera i rapporti nei formati specificati, questi vengono posizionati nella directory principale dei documenti del server web, che è il punto in cui durante l&#39;installazione si configura [!DNL Report Portal] per accedere ai rapporti.

Per ulteriori informazioni sui parametri [!DNL Report.cfg] specifici, consulta [Parametri Report.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
