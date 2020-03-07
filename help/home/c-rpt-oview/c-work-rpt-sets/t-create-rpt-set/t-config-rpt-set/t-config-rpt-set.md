---
description: Dopo aver creato e salvato le aree di lavoro all’interno della cartella del set di rapporti, dovete creare un nuovo file Report.cfg.
solution: Analytics
title: Configurare il set di report
topic: Data workbench
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurare il set di report{#configure-the-report-set}

Dopo aver creato e salvato le aree di lavoro all’interno della cartella del set di rapporti, dovete creare un nuovo file Report.cfg.

È necessario specificare nel [!DNL Report.cfg] file il set di rapporti quando e come generare e distribuire i rapporti.

**Per creare un nuovo report.cfg**

1. Nel workbench dati, aprire il modulo facendo clic con il pulsante destro del mouse all&#39;interno di un&#39;area di lavoro e scegliendo [!DNL Profile Manager] > **[!UICONTROL Admin]** > **[!UICONTROL Profile]** **[!UICONTROL Profile Manager]**.
1. Fate clic **[!UICONTROL Reports]** per aprire la [!DNL Reports] cartella.
1. Fate clic sulla cartella del set di rapporti.
1. Nella [!DNL User] colonna della cartella del set di rapporti, fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Create]** > **[!UICONTROL Report]**. Nella [!DNL Report.cfg] colonna viene visualizzato un nuovo [!DNL File]file.
1. Nella [!DNL User] colonna del nuovo [!DNL Report.cfg] file, fare clic con il pulsante destro del mouse sul segno di spunta del [!DNL Report.cfg] file, quindi scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Informazioni sul passaggio](assets/cfg_reportcfg.png)

1. Modificate i parametri di configurazione come desiderate. Per informazioni su questi parametri, consultate Parametri [](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.

   >[!NOTE]
   >
   >L&#39;esempio [!DNL Report.cfg] mostrato in questo esempio contiene solo i parametri inclusi nel [!DNL Report.cfg] file per impostazione predefinita. Per aggiungere parametri aggiuntivi a un [!DNL Report.cfg] file, è necessario utilizzare un editor di testo. Per i passaggi necessari, vedere [Modifica dei file](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)Report.cfg esistenti.

1. Salvate il file facendo clic con il pulsante destro del mouse **[!UICONTROL Report.cfg (modified)]** nella parte superiore del file e facendo clic su **[!UICONTROL Salva come rapporti\]***&lt;**[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. Chiudete il file.
1. Fare clic con il pulsante destro del [!DNL Profile Manager]mouse sul segno di spunta nella [!DNL User] colonna per il nuovo [!DNL Report.cfg] file e selezionare **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
