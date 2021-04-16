---
description: Per utilizzare un cluster, è necessario designare un Insight Server nel cluster come server principale di Insight.
title: Installazione di Master Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# Installazione di Master Insight Server{#installing-the-master-insight-server}

Per utilizzare un cluster, è necessario designare un Insight Server nel cluster come server principale di Insight.

Un componente client come [!DNL Insight] o [!DNL Report] si connette al master [!DNL Insight Server] all&#39;inizio di una sessione. Nei punti successivi durante la sessione, il client potrebbe connettersi ad altri [!DNL Insight Servers] nel cluster per eseguire una query. Queste connessioni successive tra il client e l&#39;altro [!DNL Insight Servers] nel cluster sono gestite dal principale [!DNL Insight Server] e sono trasparenti per il client.

Oltre a brokering delle connessioni tra un client e altri [!DNL Insight Servers] nel cluster, il master [!DNL Insight Server] funge da punto amministrativo centrale per l&#39;intero cluster. Quando si amministra un cluster, si aggiorna il master [!DNL Insight Server]. Le modifiche amministrative apportate al master [!DNL Insight Server] vengono recuperate dall&#39;altro [!DNL Insight Servers] nel cluster.

**Per installare il master[!DNL Insight Server]**

1. Determinare quale computer fungerà da master [!DNL Insight Server].
1. Installa e configura [!DNL Insight Server] (in genere, una [!DNL Insight Server] FSU) su questo computer come descritto in [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Installa [!DNL Insight] e configura una connessione al master [!DNL Insight Server] come descritto nella *[!DNL Insight]Guida utente*.
