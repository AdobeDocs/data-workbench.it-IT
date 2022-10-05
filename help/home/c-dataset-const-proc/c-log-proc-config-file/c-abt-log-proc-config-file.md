---
description: Il file Log Processing.cfg controlla la fase di elaborazione del registro della costruzione del set di dati, durante la quale i dati non ordinati vengono letti dalle origini dati (dette origini log), e i filtri e le trasformazioni vengono applicati ai dati.
title: Informazioni sul file di configurazione dell’elaborazione del registro
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
exl-id: 11ee3298-272d-46c8-bcfe-e485b01606b1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 5%

---

# Informazioni sul file di configurazione dell’elaborazione del registro{#about-the-log-processing-configuration-file}

{{eol}}

Il file Log Processing.cfg controlla la fase di elaborazione del registro della costruzione del set di dati, durante la quale i dati non ordinati vengono letti dalle origini dati (dette origini log), e i filtri e le trasformazioni vengono applicati ai dati.

È necessario modificare le [!DNL Log Processing.cfg] per eseguire una delle seguenti attività di configurazione del set di dati:

* Specifica delle origini di registro. Vedi [Origini del registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* Determinare quali voci di registro inserire nel set di dati durante l’elaborazione del registro. Vedi [Filtri dati](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) e [Condizione voce di registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).

* Abilitazione della suddivisione degli ID di tracciamento con grandi quantità di dati evento. Vedi [Divisione tasti](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).
* Configurazione di un server di Data Workbench da eseguire come unità file server. Vedi [Configurazione di un’unità del file server di Insight Server](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).
* Configurazione di un server di Data Workbench da eseguire come server di normalizzazione centralizzato. Vedi [Configurazione di un’unità del file server di Insight Server](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] i file possono contenere istruzioni aggiuntive per la fase di elaborazione del registro della costruzione del set di dati. Questi file esistono nella directory Dataset\Log Processing per qualsiasi profilo ereditato. In genere definiscono parametri specifici per l&#39;applicazione (ad esempio parametri di configurazione specifici per il Web per l&#39;applicazione Site). Per informazioni su [!DNL Log Processing Dataset Include] file, vedi [Dataset Include Files (File inclusi nel set di dati)](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Per informazioni sui parametri di configurazione specifici per il Web per il sito, consulta [Impostazioni di configurazione per i dati web](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md).
