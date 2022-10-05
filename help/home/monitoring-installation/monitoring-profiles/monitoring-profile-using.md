---
description: Il profilo Stato profilo di Data Workbench fornisce informazioni correnti sullo stato del server di Data Workbench in base al profilo, anziché alle metriche del server o ai dati storici.
title: Area di lavoro di stato del profilo di Data Workbench
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
exl-id: 40b9b0bf-4fd9-48d8-875b-514921c520cd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 4%

---

# Area di lavoro di stato del profilo di Data Workbench{#data-workbench-profile-status-workspace}

{{eol}}

Il profilo Stato profilo di Data Workbench fornisce informazioni correnti sullo stato del server di Data Workbench in base al profilo, anziché alle metriche del server o ai dati storici.

## Data Workbench stato profilo {#section-65d1fa393cfd450cbacef3cba823fcc1}

Questo profilo di stato fornisce le informazioni correnti sul server di Data Workbench, ma non in tempo reale, perché l’agente viene controllato ogni dieci minuti e il reporting include sempre questa latenza di dieci minuti. Più precisamente, i set di dati generati da questo profilo forniscono l’ultima osservazione del server da parte dell’agente, che spesso ha un periodo di polling predefinito di dieci minuti.

Per ulteriori informazioni di riferimento sulle dimensioni utilizzate nel profilo dello stato del profilo di Data Workbench, consulta [Profilo di stato del profilo di Insight](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64).

![](assets/Status_General_Status.png)

Questa relazione è più destinata al monitoraggio delle operazioni che non a componenti o a specifiche fluttuazioni del traffico.

![](assets/Status_General_page.png)

Questo ci dà un senso di chi è in che modo: Se vediamo un elevato tasso di input rapido per un determinato profilo, il profilo è in modalità Fast Input.

Se la metrica in stallo è 1, il server viene arrestato. Se il valore è 0, il server non viene bloccato.

**Lettura del registro per carichi batch di grandi dimensioni**

![](assets/Status_General_stalled_log.png)
