---
description: Le istruzioni per l'installazione di un FSU di Insight Server e la configurazione per l'uso amministrativo sono molto simili a quelle per l'installazione e la configurazione di un DPU di Insight Server.
solution: Insight
title: Procedure di installazione per un FSU di Insight Server
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Procedure di installazione per un FSU di Insight Server{#installation-procedures-for-an-insight-server-fsu}

Le istruzioni per l&#39;installazione di un FSU di Insight Server e la configurazione per l&#39;uso amministrativo sono molto simili a quelle per l&#39;installazione e la configurazione di un DPU di Insight Server.

Per *MS System Center Endpoint Protection* nei server Windows 2012, questi eseguibili devono essere aggiunti ai processi **esclusi:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Per installare e configurare un [!DNL Insight Server] FSU, è necessario completare le seguenti attività:

1. Installate i file del [!DNL Insight Server] programma.
1. Installate il certificato [!DNL Insight Server] digitale.
1. Controllare le impostazioni della porta nel [!DNL Communications.cfg] file.
1. Modificate il [!DNL Access Control.cfg] file per consentire l&#39;accesso amministrativo a [!DNL the Server] da [!DNL the Client].
1. Modificare il [!DNL server.address] file per definire il percorso di rete del server.
1. Impostare i parametri di utilizzo della memoria di Windows come descritto.
1. Registratevi [!DNL Insight Server] come servizio Windows come descritto.

   Per istruzioni su come configurare origini dati, autorizzazioni e comunicazioni per un [!DNL Insight Server] FSU, vedere la Guida alla configurazione del *set di dati*.

