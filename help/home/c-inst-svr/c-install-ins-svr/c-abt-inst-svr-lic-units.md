---
description: Insight Server è disponibile in due tipi di licenza.
title: Informazioni sulle unità di licenza di Insight Server
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---

# Informazioni sulle unità di licenza di Insight Server{#about-insight-server-license-units}

Insight Server è disponibile in due tipi di licenza.

Di seguito sono elencati i due tipi di licenza:

* [Unità di elaborazione dati (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [File Server Unit (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Unità di elaborazione dati (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Questo tipo di [!DNL Insight Server] può elaborare, memorizzare e distribuire dati da un set di dati di Adobe. Facoltativamente può memorizzare i file di registro che contengono i dati di origine da cui è costruito il set di dati, o può ricevere tali dati da una [!DNL Insight Server] File Server Unit (FSU). Una DPU è il tipo di [!DNL Insight Server] con cui i client [!DNL Insight] e [!DNL Report] interagiscono direttamente.

Se stai installando una DPU [!DNL Insight Server], consulta [Procedure di installazione per una DPU di Insight Server](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## File Server Unit (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Questo tipo di server è configurato per ricevere e memorizzare i dati evento da una o più [!DNL Sensor] istanze di replica dei dati dell&#39;evento ( [!DNL Repeater] funzionalità fornita con una licenza d&#39;uso speciale) e per inviare i dati a una o più unità di elaborazione dei dati (DPU, Data Processing Units) per la costruzione di set di dati di Adobe. [!DNL Insight Server] Le DPU comunicano con una FSU utilizzando un protocollo che ottimizza il trasferimento dei dati dell’evento alla DPU ed è notevolmente più veloce rispetto alla manutenzione dei file di registro sui normali file server. L&#39;utilizzo di una FSU riduce inoltre i costi dell&#39;hardware consentendo la memorizzazione dei dati di registro su hardware di storage a basso costo e riducendo la complessità amministrativa consentendo a più [!DNL Sensors] di puntare a un singolo [!DNL Insight Server].

Se stai installando una FSU [!DNL Insight Server], consulta [Procedure di installazione per una FSU di Insight Server](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
