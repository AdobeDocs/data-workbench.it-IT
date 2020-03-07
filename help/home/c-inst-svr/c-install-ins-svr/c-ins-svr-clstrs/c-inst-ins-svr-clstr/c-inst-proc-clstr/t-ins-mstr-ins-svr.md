---
description: Per utilizzare un cluster, è necessario designare un server Insight nel cluster che funga da server di visualizzazione principale.
solution: Insight
title: Installazione di Master Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Installazione di Master Insight Server{#installing-the-master-insight-server}

Per utilizzare un cluster, è necessario designare un server Insight nel cluster che funga da server di visualizzazione principale.

Un componente client, ad esempio [!DNL Insight] o [!DNL Report] , si connette al master [!DNL Insight Server] all&#39;inizio di una sessione. Nei punti successivi della sessione, il client potrebbe connettersi ad altri [!DNL Insight Servers] del cluster per eseguire una query. Tali connessioni successive tra il client e l&#39;altro [!DNL Insight Servers] nel cluster sono gestite dal master [!DNL Insight Server] e sono trasparenti per il client.

Oltre alle connessioni di intermediazione tra un client e altri [!DNL Insight Servers] nel cluster, il master [!DNL Insight Server] funge da punto amministrativo centrale per l&#39;intero cluster. Quando amministrate un cluster, aggiornate il master [!DNL Insight Server]. Le modifiche amministrative apportate al master [!DNL Insight Server] vengono recuperate dall&#39;altro [!DNL Insight Servers] nel cluster.

**Per installare il master[!DNL Insight Server]**

1. Determinare quale computer fungerà da master [!DNL Insight Server].
1. Installate e configurate [!DNL Insight Server] (in genere, un [!DNL Insight Server] FSU) su questo computer come descritto in [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Installate [!DNL Insight] e configurate una connessione al master [!DNL Insight Server] come descritto nella Guida *[!DNL Insight]*utente.
