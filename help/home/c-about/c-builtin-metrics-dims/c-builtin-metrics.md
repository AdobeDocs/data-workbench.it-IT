---
description: Data Workbench include metriche integrate.
title: Metriche incorporate
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
exl-id: a8a2a8dd-dc13-4eb3-92ce-09f02252ecf0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 1%

---

# Metriche incorporate{#built-in-metrics}

Data Workbench include metriche integrate.

Nella tabella seguente sono elencate le metriche integrate disponibili per Data Workbench:

| Metrica incorporata | Descrizione |
|---|---|
| A partire da | A partire dall’ora del set di dati in intervalli di 100 nanosecondi dal 1° gennaio 1600 00:00 UTC. La marca temporale A è l’ora più recente nel set di dati per cui tutti i dati sono stati definitivamente elaborati. |
| Byte di registro letti | La quantità totale di dati compressi (in byte) elaborati finora durante la fase di elaborazione del registro. |
| Totale byte di registro | La quantità totale di dati compressi (in byte) nei file di registro che corrispondono ai criteri delle origini di registro configurate e all&#39;intervallo di date di inizio e fine del set di dati. Se l’elaborazione del registro viene sospesa nel file di configurazione della Modalità di elaborazione del registro, il totale dei byte del registro sarà lo stesso dei byte di registro letti. |
| Avanzamento dell’elaborazione del registro | Percentuale di completamento della fase di elaborazione del registro dell’elaborazione dei dati di Insight Server. |
| Totale voci di registro decodificate | Numero di voci nei file di registro decodificate correttamente come parte della fase di elaborazione del registro dell’elaborazione dei dati di Insight Server. |
| Totale voci di registro filtrate | Il numero di voci nei file di log che dopo la decodifica sono state accettate dal filtro robot e dalle condizioni di ingresso registro e da altri filtri applicati come parte della fase di elaborazione del log dell&#39;elaborazione dati Insight Server. |
| Totale voci di registro | Il numero di voci nei file di registro che sono state finora elaborate dalla fase di elaborazione del registro dell’elaborazione dei dati di Insight Server. |
| Totale voci di registro elaborate | Il numero di voci di registro filtrate incorporate nel set di dati di Adobe. |
| Avanzamento trasformazione | Percentuale di completamento della fase di trasformazione dell’elaborazione dati di Insight Server. |
| Byte di registro non compressi letti | La quantità totale di dati non compressi (in byte) elaborati finora durante la fase di elaborazione del registro. |
