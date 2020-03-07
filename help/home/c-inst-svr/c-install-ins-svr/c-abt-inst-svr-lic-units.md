---
description: Insight Server è disponibile in due tipi di licenza.
solution: Insight
title: Informazioni sulle unità di licenza di Insight Server
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informazioni sulle unità di licenza di Insight Server{#about-insight-server-license-units}

Insight Server è disponibile in due tipi di licenza.

Di seguito sono elencati i due tipi di licenza:

* [Unità di elaborazione dati (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [File Server Unit (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Unità di elaborazione dati (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Questo tipo di dati [!DNL Insight Server] può elaborare, memorizzare e distribuire dati da un set di dati Adobe. È possibile memorizzare i file di registro che contengono i dati di origine da cui il set di dati è costruito, oppure ricevere tali dati da un&#39;unità [!DNL Insight Server] FSU (File Server Unit). Un DPU è il tipo di [!DNL Insight Server] con cui [!DNL Insight] e [!DNL Report] i client interagiscono direttamente.

Se state installando un [!DNL Insight Server] DPU, consultate Procedure di [installazione per un DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)server di Insight.

## File Server Unit (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Questo tipo di server è configurato per ricevere e memorizzare i dati evento da una o più istanze di replica dei dati dell&#39;evento ( [!DNL Sensor] funzionalità fornita con una licenza per l&#39;uso speciale) e per trasmettere i dati a una o più unità di elaborazione [!DNL Repeater] [!DNL Insight Server] dati (DPU) per la creazione di set di dati Adobe. I DPU comunicano con un FSU utilizzando un protocollo che ottimizza il trasferimento dei dati dell&#39;evento al DPU ed è notevolmente più veloce rispetto alla gestione dei file di registro sui normali file server. L&#39;utilizzo di un FSU riduce inoltre i costi hardware consentendo la memorizzazione dei dati del registro su hardware di storage a basso costo e riduce la complessità amministrativa consentendo a più utenti [!DNL Sensors] di puntare a un unico [!DNL Insight Server].

Se state installando un [!DNL Insight Server] FSU, consultate Procedure di [installazione per un FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)di Insight Server.
