---
description: Il workbench dati include metriche integrate.
solution: Analytics
title: Metriche integrate
topic: Data workbench
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Metriche integrate{#built-in-metrics}

Il workbench dati include metriche integrate.

Nella tabella seguente sono elencate le metriche integrate disponibili per il workbench dati:

| Metrica incorporata | Descrizione |
|---|---|
| A | Data e ora del set di dati in intervalli di 100 nanosecondi dal 1 gennaio 1600 00:00 UTC. La marca temporale Come di è l&#39;ultima ora del dataset per il quale tutti i dati sono stati elaborati. |
| Byte di registro letti | La quantità totale di dati compressi (in byte) elaborati finora durante la fase di elaborazione del registro. |
| Totale byte di registro | La quantità totale di dati compressi (in byte) nei file di registro che corrispondono ai criteri delle origini di registro configurate e all&#39;intervallo di date di inizio e fine del dataset. Se l&#39;elaborazione del registro viene messa in pausa nel file di configurazione della modalità di elaborazione del registro, il totale dei byte del registro sarà uguale a quello dei byte di registro letti. |
| Avanzamento elaborazione log | Percentuale di completamento della fase di elaborazione del registro dell&#39;elaborazione dati di Insight Server. |
| Totale voci di registro decodificate | Il numero di voci nei file di registro che sono state decodificate come parte della fase di elaborazione del registro dell&#39;elaborazione dei dati di Insight Server. |
| Totale voci di registro filtrate | Il numero di voci nei file di registro che dopo la decodifica sono state accettate dal filtro robot, dalle condizioni di ingresso del registro e da altri filtri applicati come parte della fase di elaborazione del log dell&#39;elaborazione dei dati di Insight Server. |
| Totale voci di registro | Numero di voci nei file di registro che sono state finora elaborate dalla fase di elaborazione del registro dell&#39;elaborazione dei dati di Insight Server. |
| Totale voci di registro elaborate | Numero di voci di registro filtrate incorporate nel set di dati di Adobe. |
| Avanzamento trasformazione | Percentuale di completamento della fase di trasformazione dell&#39;elaborazione dati di Insight Server. |
| Byte di registro non compressi letti | La quantità totale di dati non compressi (in byte) elaborati finora durante la fase di elaborazione del registro. |

