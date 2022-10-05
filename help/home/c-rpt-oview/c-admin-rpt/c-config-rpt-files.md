---
description: Nel Report Portal (Portale dei rapporti) è possibile visualizzare i rapporti generati da Report Server come file Excel (.xls o .xlsx) o file .png.
title: Configurazione dei file Report.cfg
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# Configurazione dei file Report.cfg{#configuring-report-cfg-files}

{{eol}}

Nel Report Portal (Portale dei rapporti) è possibile visualizzare i rapporti generati da Report Server come file Excel (.xls o .xlsx) o file .png.

Per visualizzare un set di rapporti nel [!DNL Report Portal], è necessario impostare i seguenti parametri nel [!DNL Report.cfg] file per quel set di rapporti:

* In **[!UICONTROL Output Root]** specificare la directory principale del documento del server Web utilizzato per il portale.
* In **[!UICONTROL Report Types]** Specifica Excel, png e/o miniatura come tipi di rapporto che desideri generare.

Quando [!DNL Report Server] genera i report nei formati specificati, li inserisce nella directory principale dei documenti del server web, che è il punto in cui durante l&#39;installazione si configura il [!DNL Report Portal] per accedere ai rapporti.

Per ulteriori informazioni sulle specifiche [!DNL Report.cfg] parametri, vedi [Parametri Report.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
