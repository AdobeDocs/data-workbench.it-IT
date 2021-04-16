---
description: Aggiornamento dei componenti server per Data Workbench 6.1 dall’installazione 5.4.
title: Aggiornamento del server DWB da 5.4 a 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# Aggiornamento del server DWB: da 5.4 a 5.5{#dwb-server-upgrade-to}

Aggiornamento dei componenti server per Data Workbench 6.1 dall’installazione 5.4.

Di conseguenza, l&#39;aggiornamento da [!DNL Insight] 5.4 a [!DNL Insight] 5.5 è relativamente semplice.

Puoi anche eseguire l’aggiornamento direttamente da [!DNL Insight] 5.3 a [!DNL Insight] 5.5 seguendo i passaggi seguenti. Assicurati di eseguire tutte le attività di aggiornamento elencate nella sezione [Aggiornamento da Insight 5.4 a 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) e nella sezione [Aggiornamento da Insight 5.4 a 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) .

1. Arresta i servizi [!DNL Insight Server] su tutti i server del cluster ad eccezione di [!DNL Insight Master Server].

   1. Copia i nuovi file [!DNL ReportServer.exe] e [!DNL Insight.exe] nella cartella Software\Insight .

   1. Dopo l&#39;aggiornamento del client [!DNL Insight], copia i file [!DNL InsightServer.exe] e [!DNL InsightServer64.exe] nella cartella \Bin.

   1. Attendi l’avvio di [!DNL Insight Master Server], quindi verifica la versione in esecuzione tramite la visualizzazione [!DNL Connections].

1. Nel client [!DNL Master Server] del cluster nel [!DNL Insight] :

   1. Crea una copia locale del profilo [!DNL Base] esistente e rinominalo (ad esempio, BaseBackup).
   1. Copia il nuovo profilo [!DNL Base] nella cartella Profiles .
   1. Ripetere questi due passaggi per la cartella Trasforma.

1. Copia la cartella Script dal pacchetto server nella directory di installazione del server [!DNL Master Server].
1. Copia il file [!DNL Terrain Images.cfg.off] nella cartella Components della cartella [!DNL Master Server].
   **Per aggiornare il software client da  [!DNL Insight] 5.4 a 5.5**

Nel file [!DNL Insight.cfg], accertati che l&#39;impostazione Aggiorna software sia impostata su TRUE.
