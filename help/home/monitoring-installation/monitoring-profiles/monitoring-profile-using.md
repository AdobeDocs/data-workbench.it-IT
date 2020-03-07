---
description: Il profilo Stato profilo workbench dati fornisce informazioni aggiornate sullo stato del server workbench dati in base al profilo anziché alle metriche del server o ai dati storici.
solution: Analytics
title: Area di lavoro Stato profilo di Workbench dati
topic: Data workbench
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Area di lavoro Stato profilo di Workbench dati{#data-workbench-profile-status-workspace}

Il profilo Stato profilo workbench dati fornisce informazioni aggiornate sullo stato del server workbench dati in base al profilo anziché alle metriche del server o ai dati storici.

## Stato profilo Workbench dati {#section-65d1fa393cfd450cbacef3cba823fcc1}

Questo profilo di stato fornisce le informazioni correnti sul server del workbench dati, ma non in tempo reale, perché l&#39;agente viene controllato ogni dieci minuti e il reporting include sempre questa latenza di dieci minuti. Più precisamente, i set di dati generati da questo profilo forniscono l&#39;osservazione più recente del server dall&#39;agente, che ha più spesso un periodo predefinito di polling di dieci minuti.

Per ulteriori informazioni di riferimento sulle dimensioni utilizzate nel profilo Stato profilo workbench dati, vedere [Profilo](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64)di stato profilo Insight.

![](assets/Status_General_Status.png)

Questa relazione è più destinata al monitoraggio delle operazioni che non ai componenti o alle specifiche fluttuazioni del traffico.

![](assets/Status_General_page.png)

Questo ci dà il senso di chi è in che modo: Se per un determinato profilo viene visualizzata una velocità di ingresso veloce elevata, il profilo è in modalità di ingresso rapido.

Se la metrica Bloccato è 1, il server è bloccato. Se il valore è 0, il server non viene bloccato.

**Lettura log per carichi batch di grandi dimensioni**

![](assets/Status_General_stalled_log.png)

