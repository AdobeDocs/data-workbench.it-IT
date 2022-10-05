---
description: Procedura per installare e configurare il software del server di rapporto.
title: Panoramica dell’installazione
uuid: ffc72aa1-98d8-41dc-b4e5-6f70ff43430e
exl-id: 4ddc0761-a999-49ed-b0e4-12cf34e2688c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 8%

---

# Panoramica dell’installazione{#installation-overview}

{{eol}}

Procedura per installare e configurare il software del server di rapporto.

I seguenti compiti devono essere completati in ordine:

1. Installare i file del programma del server di rapporto.
1. Scarica e installa il certificato digitale del server di rapporto. Vedi [Download e installazione del certificato digitale](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
1. Configurare la connessione tra Report Server e il server di Data Workbench (InsightServer64.exe). Vedi [Configurazione della connessione a Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c).
1. Aggiorna il server di rapporto con un file della lingua (file .zbin).

   Vedi [Aggiorna il server di rapporto con un file della lingua (file .zbin)](../../../home/c-rpt-oview/c-inst-rpt/c-zbin-file-update.md#concept-5637a8f52b7643759e423c2068b4126b). 1. Aggiornare il file di controllo di accesso sul computer server di Data Workbench per consentire a Report Server di accedere al server di Data Workbench. Vedi [Abilitazione dell’accesso a Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-en-acc-ins-svr.md#task-e7b95cf9cb194842ad72fa534c56c3cc).
1. Modificare il file di comunicazione nel computer server di Data Workbench principale per visualizzare lo stato del server di rapporto nel [!DNL Master Server Detailed Status] interfaccia. Vedi [Configurazione di Insight Server per visualizzare lo stato del server per il rapporto](../../../home/c-rpt-oview/c-inst-rpt/t-display-svr-st-rpt.md#task-a14d096f85924d9b93eef950591f93a8).
1. Registra report come servizio Windows. Vedi [Registrazione del report come servizio Windows](../../../home/c-rpt-oview/c-inst-rpt/t-reg-rpt-win-svc.md#task-a8762d7818ed4cfd87e616db6a68b3a6).
