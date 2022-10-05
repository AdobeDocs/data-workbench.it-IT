---
description: Il file di configurazione DPU, DPU.cfg, specifica vari parametri di prestazioni per Insight Server.
title: Configurazione di DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# Configurazione di DPU.cfg{#configuring-dpu-cfg}

{{eol}}

Il file di configurazione DPU, DPU.cfg, specifica vari parametri di prestazioni per Insight Server.

La modalità di impostazione di questi parametri dipende dalla dimensione del set di dati e da molti altri fattori. Contatta Adobe Consulting Services per assistenza sulla regolazione delle prestazioni.

**Frequenza consigliata:** Solo quando necessario

**Per modificare [!DNL Insight Server] Impostazioni delle prestazioni DPU**

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.
1. Fai clic con il pulsante destro del mouse sull’icona [!DNL Insight Server] si desidera configurare e fare clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. La [!DNL DPU.cfg] il file si trova all&#39;interno di questa directory.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nel *nome server* colonna per [!DNL DPU.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nel [!DNL Temp] colonna per [!DNL DPU.cfg].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nel [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In [!DNL DPU.cfg] fai clic su componente per visualizzarne il contenuto.
1. Se necessario, modifica le impostazioni delle prestazioni e del percorso. Per un elenco dei parametri disponibili in questo file, vedi [Impostazioni delle prestazioni DPU](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1).

   >[!NOTE]
   >
   >Contatta l&#39;Adobe prima di modificare uno qualsiasi dei parametri in questo file.

   ![](assets/cfg_DPU_egvalues.png)

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
