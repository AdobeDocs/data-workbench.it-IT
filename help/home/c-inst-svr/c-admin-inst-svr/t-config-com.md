---
description: Il file di configurazione Communications, Communications.cfg, contiene le impostazioni di rete di Insight Server e il percorso del file Access Control.cfg.
title: Configurazione delle comunicazioni
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Configurazione delle comunicazioni{#configuring-communications}

{{eol}}

Il file di configurazione Communications, Communications.cfg, contiene le impostazioni di rete di Insight Server e il percorso del file Access Control.cfg.

Queste impostazioni consentono di connettersi a [!DNL Insight Server].

**Frequenza consigliata:** Solo quando necessario

**Per visualizzare e modificare le impostazioni di comunicazione in[!DNL Insight]**

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.
1. Fai clic con il pulsante destro del mouse sull’icona [!DNL Insight Server] si desidera configurare e fare clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. La [!DNL Communications.cfg] il file si trova all&#39;interno di questa directory.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nel *nome server* colonna per [!DNL Communications.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nel [!DNL Temp] colonna per [!DNL Communications.cfg].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nel [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In [!DNL Communications.cfg] finestra, fai clic su **[!UICONTROL component]** per visualizzarne il contenuto.
1. Se necessario, modifica le impostazioni. Per informazioni sui parametri disponibili in questo file, vedi [Impostazioni di configurazione delle comunicazioni](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![Informazioni sul passaggio](assets/cfg_communications_examplevalues.png)

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
