---
description: Il file di configurazione DPU, DPU.cfg, specifica vari parametri di prestazioni per Insight Server.
title: Configurazione di DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# Configurazione di DPU.cfg{#configuring-dpu-cfg}

Il file di configurazione DPU, DPU.cfg, specifica vari parametri di prestazioni per Insight Server.

La modalità di impostazione di questi parametri dipende dalla dimensione del set di dati e da molti altri fattori. Contatta Adobe Consulting Services per assistenza sulla regolazione delle prestazioni.

**Frequenza consigliata:** solo se necessario

**Per modificare le impostazioni delle prestazioni  [!DNL Insight Server] DPU**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.
1. Fai clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] da configurare e fai clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. Il file [!DNL DPU.cfg] si trova all&#39;interno di questa directory.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* per [!DNL DPU.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella colonna [!DNL Temp] per [!DNL DPU.cfg].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Nella finestra [!DNL DPU.cfg], fai clic su componente per visualizzarne il contenuto.
1. Se necessario, modifica le impostazioni delle prestazioni e del percorso. Per un elenco dei parametri disponibili in questo file, consulta [Impostazioni delle prestazioni DPU](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1).

   >[!NOTE]
   >
   >Contatta l&#39;Adobe prima di modificare uno qualsiasi dei parametri in questo file.

   ![](assets/cfg_DPU_egvalues.png)

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
