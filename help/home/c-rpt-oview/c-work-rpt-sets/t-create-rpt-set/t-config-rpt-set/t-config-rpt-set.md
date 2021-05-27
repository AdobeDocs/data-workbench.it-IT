---
description: Dopo aver creato e salvato le aree di lavoro all’interno della cartella del set di rapporti, devi creare un nuovo file Report.cfg.
title: Configurare il set di rapporto
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Configurare il set di rapporto{#configure-the-report-set}

Dopo aver creato e salvato le aree di lavoro all’interno della cartella del set di rapporti, devi creare un nuovo file Report.cfg.

È necessario specificare nel file [!DNL Report.cfg] il set di rapporti quando e come generare e distribuire i rapporti.

**Per creare un nuovo Report.cfg**

1. All’interno di Data Workbench, apri la cartella [!DNL Profile Manager] facendo clic con il pulsante destro del mouse all’interno di un’area di lavoro e facendo clic su **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. Fai clic su **[!UICONTROL Reports]** per aprire la cartella [!DNL Reports].
1. Fai clic sulla cartella del set di rapporti.
1. Nella colonna [!DNL User] della cartella del set di rapporti, fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Create]** > **[!UICONTROL Report]**. Nella colonna [!DNL File]viene visualizzato un nuovo file [!DNL Report.cfg].
1. Nella colonna [!DNL User] del nuovo file [!DNL Report.cfg] fare clic con il pulsante destro del mouse sul segno di spunta del file [!DNL Report.cfg], quindi fare clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Informazioni sul passaggio](assets/cfg_reportcfg.png)

1. Modifica i parametri di configurazione come desiderato. Per informazioni su questi parametri, consulta [Parametri Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >L&#39;esempio [!DNL Report.cfg] mostrato in questo esempio contiene solo i parametri inclusi nel file [!DNL Report.cfg] per impostazione predefinita. Se devi aggiungere parametri aggiuntivi a un file [!DNL Report.cfg], devi farlo utilizzando un editor di testo. Per i passaggi necessari, consulta [Modifica dei file Report.cfg esistenti](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

1. Salva il file facendo clic con il pulsante destro del mouse su **[!UICONTROL Report.cfg (modified)]** nella parte superiore del file e facendo clic su **[!UICONTROL Save as Reports\]***&lt; **[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. Chiudi il file.
1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta nella colonna [!DNL User] del nuovo file [!DNL Report.cfg] e seleziona **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
