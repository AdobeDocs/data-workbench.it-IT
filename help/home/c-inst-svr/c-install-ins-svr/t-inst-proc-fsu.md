---
description: Le istruzioni per l’installazione di una FSU di Insight Server e la configurazione per uso amministrativo sono molto simili a quelle per l’installazione e la configurazione di una DPU di Insight Server.
title: Procedure di installazione per una FSU di Insight Server
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Procedure di installazione per una FSU di Insight Server{#installation-procedures-for-an-insight-server-fsu}

Le istruzioni per l’installazione di una FSU di Insight Server e la configurazione per uso amministrativo sono molto simili a quelle per l’installazione e la configurazione di una DPU di Insight Server.

Per *MS System Center Endpoint Protection* nei server Windows 2012, questi eseguibili devono essere aggiunti ai **Processi esclusi:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Per installare e configurare una FSU [!DNL Insight Server], è necessario completare le seguenti attività:

1. Installa i file di programma [!DNL Insight Server].
1. Installa il certificato digitale [!DNL Insight Server].
1. Controlla le impostazioni della porta nel file [!DNL Communications.cfg].
1. Modifica il file [!DNL Access Control.cfg] per consentire l&#39;accesso amministrativo a [!DNL the Server] da [!DNL the Client].
1. Modifica il file [!DNL server.address] per definire il percorso di rete del server.
1. Impostare i parametri di utilizzo della memoria di Windows come descritto.
1. Registrati [!DNL Insight Server] come servizio Windows come descritto.

   Per istruzioni su come configurare origini dati, autorizzazioni e comunicazioni per una FSU [!DNL Insight Server], consulta la *Guida alla configurazione del set di dati*.
