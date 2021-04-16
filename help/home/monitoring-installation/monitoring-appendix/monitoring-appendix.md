---
description: Questo documento descrive i profili con i relativi campi, dimensioni e metriche utilizzati dal profilo di monitoraggio di Data Workbench.
title: Dimensioni e metriche del profilo di Data Workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Dimensioni e metriche del profilo di Data Workbench{#data-workbench-profile-dimensions-and-metrics}

Questo documento descrive i profili con i relativi campi, dimensioni e metriche utilizzati dal profilo di monitoraggio di Data Workbench.

Per monitorare i server di Data Workbench, i dati vengono raccolti utilizzando uno script che analizza lo stato dettagliato e acquisisce al contempo informazioni specifiche sul server. Le informazioni sul server di Data Workbench vengono quindi passate a una chiamata tag di pagina affinché Data Workbench Sensor raccolga e salvi in un file VSL.

## Profili utilizzati dal profilo di monitoraggio Data Workbench {#section-b5b1234f55c3407dae8e68b031b7cd7f}

Questi profili forniscono dimensioni e metriche che ti consentono di visualizzare i dati sullo stato e sulle prestazioni del server:

* [Dimension nel profilo dello stato del profilo di Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimension nel profilo dello stato di Insight Server](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimension nel profilo di Insight Historic](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Metriche nel profilo di monitoraggio cronologico di Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

I profili di stato ti consentono di visualizzare le prestazioni di Data Workbench da un punto di vista operativo. Il profilo **Stato profilo** e il profilo **Stato server** raccolgono i dati dallo stato dettagliato e dai server di Data Workbench. Tutti i dati raccolti vengono inseriti nel campo `cs-uri-query` da utilizzare.

I **Profili storici** consentono di valutare l&#39;impatto delle modifiche di configurazione e hardware utilizzando i dati storici. Il profilo storico può essere il più utile perché consente di valutare l’impatto delle modifiche alla configurazione e all’hardware nel tempo.
