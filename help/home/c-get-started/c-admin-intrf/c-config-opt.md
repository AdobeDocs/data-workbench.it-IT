---
description: L’opzione Configurazione apre il file Insight.cfg, che controlla le connessioni a vari server.
title: Opzione di configurazione
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 2%

---

# Opzione di configurazione{#configuration-option}

{{eol}}

L’opzione Configurazione apre il file Insight.cfg, che controlla le connessioni a vari server.

![](assets/cfg_Workstation.png)

**Per modificare il file Insight.cfg**

1. In [!DNL Insight.cfg] finestra, modifica i parametri come desiderato. Per una descrizione dettagliata dei parametri nel [!DNL Insight.cfg] file, vedi [Parametri di configurazione di Insight](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Per salvare le impostazioni di configurazione, fai clic con il pulsante destro del mouse su **[!UICONTROL Insight.cfg (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save as Insight.cfg]**.

**Aggiunta di nuovi server**

1. In [!DNL Insight.cfg] finestra, clic con il pulsante destro del mouse **[!UICONTROL Servers]** e fai clic su **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Completa o modifica i parametri del server per fornire a Data Workbench l’accesso al server desiderato. Per una descrizione dettagliata dei parametri nel [!DNL Insight.cfg] file, vedi [Parametri di configurazione di Insight](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Ripetere i passaggi 1 e 2 per ogni server in cui si desidera configurare una connessione.
1. Per salvare le impostazioni di configurazione, fai clic con il pulsante destro del mouse su **[!UICONTROL Insight.cfg (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save as Insight.cfg]**.

Data Workbench tenta di connettersi ai server utilizzando le impostazioni specificate. Se viene stabilita una connessione, viene visualizzato un nodo verde nel [!DNL Servers Manager] come mostrato di seguito. Se Data Workbench non è in grado di connettersi al server, viene visualizzato un nodo rosso.

![](assets/vis_SysStat_RedGreenDots.png)
