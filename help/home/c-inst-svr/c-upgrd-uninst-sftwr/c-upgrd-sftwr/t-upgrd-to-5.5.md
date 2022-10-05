---
description: Aggiornamento dei componenti server per Data Workbench 6.1 dall’installazione 5.4.
title: Aggiornamento del server DWB da 5.4 a 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# Aggiornamento del server DWB: da 5.4 a 5.5{#dwb-server-upgrade-to}

{{eol}}

Aggiornamento dei componenti server per Data Workbench 6.1 dall’installazione 5.4.

Di conseguenza, l&#39;aggiornamento da [!DNL Insight] da 5.4 a [!DNL Insight] 5.5 è relativamente semplice.

Puoi anche effettuare l&#39;aggiornamento direttamente da [!DNL Insight] Da 5,3 a [!DNL Insight] 5.5 seguendo i passaggi seguenti. Assicurati di eseguire tutte le attività di aggiornamento elencate in [Aggiornamento da Insight 5.4 a 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) la sezione [Aggiornamento da Insight 5.4 a 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) sezione .

1. Interrompi [!DNL Insight Server] servizi su tutti i server del cluster, ad eccezione dei [!DNL Insight Master Server].

   1. Copia il nuovo [!DNL ReportServer.exe] e [!DNL Insight.exe] nella cartella Software\Insight.

   1. Dopo la [!DNL Insight] il client è stato aggiornato, copia il [!DNL InsightServer.exe] e [!DNL InsightServer64.exe] nella cartella \Bin.

   1. Attendi la [!DNL Insight Master Server] per iniziare, verifica la versione in esecuzione tramite il [!DNL Connections] visualizzazione.

1. Sul cluster [!DNL Master Server] in [!DNL Insight] client:

   1. Crea una copia locale dell&#39;esistente [!DNL Base] e rinominarlo (ad esempio, BaseBackup).
   1. Copia il nuovo [!DNL Base] nella cartella Profiles .
   1. Ripetere questi due passaggi per la cartella Trasforma.

1. Copia la cartella Script dal pacchetto del server nel [!DNL Master Server] nella directory di installazione del server.
1. Copia il [!DNL Terrain Images.cfg.off] nella cartella Components del [!DNL Master Server].
   **Per aggiornare il software client da [!DNL Insight] Da 5.4 a 5.5**

In [!DNL Insight.cfg] file, assicurati che l&#39;impostazione Aggiorna software sia impostata su TRUE.
