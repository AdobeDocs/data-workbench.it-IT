---
description: Il file Log Processing.cfg controlla la fase di elaborazione del log della costruzione del set di dati, durante la quale i dati non ordinati vengono letti dalle origini dati (denominate "origini log"), e filtri e trasformazioni vengono applicati ai dati.
solution: Analytics
title: Informazioni sul file di configurazione dell'elaborazione del registro
topic: Data workbench
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Informazioni sul file di configurazione dell&#39;elaborazione del registro{#about-the-log-processing-configuration-file}

Il file Log Processing.cfg controlla la fase di elaborazione del log della costruzione del set di dati, durante la quale i dati non ordinati vengono letti dalle origini dati (denominate &quot;origini log&quot;), e filtri e trasformazioni vengono applicati ai dati.

È necessario modificare il [!DNL Log Processing.cfg] file per eseguire una delle seguenti attività di configurazione del dataset:

* Specifica delle origini di registro. Vedere [Origini](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md)di registro.
* Determinazione delle voci di registro inserite nel dataset durante l&#39;elaborazione del registro. Consulta Filtri [](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) dati e Condizione [di immissione](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)registro.

* Abilitazione della divisione degli ID di tracciamento con grandi quantità di dati evento. Vedere [Divisione](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)tasti.
* Configurazione di un server workbench dati da eseguire come unità del file server. Consultate [Configurazione di un&#39;unità](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)del file server di Insight Server.
* Configurazione di un server workbench dati da eseguire come server di normalizzazione centralizzato. Consultate [Configurazione di un&#39;unità](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)del file server di Insight Server.

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] i file possono contenere istruzioni aggiuntive per la fase di elaborazione del log della costruzione del dataset. Questi file esistono nella directory Dataset\Log Processing per qualsiasi profilo ereditato. In genere definiscono parametri specifici per le applicazioni (ad esempio parametri di configurazione specifici per il Web per l&#39;applicazione Site). Per informazioni sui [!DNL Log Processing Dataset Include] file, vedere [Set di dati Includi file](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Per informazioni sui parametri di configurazione specifici per il Web per il sito, vedere Impostazioni [di configurazione per i dati](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md)Web.

