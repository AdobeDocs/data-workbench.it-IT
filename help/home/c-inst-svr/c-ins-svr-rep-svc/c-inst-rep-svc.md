---
description: Il servizio Insight ServerReplication consente di trasmettere i dati dell’evento raccolti e memorizzati su un computer Insight Server a un altro computer Insight Server.
title: Installazione del servizio di replica
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# Installazione del servizio di replica{#installing-the-replication-service}

{{eol}}

Il servizio Insight ServerReplication consente di trasmettere i dati dell’evento raccolti e memorizzati su un computer Insight Server a un altro computer Insight Server.

In genere, il computer in cui i dati vengono raccolti e memorizzati è configurato per l&#39;esecuzione come [!DNL Repeater] macchina. Vedi [Funzionalità Repeater (Ripetitore)](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). La [!DNL Replication Service], configurato dalla [!DNL Replicate.cfg] abilita un [!DNL Insight Server] macchina per recuperare i dati dal [!DNL Repeater] e archiviarlo localmente. La [!DNL Insight Server] macchina è indicata come computer di destinazione. Multipli [!DNL Insight Server] Le DPU possono connettersi a un singolo [!DNL Repeater] per richiedere copie dei dati evento da includere in più set di dati.

È possibile utilizzare [!DNL Replication Service] in infrastrutture di rete con più livelli di firewall per ottenere comunicazioni da una porta all’altra tra componenti separati da firewall.

**Per installare[!DNL Replication Service]**

La [!DNL Replicate.cfg] deve essere installato come parte del [!DNL Insight Server] installazione. Puoi trovare il file all’interno del [!DNL Components] cartella [!DNL Insight Server] directory di installazione. Se non disponi di questo file, contatta l’Adobe.
