---
description: Di seguito sono elencate le metriche incluse nel workbench dati Historical Monitoring Profile (Profilo di monitoraggio storico del workbench dati) e le relative modalità di derivazione.
solution: Analytics
title: Metriche nel profilo di monitoraggio storico Workbench dati
topic: Data workbench
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Metriche nel profilo di monitoraggio storico Workbench dati{#metrics-in-the-data-workbench-historical-monitoring-profile}

Di seguito sono elencate le metriche incluse nel workbench dati Historical Monitoring Profile (Profilo di monitoraggio storico del workbench dati) e le relative modalità di derivazione.

| **Critici di avviso** | La somma della dimensione Critico avviso per ogni ping. |
|---|---|
| **Avvisi** | La somma della dimensione Alert Down (Avviso verso il basso) per ogni ping. |
| **Avvisi avvisi** | La somma della dimensione Avviso avviso per ogni ping. |
| **Tutti i componenti** | Il numero di ping in cui il controllo del successo del componente è uguale a &quot;1&quot; diviso per la metrica Pings moltiplicato per 100. |
| **A Partire Da Minuti Di Ritardo** | Questa metrica è la somma dei minuti di ritardo come per ogni Ping, quindi divisa per la metrica Pings. |
| **Blocchi** | La somma di uno per ogni blocco. |
| **Blocca tutto** | Tutti gli isolati. |
| **Capacità** | La metrica Dimensione capacità è pari a 2 più la metrica Riga capacità, divisa per 3. |
| **Riga di capacità** | La somma della dimensione Percentuale riga capacità per ogni Ping divisa per la metrica Pings. |
| **Dimensione capacità** | La somma della dimensione Percentuale dimensione capacità per ogni Ping, divisa per la metrica Pings. |
| **Comunicazioni** | Il numero di ping in cui il successo del controllo rapido corrisponde a &quot;1&quot;, diviso per la metrica Pings. |
| **Secondi controllo dettagliati** | La somma della dimensione Secondi controllo dettagliati per ogni Ping in cui il tipo di ping è &quot;server&quot;, divisa per la metrica Pings. |
| **GigaByte dimensione** | La somma di Gigabyte di dimensione per ciascun Ping, divisa per la metrica Pings. |
| **Disco &quot;x&quot;** | Le metriche del disco vengono calcolate prendendo la somma della percentuale di utilizzo del disco per ogni Ping, divisa per la metrica Pings. |
| **Minuti di sweep stimati** | Questa è la somma dei Dekaseconds Sweep Estimated Dekaseconds per ogni Ping, divisi per la metrica Pings dove Dekaseconds Sweep Estimated è maggiore di zero, tutti divisi per 6. |
| **MB di ingresso rapido al minuto** | La somma di MegaBytes di Input Rapido per Minuto per ciascun Ping divisa per il numero di Pings quando MegaBytes di Input Rapido per Minuto è maggiore di zero. |
| **Modalità di ingresso rapido** | Pings in cui la dimensione Modalità di elaborazione è uguale a &quot;Input rapido&quot; diviso per Pings. |
| **Unione veloce megaByte al minuto** | La somma di Megabyte di Unione veloce al minuto per ogni Ping, divisa per la metrica Pings. |
| **Modalità Unione Rapida** | Pings in cui Modalità di elaborazione è uguale a &quot;unione rapida&quot; divisa per la metrica Pings. |
| **GigaBytes campo** | La somma della dimensione Gigabyte di campo per ogni Ping divisa per la metrica Pings. |
| **Caricamento** | La somma della dimensione Media del carico per ogni Ping, divisa per la metrica Pings. |
| **Lettura log** | La somma della dimensione Elaborazione lettura log per ogni Ping, divisa per la metrica Pings, divisa per 10. |
| **Pagina memoria** | La somma della percentuale di file della pagina di memoria per ogni Ping, divisa per la metrica Pings. |
| **Memoria fisica** | La somma della dimensione Percentuale fisica memoria per ogni Ping, divisa per la metrica Pings. |
| **Query di memoria** | La somma della percentuale di query di memoria per ogni ping, divisa per la metrica Pings. |
| **Totale memoria GB** | La somma della dimensione Totale MegaByte fisici memoria per ogni ping, divisa per la metrica Pings. |
| **Connessioni di rete** | È la somma delle connessioni di rete per ogni ping divisa per la metrica Pings. |
| **Pings x Capacità Totale** | La metrica Pings moltiplicata per la metrica Capacità complessiva. |
| **Latenza sondaggio millisecondi** | La somma della dimensione Centesimi di secondo di latenza del sondaggio per ogni ping, divisa per la metrica Pings, moltiplicata per 10. |
| **Query in esecuzione** | La somma di uno per ogni Ping in cui Dekaseconds Sweep Estimated è maggiore di &quot;0&quot;, divisa per la metrica Pings in cui Tipo Ping è uguale a &quot;server&quot;. |
| **Secondi controllo rapido** | La somma dei secondi di controllo rapido per ogni ping in cui il tipo di ping è uguale a &quot;server&quot;, divisa per la metrica Pings. |
| **Righe di output** | La somma della dimensione Righe di output per ciascun ping divisa per la metrica Pings, moltiplicata per 100000. |
| **Modalità Real Time** | Il numero di ping la cui dimensione Modalità di elaborazione è uguale a &quot;tempo reale&quot;, diviso per la metrica Pings, tutti moltiplicati per 100. |
| **Modalità di rielaborazione** | 100 meno il numero di ping in cui la modalità di elaborazione è uguale a &quot;tempo reale&quot; diviso per la metrica Pings, moltiplicato per 100. |
| **Bloccato** | La somma della dimensione Elaborazione bloccata nel profilo Stato [](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64) profilo di Insight. |
| **DB temporaneo** | La somma della percentuale di spazio DB temporaneo per ogni Ping, divisa per la metrica Pings. |
| **Trasformazione** | La somma della percentuale di trasformazione per ogni Ping divisa per la metrica Pings divisa per 10. |

