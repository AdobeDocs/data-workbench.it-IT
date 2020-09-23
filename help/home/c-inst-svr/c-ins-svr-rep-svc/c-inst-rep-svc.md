---
description: Il servizio Insight ServerReplication Service consente di trasmettere i dati dell'evento raccolti e memorizzati in un computer Insight Server a un altro computer Insight Server.
solution: Analytics
title: Installazione del servizio di replica
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---


# Installazione del servizio di replica{#installing-the-replication-service}

Il servizio Insight ServerReplication Service consente di trasmettere i dati dell&#39;evento raccolti e memorizzati in un computer Insight Server a un altro computer Insight Server.

In genere, il computer in cui vengono raccolti e memorizzati i dati è configurato per l&#39;esecuzione come [!DNL Repeater] computer. Consultate Funzionalità [Ripetitore](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). Il [!DNL Replication Service], configurato dal [!DNL Replicate.cfg] file, consente a un [!DNL Insight Server] computer di recuperare i dati dal [!DNL Repeater] computer e memorizzarli localmente. La [!DNL Insight Server] macchina viene definita macchina di destinazione. Più [!DNL Insight Server] unità di elaborazione dati possono connettersi a una singola unità [!DNL Repeater] per richiedere copie dei dati dell&#39;evento da includere in più set di dati.

È possibile utilizzare le infrastrutture [!DNL Replication Service] di rete con più livelli di firewall per ottenere comunicazioni da una porta all’altra tra componenti separati da firewall.

**Per installare il[!DNL Replication Service]**

Il [!DNL Replicate.cfg] file deve essere installato come parte dell&#39; [!DNL Insight Server] installazione. Potete trovare il file nella [!DNL Components] cartella della directory di [!DNL Insight Server] installazione. Se non disponete di questo file, contattate  Adobe.
