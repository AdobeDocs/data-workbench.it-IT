---
description: Per utilizzare un cluster, è necessario designare un Insight Server nel cluster come server principale di Insight.
title: Installazione di Master Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# Installazione di Master Insight Server{#installing-the-master-insight-server}

{{eol}}

Per utilizzare un cluster, è necessario designare un Insight Server nel cluster come server principale di Insight.

Un componente client come [!DNL Insight] o [!DNL Report] si connette al master [!DNL Insight Server] all’inizio di una sessione. Nei punti successivi della sessione, il client potrebbe connettersi ad altri [!DNL Insight Servers] nel cluster per eseguire una query. Queste successive connessioni tra il client e gli altri [!DNL Insight Servers] nel cluster sono brokered dal master [!DNL Insight Server] e sono trasparenti per il cliente.

Oltre a collegamenti di intermediazione tra un cliente e altri [!DNL Insight Servers] nel cluster, il master [!DNL Insight Server] funge da punto amministrativo centrale per l&#39;intero cluster. Quando si amministra un cluster, si aggiorna il master [!DNL Insight Server]. Modifiche amministrative apportate al master [!DNL Insight Server] sono recuperate dall&#39;altro [!DNL Insight Servers] nel cluster.

**Per installare il master[!DNL Insight Server]**

1. Determinare quale macchina fungerà da master [!DNL Insight Server].
1. Installare e configurare [!DNL Insight Server] (in genere, un [!DNL Insight Server] FSU) su questa macchina come descritto in [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Installa [!DNL Insight] e configurare una connessione al master [!DNL Insight Server] come descritto nel *[!DNL Insight]Guida utente*.
