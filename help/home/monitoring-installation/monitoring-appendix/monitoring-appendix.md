---
description: Questo documento descrive i profili con i relativi campi, dimensioni e metriche utilizzati dal profilo di monitoraggio workbench dati.
solution: Analytics
title: Dimensioni e metriche del profilo di Workbench dati
topic: Data workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensioni e metriche del profilo di Workbench dati{#data-workbench-profile-dimensions-and-metrics}

Questo documento descrive i profili con i relativi campi, dimensioni e metriche utilizzati dal profilo di monitoraggio workbench dati.

Per monitorare i server workbench dati, i dati vengono raccolti utilizzando uno script che analizza lo stato dettagliato e al contempo acquisendo informazioni specifiche sul server. Le informazioni sul server Workbench dati vengono quindi trasmesse a una chiamata di tag della pagina per consentire al sensore Workbench dati di raccogliere e salvare in un file VSL.

## Profili utilizzati dal profilo di monitoraggio Workbench dati {#section-b5b1234f55c3407dae8e68b031b7cd7f}

Questi profili forniscono dimensioni e metriche che consentono di visualizzare lo stato del server e i dati sulle prestazioni:

* [Dimensioni nel profilo Stato profilo di Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimensioni nel profilo Stato server Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimensioni nel profilo Storico Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Metriche nel profilo di monitoraggio storico di Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

I profili di stato consentono di visualizzare le prestazioni del workbench dati da un punto di vista operativo. Il profilo Stato **** profilo e il profilo Stato **** server raccolgono i dati dallo Stato dettagliato e dai server workbench dati. Tutti i dati raccolti vengono inseriti nel `cs-uri-query` campo per l&#39;uso.

I profili **** storici consentono di valutare l&#39;impatto delle modifiche alla configurazione e all&#39;hardware utilizzando dati storici. Il profilo storico può essere il più utile perché permette di valutare l&#39;impatto delle modifiche alla configurazione e all&#39;hardware nel tempo.
