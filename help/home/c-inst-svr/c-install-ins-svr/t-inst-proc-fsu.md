---
description: Le istruzioni per l’installazione di una FSU di Insight Server e la configurazione per uso amministrativo sono molto simili a quelle per l’installazione e la configurazione di una DPU di Insight Server.
title: Procedure di installazione per una FSU di Insight Server
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Procedure di installazione per una FSU di Insight Server{#installation-procedures-for-an-insight-server-fsu}

{{eol}}

Le istruzioni per l’installazione di una FSU di Insight Server e la configurazione per uso amministrativo sono molto simili a quelle per l’installazione e la configurazione di una DPU di Insight Server.

Per *Endpoint Protection di Microsoft System Center* nei server Windows 2012, questi eseguibili devono essere aggiunti al **Processi esclusi:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Per installare e configurare un [!DNL Insight Server] FSU, è necessario completare le seguenti attività:

1. Installa il [!DNL Insight Server] file di programma.
1. Installa il [!DNL Insight Server] certificato digitale.
1. Controlla le impostazioni della porta nella [!DNL Communications.cfg] file.
1. Modifica la [!DNL Access Control.cfg] file per consentire l&#39;accesso amministrativo a [!DNL the Server] da [!DNL the Client].
1. Modifica la [!DNL server.address] per definire il percorso di rete del server.
1. Impostare i parametri di utilizzo della memoria di Windows come descritto.
1. Registro [!DNL Insight Server] come servizio Windows, come descritto.

   Per istruzioni su come configurare origini dati, autorizzazioni e comunicazioni per un [!DNL Insight Server] FSU, vedere *Guida alla configurazione del set di dati*.
