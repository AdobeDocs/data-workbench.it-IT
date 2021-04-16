---
description: Il file di configurazione Communications, Communications.cfg, contiene le impostazioni di rete di Insight Server e il percorso del file Access Control.cfg.
title: Configurazione delle comunicazioni
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Configurazione delle comunicazioni{#configuring-communications}

Il file di configurazione Communications, Communications.cfg, contiene le impostazioni di rete di Insight Server e il percorso del file Access Control.cfg.

Queste impostazioni consentono di connettersi a [!DNL Insight Server].

**Frequenza consigliata:** solo se necessario

**Per visualizzare e modificare le impostazioni di comunicazione in[!DNL Insight]**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.
1. Fai clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] da configurare e fai clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. Il file [!DNL Communications.cfg] si trova all&#39;interno di questa directory.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* per [!DNL Communications.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella colonna [!DNL Temp] per [!DNL Communications.cfg].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Nella finestra [!DNL Communications.cfg] fare clic su **[!UICONTROL component]** per visualizzarne il contenuto.
1. Se necessario, modifica le impostazioni. Per informazioni sui parametri disponibili in questo file, consulta [Impostazioni di configurazione delle comunicazioni](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![Informazioni sul passaggio](assets/cfg_communications_examplevalues.png)

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
