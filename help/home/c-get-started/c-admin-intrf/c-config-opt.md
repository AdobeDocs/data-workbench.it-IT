---
description: L'opzione Configurazione apre il file Insight.cfg, che controlla le connessioni a vari server.
solution: Analytics
title: Opzione di configurazione
topic: Data workbench
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Opzione di configurazione{#configuration-option}

L&#39;opzione Configurazione apre il file Insight.cfg, che controlla le connessioni a vari server.

![](assets/cfg_Workstation.png)

**Per modificare il file Insight.cfg**

1. Nella [!DNL Insight.cfg] finestra, modificate i parametri come desiderate. Per una descrizione dettagliata dei parametri nel [!DNL Insight.cfg] file, consultate Parametri [di configurazione](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)di Insight.
1. Per salvare le impostazioni di configurazione, fai clic con il pulsante destro del mouse **[!UICONTROL Insight.cfg (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save as Insight.cfg]**.

**Aggiunta di nuovi server**

1. Nella [!DNL Insight.cfg] finestra fare clic con il pulsante destro del mouse **[!UICONTROL Servers]** e scegliere **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Completare o modificare i parametri del server per consentire a Workbench dati di accedere al server desiderato. Per una descrizione dettagliata dei parametri nel [!DNL Insight.cfg] file, consultate Parametri [di configurazione](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)di Insight.
1. Ripetere i passaggi 1 e 2 per ogni server in cui si desidera configurare una connessione.
1. Per salvare le impostazioni di configurazione, fai clic con il pulsante destro del mouse **[!UICONTROL Insight.cfg (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save as Insight.cfg]**.

Workbench dati tenta di connettersi ai server utilizzando le impostazioni specificate. Se viene stabilita una connessione, nel pannello viene visualizzato un nodo verde [!DNL Servers Manager] come mostrato di seguito. Se Workbench dati non è in grado di connettersi al server, viene visualizzato un nodo rosso.

![](assets/vis_SysStat_RedGreenDots.png)

