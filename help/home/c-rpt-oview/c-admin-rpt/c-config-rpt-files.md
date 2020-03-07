---
description: Nel portale dei report puoi visualizzare i report generati dal server dei report come file Excel (.xls o .xlsx) o .png.
solution: Analytics
title: Configurazione dei file Report.cfg
topic: Data workbench
uuid: b6ce1621-283f-458d-a88d-a062539d243b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurazione dei file Report.cfg{#configuring-report-cfg-files}

Nel portale dei report puoi visualizzare i report generati dal server dei report come file Excel (.xls o .xlsx) o .png.

Per visualizzare un set di report nel [!DNL Report Portal], devi impostare i seguenti parametri nel [!DNL Report.cfg] file per quel set di report:

* Nel **[!UICONTROL Output Root]** parametro, specificate la radice del documento del server Web utilizzato per il portale.
* Nel **[!UICONTROL Report Types]** parametro, specificate Excel, png e/o miniatura come tipi di rapporto che desiderate generare.

Quando [!DNL Report Server] genera i rapporti nei formati specificati, questi vengono inseriti nella directory principale del documento del server Web, dove durante l&#39;installazione si configura l&#39;utente [!DNL Report Portal] per accedere ai rapporti.

Per ulteriori informazioni sui [!DNL Report.cfg] parametri specifici, vedi Parametri [Report.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
