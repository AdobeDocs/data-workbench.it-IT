---
description: Il file di configurazione DPU, DPU.cfg, specifica vari parametri di prestazioni per Insight Server.
solution: Insight
title: Configurazione di DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurazione di DPU.cfg{#configuring-dpu-cfg}

Il file di configurazione DPU, DPU.cfg, specifica vari parametri di prestazioni per Insight Server.

La modalità di impostazione di questi parametri dipende dalla dimensione del set di dati e da molti altri fattori. Per assistenza nell&#39;ottimizzazione delle prestazioni, contattate i servizi di consulenza Adobe.

**Frequenza consigliata:** Solo se necessario

**Per modificare le impostazioni delle prestazioni[!DNL Insight Server]DPU**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.
1. Fare clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] file da configurare e fare clic su **[!UICONTROL Server Files]**.
1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL DPU.cfg] file si trova all&#39;interno di questa directory.
1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server per [!DNL DPU.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL DPU.cfg].
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Nella [!DNL DPU.cfg] finestra, fate clic sul componente per visualizzarne il contenuto.
1. Se necessario, modificate le prestazioni e le impostazioni del percorso. Per un elenco dei parametri disponibili in questo file, consultate Impostazioni [prestazioni](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1)DPU.

   >[!NOTE]
   >
   >Contattate Adobe prima di modificare uno qualsiasi dei parametri in questo file.

   ![](assets/cfg_DPU_egvalues.png)

1. Salvate le modifiche al server effettuando le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. Fare [!DNL Server Files Manager]clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL Temp] colonna e selezionare **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

