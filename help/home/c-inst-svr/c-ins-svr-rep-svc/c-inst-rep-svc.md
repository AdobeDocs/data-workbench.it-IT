---
description: Il servizio Insight ServerReplication consente di trasmettere i dati dell’evento raccolti e memorizzati su un computer Insight Server a un altro computer Insight Server.
title: Installazione del servizio di replica
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# Installazione del servizio di replica{#installing-the-replication-service}

Il servizio Insight ServerReplication consente di trasmettere i dati dell’evento raccolti e memorizzati su un computer Insight Server a un altro computer Insight Server.

In genere, il computer in cui vengono raccolti e memorizzati i dati viene configurato per l&#39;esecuzione come [!DNL Repeater] computer. Vedere [Funzionalità Repeater](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). Il [!DNL Replication Service], configurato dal file [!DNL Replicate.cfg], consente a un computer [!DNL Insight Server] di recuperare i dati dal computer [!DNL Repeater] e archiviarli localmente. Il computer [!DNL Insight Server] è indicato come computer di destinazione. Più DPU [!DNL Insight Server] possono connettersi a un singolo [!DNL Repeater] per richiedere copie dei dati dell’evento da includere in più set di dati.

È possibile utilizzare [!DNL Replication Service] nelle infrastrutture di rete con più livelli di firewall per ottenere comunicazioni a una porta da una a una porta tra i componenti separati da firewall.

**Per installare[!DNL Replication Service]**

Il file [!DNL Replicate.cfg] deve essere installato come parte dell&#39;installazione di [!DNL Insight Server]. Puoi trovare il file nella cartella [!DNL Components] della directory di installazione [!DNL Insight Server]. Se non disponi di questo file, contatta l’Adobe.
