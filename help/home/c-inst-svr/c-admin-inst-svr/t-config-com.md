---
description: Il file di configurazione Communications, Communications.cfg, contiene le impostazioni di rete di Insight Server e il percorso del file Access Control.cfg.
solution: Insight
title: Configurazione delle comunicazioni
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurazione delle comunicazioni{#configuring-communications}

Il file di configurazione Communications, Communications.cfg, contiene le impostazioni di rete di Insight Server e il percorso del file Access Control.cfg.

Queste impostazioni consentono di connettersi a [!DNL Insight Server].

**Frequenza consigliata:** Solo se necessario

**Per visualizzare e modificare le impostazioni di comunicazione in[!DNL Insight]**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.
1. Fare clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] file da configurare e fare clic su **[!UICONTROL Server Files]**.
1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL Communications.cfg] file si trova all&#39;interno di questa directory.
1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server per [!DNL Communications.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Communications.cfg].
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Nella [!DNL Communications.cfg] finestra, fate clic **[!UICONTROL component]** per visualizzarne il contenuto.
1. Modificate le impostazioni in base alle esigenze. Per informazioni sui parametri disponibili in questo file, consulta Impostazioni [di configurazione delle](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1)comunicazioni.

   ![Informazioni sul passaggio](assets/cfg_communications_examplevalues.png)

1. Salvate le modifiche al server effettuando le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. Fare [!DNL Server Files Manager]clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL Temp] colonna e selezionare **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

