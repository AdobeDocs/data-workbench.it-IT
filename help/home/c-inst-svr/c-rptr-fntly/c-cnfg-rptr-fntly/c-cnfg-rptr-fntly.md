---
description: La funzionalità Repeater (Ripetitore) consente a una FSU di Insight Server di ricevere i dati degli eventi acquisiti dal sensore da una o più origini e di replicarli in una o più FSU di Insight Server che eseguono il servizio di replica di Insight Server.
title: Configurazione della funzionalità Repeater (Ripetitore)
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
exl-id: 61b70772-07fb-4963-b09f-6b2cf97b01a1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 9%

---

# Configurazione della funzionalità Repeater (Ripetitore){#configuring-repeater-functionality}

La funzionalità Repeater (Ripetitore) consente a una FSU di Insight Server di ricevere i dati degli eventi acquisiti dal sensore da una o più origini e di replicarli in una o più FSU di Insight Server che eseguono il servizio di replica di Insight Server.

Consulta [Servizio di replica di Insight Server](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). Questa funzione consente la replica dei dati in impianti ridondanti a scopo di disaster recovery. I server di destinazione fungono da client di rete e si connettono alla FSU di origine per richiedere copie dei dati dell’evento da includere in più set di dati.

È possibile utilizzare la funzionalità di ripetizione nelle infrastrutture di rete con più livelli di firewall per ottenere comunicazioni da una porta all’altra tra i componenti separati da firewall.

Per informazioni sui requisiti di sistema per l&#39;installazione, la configurazione e il funzionamento [!DNL Repeater], vedere il documento *Requisiti minimi di sistema* .

Per installare [!DNL Repeater], è necessario eseguire i passaggi elencati per le due procedure seguenti:

* [Configurazione di un FSU di Insight Server per il Repeater (Ripetitore)](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Configurazione del controllo di accesso per i computer di destinazione](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

Se i firewall di rete consentono l’accesso a [!DNL Repeater] da [!DNL Insight], puoi creare una connessione come descritto in [Creazione di una connessione tra Insight e Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118).
