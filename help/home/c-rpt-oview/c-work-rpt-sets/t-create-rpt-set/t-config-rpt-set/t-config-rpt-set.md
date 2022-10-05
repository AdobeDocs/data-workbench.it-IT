---
description: Dopo aver creato e salvato le aree di lavoro all’interno della cartella del set di rapporti, devi creare un nuovo file Report.cfg.
title: Configurare il set di rapporto
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Configurare il set di rapporto{#configure-the-report-set}

{{eol}}

Dopo aver creato e salvato le aree di lavoro all’interno della cartella del set di rapporti, devi creare un nuovo file Report.cfg.

È necessario specificare nella [!DNL Report.cfg] per il set di rapporti quando e come generare e distribuire i rapporti.

**Per creare un nuovo Report.cfg**

1. All’interno di Data Workbench, apri la [!DNL Profile Manager] facendo clic con il pulsante destro del mouse all’interno di un’area di lavoro e facendo clic su **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. Fai clic su **[!UICONTROL Reports]** per aprire [!DNL Reports] cartella.
1. Fai clic sulla cartella del set di rapporti.
1. In [!DNL User] per la cartella del set di rapporti, fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Create]** > **[!UICONTROL Report]**. Nuovo [!DNL Report.cfg] il file viene visualizzato nel [!DNL File]colonna.
1. In [!DNL User] colonna per il nuovo [!DNL Report.cfg] , fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL Report.cfg] file, quindi fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Informazioni sul passaggio](assets/cfg_reportcfg.png)

1. Modifica i parametri di configurazione come desiderato. Per informazioni su questi parametri, vedi [Parametri Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >Il campione [!DNL Report.cfg] mostrato in questo esempio contiene solo i parametri inclusi nel [!DNL Report.cfg] per impostazione predefinita. Se devi aggiungere parametri aggiuntivi a un [!DNL Report.cfg] , è necessario utilizzare un editor di testo. Per i passaggi da seguire, vedi [Modifica dei file Report.cfg esistenti](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

1. Salva il file facendo clic con il pulsante destro del mouse **[!UICONTROL Report.cfg (modified)]** nella parte superiore del file e facendo clic su **[!UICONTROL Save as Reports\]***&lt; **[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. Chiudi il file.
1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta nel [!DNL User] colonna per il nuovo [!DNL Report.cfg] e seleziona **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
