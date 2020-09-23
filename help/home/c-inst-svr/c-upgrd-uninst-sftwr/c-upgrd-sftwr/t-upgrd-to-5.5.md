---
description: Aggiornamento dei componenti server per Data Workbench 6.1 dall’installazione 5.4.
solution: Analytics
title: Aggiornamento a DWB Server da 5.4 a 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---


# Aggiornamento del server DWB: da 5.4 a 5.5{#dwb-server-upgrade-to}

Aggiornamento dei componenti server per Data Workbench 6.1 dall’installazione 5.4.

Di conseguenza, l&#39;aggiornamento da [!DNL Insight] 5.4 a [!DNL Insight] 5.5 è relativamente semplice.

Puoi anche effettuare l’aggiornamento direttamente da [!DNL Insight] 5.3 a [!DNL Insight] 5.5, seguendo la procedura indicata di seguito. Accertatevi di eseguire tutte le attività di aggiornamento elencate nella sezione [Aggiornamento da Insight 5.4 a 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) e nella sezione [Aggiornamento da Insight 5.4 a 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) .

1. Arrestate i [!DNL Insight Server] servizi su tutti i server del cluster, ad eccezione di [!DNL Insight Master Server].

   1. Copiare i nuovi [!DNL ReportServer.exe] e [!DNL Insight.exe] file nella cartella Software\Insight.

   1. Una volta aggiornato il [!DNL Insight] client, copiate i file [!DNL InsightServer.exe] e [!DNL InsightServer64.exe] nella cartella \Bin.

   1. Attendi che [!DNL Insight Master Server] inizi, quindi verifica la versione in esecuzione tramite la [!DNL Connections] visualizzazione.

1. Nel cluster [!DNL Master Server] nel [!DNL Insight] client:

   1. Creare una copia locale del [!DNL Base] profilo esistente e rinominarlo (ad esempio, BaseBackup).
   1. Copiate il nuovo [!DNL Base] profilo nella cartella Profili.
   1. Ripetete questi due passaggi per la cartella Transform.

1. Copiate la cartella Scripts dal pacchetto del server [!DNL Master Server] nella directory di installazione del server.
1. Copiare il [!DNL Terrain Images.cfg.off] file nella cartella Components (Componenti) del [!DNL Master Server].
   **Per aggiornare il software client da[!DNL Insight]5.4 a 5.5**

Nel [!DNL Insight.cfg] file, accertatevi che l&#39;impostazione Aggiornamento software sia impostata su TRUE.
