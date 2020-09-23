---
description: La funzionalità Ripetitore consente a un FSU di Insight Server di ricevere i dati degli eventi acquisiti dal sensore da una o più origini e di replicare i dati su uno o più FSU di Insight Server che eseguono Insight ServerReplication Service.
solution: Analytics
title: Configurazione della funzionalità Repeater (Ripetitore)
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 9%

---


# Configurazione della funzionalità Repeater (Ripetitore){#configuring-repeater-functionality}

La funzionalità Ripetitore consente a un FSU di Insight Server di ricevere i dati degli eventi acquisiti dal sensore da una o più origini e di replicare i dati su uno o più FSU di Insight Server che eseguono Insight ServerReplication Service.

See [Insight Server Replication Service](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). Questa funzione consente la replica dei dati in strutture ridondanti a scopo di disaster recovery. I server di destinazione agiscono come client di rete, collegandosi all&#39;FSU di origine per richiedere copie dei dati dell&#39;evento da includere in più set di dati.

È possibile utilizzare la funzionalità di ripetizione nelle infrastrutture di rete con più livelli di firewall per ottenere comunicazioni da una porta all’altra tra componenti separati da firewall.

Per informazioni sui requisiti di sistema per l’installazione, la configurazione e il funzionamento [!DNL Repeater]consultate il documento sui requisiti *di sistema* minimi.

Per eseguire l&#39;installazione [!DNL Repeater], è necessario eseguire i passaggi elencati per le due procedure seguenti:

* [Configurazione di un FSU di Insight Server per il Repeater (Ripetitore)](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Configurazione del controllo di accesso per i computer di destinazione](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

Se i firewall di rete consentono l’accesso al [!DNL Repeater] modulo da [!DNL Insight], potete creare una connessione come descritto in [Creazione di una connessione tra Vista e Ripetitore](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118).
