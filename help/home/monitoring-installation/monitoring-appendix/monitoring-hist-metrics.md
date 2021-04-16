---
description: Di seguito sono elencate le metriche incluse nel profilo di monitoraggio cronologico di Data Workbench e le relative modalità di derivazione.
title: Metriche nel profilo di monitoraggio cronologico di Data Workbench
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
exl-id: 65f0f605-f128-45bb-8f6c-95284b2da740
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 2%

---

# Metriche nel profilo di monitoraggio cronologico di Data Workbench{#metrics-in-the-data-workbench-historical-monitoring-profile}

Di seguito sono elencate le metriche incluse nel profilo di monitoraggio cronologico di Data Workbench e le relative modalità di derivazione.

| **Critici di avviso** | Somma della dimensione Critico avviso per ogni ping. |
|---|---|
| **Avvisi in caso di spegnimento** | Somma della dimensione Avviso verso il basso per ogni ping. |
| **Avvisi** | Somma della dimensione Avviso di avviso per ogni ping. |
| **Tutti i componenti** | Il conteggio dei ping in cui il controllo del successo del componente è uguale a &quot;1&quot; diviso per la metrica dei ping moltiplicata per 100. |
| **A Partire Da Minuti Di Ritardo** | Questa metrica è la somma dei Minuti di ritardo come A per ogni Ping, quindi divisa per la metrica Pings (Ping). |
| **Blocchi** | La somma di uno per ogni blocco. |
| **Blocca tutto** | Tutti i blocchi. |
| **Capacità complessiva** | La metrica Dimensione capacità x 2 più la metrica Riga capacità, divisa per 3. |
| **Riga di capacità** | La somma della dimensione Percentuale riga capacità per ogni Ping divisa per la metrica Pings. |
| **Dimensione della capacità** | La somma della dimensione Percentuale dimensione capacità per ogni Ping, divisa per la metrica Pings. |
| **Comunicazioni** | Il numero di ping in cui il successo del controllo rapido corrisponde a &quot;1&quot;, diviso per la metrica Pings. |
| **Secondi di controllo dettagliati** | La somma della dimensione dei secondi di controllo dettagliati per ogni ping in cui il tipo di ping è &quot;server&quot;, divisa per la metrica Pings. |
| **GigaBytes Dimension** | La somma di Gigabyte di Dimension per ogni Ping, divisa per la metrica Pings. |
| **Disco &quot;x&quot;** | Le metriche del disco vengono calcolate prendendo la somma della percentuale di utilizzo del disco per ogni Ping, divisa per la metrica Pings. |
| **Minuti di sweep stimati** | Questa è la somma dei Dekasecond di sweep stimati per ogni ping, divisi per la metrica Pings in cui Dekaseconds di sweep stimato è maggiore di zero, tutti divisi per 6. |
| **MB di ingresso rapido al minuto** | La somma di MegaBytes Fast Input per Minuto per ogni Ping divisa per il numero di Ping quando MegaBytes Fast Input per Minute è maggiore di zero. |
| **Modalità di ingresso rapido** | Pings in cui la dimensione Modalità di elaborazione è uguale a &quot;Fast input&quot; diviso per Pings. |
| **MegaByte Fast Merge al minuto** | La somma di Megabyte Fast Merge al minuto per ogni Ping, divisa per la metrica Pings. |
| **Modalità Fast Merge** | Pings in cui la modalità di elaborazione è uguale a &quot;fast merge&quot; divisa per la metrica Pings. |
| **Byte campo** | La somma della dimensione Gigabyte di campo per ogni Ping divisa per la metrica Pings. |
| **Load** | La somma della dimensione Media di carico per ogni Ping, divisa per la metrica Pings. |
| **Lettura del registro** | La somma della dimensione Elaborazione della lettura del registro per ogni ping, divisa per la metrica Pings (Ping), divisa per 10. |
| **Pagina di memoria** | La somma della percentuale di file della pagina di memoria per ogni ping, divisa per la metrica Pings. |
| **Memoria fisica** | La somma della dimensione Percentuale fisica memoria per ogni Ping, divisa per la metrica Pings. |
| **Query di memoria** | La somma della percentuale di query di memoria per ogni ping, divisa per la metrica Pings. |
| **Totale memoria GB** | La somma della dimensione Totale MegaByte fisici di memoria per ogni Ping, divisa per la metrica Pings. |
| **Connessioni di rete** | È la somma delle connessioni di rete per ogni ping diviso per la metrica Pings. |
| **Ping x capacità complessiva** | La metrica Pings (Ping) moltiplicata per la metrica Capacity Total (Capacità complessiva). |
| **Millisecondi di latenza del sondaggio** | La somma della dimensione Centisecondi di di latenza del sondaggio per ogni Ping, divisa per la metrica Pings (Ping), tutti moltiplicata per 10. |
| **Query in esecuzione** | La somma di uno per ogni ping in cui i valori di Debugger stimati sono maggiori di &quot;0&quot;, divisa per la metrica Pings in cui Tipo di ping è uguale a &quot;server&quot;. |
| **Secondi di controllo rapido** | La somma dei secondi di controllo rapido per ogni ping in cui il tipo di ping è uguale a &quot;server&quot;, divisa per la metrica Pings. |
| **Righe di output** | La somma della dimensione Righe di output per ciascun ping diviso per la metrica Pings, moltiplicata per 100000. |
| **Modalità in tempo reale** | Il numero di ping in cui la dimensione Modalità di elaborazione è uguale a &quot;tempo reale&quot;, diviso per la metrica Pings, tutto moltiplicato per 100. |
| **Modalità di rielaborazione** | 100 meno il numero di ping in cui la modalità di elaborazione è uguale a &quot;tempo reale&quot; diviso per la metrica Pings, moltiplicato per 100. |
| **In stallo** | La somma della dimensione di elaborazione bloccata nel profilo Insight [Stato profilo](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64). |
| **DB temporaneo** | La somma della percentuale di spazio del database temporaneo per ogni ping, divisa per la metrica Pings. |
| **Transformation (Trasformazione)** | La somma della percentuale di trasformazione per ogni Ping divisa per la metrica Pings (Ping) divisa per 10. |
