---
description: Le dimensioni seguenti sono disponibili per l’utilizzo nel profilo dello stato del server di Data Workbench.
title: Dimensioni nel profilo dello stato del server di Data Workbench
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Dimensioni nel profilo dello stato del server di Data Workbench{#dimensions-in-the-data-workbench-server-status-profile}

Le dimensioni seguenti sono disponibili per l’utilizzo nel profilo dello stato del server di Data Workbench.

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Server</b> </td> 
   <td colname="col2"> Costruita dal campo x-trackingid, questa dimensione numerabile rappresenta i server che attualmente eseguono Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versione agente</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(af) viene utilizzato per questo Dimension semplice. Si tratta del valore Ultimo non vuoto per un server. Viene visualizzata la data e l’ora della build per le versioni dell’agente di monitoraggio in esecuzione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Qualsiasi rielaborazione del profilo</b> </td> 
   <td colname="col2"> Il campo cs-uri-query(aa) viene utilizzato per questo Dimension numerico, è il valore dell'ultima riga per un determinato server, condizionale su cs-uri-query(k) non è vuoto. Questa dimensione viene utilizzata per indicare se eventuali profili vengono rielaborati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale riga capacità</b> </td> 
   <td colname="col2"> Il campo cs-uri-query(r) viene utilizzato per questo Dimension numerico, è il valore dell'ultima riga per un determinato server, condizionale su cs-uri-query(k) non è vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale di capacità</b> </td> 
   <td colname="col2"> Il campo cs-uri-query(n) viene utilizzato per questo Dimension numerico, è il valore dell'ultima riga per un determinato server, condizionale su cs-uri-query(k) non è vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nome comune</b> </td> 
   <td colname="col2"> Il campo sc-ur-query(am) viene utilizzato per questo Dimension semplice, è il valore dell'ultimo valore non vuoto per un determinato server. Visualizza il nome comune dei server monitorati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Controllo componente completato</b> </td> 
   <td colname="col2"> Il campo cs-uri-query(v) viene utilizzato per questo Dimension semplice, è il valore dell'ultima riga per un determinato server. Questa dimensione controlla i componenti del server per verificarne il corretto funzionamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Componenti in errore</b> </td> 
   <td colname="col2"> Una trasformazione Crossrows prende il valore Last Row del cs-uri-query(ao) e lo copia nel campo x-components-in-error. Questa dimensione Da molti a molti visualizza tutti i componenti in errore sui server monitorati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ambiente</b> </td> 
   <td colname="col2">Il valore cs-uri-query(c) viene utilizzato per l'ID ambiente. L’ultima riga per un blocco viene utilizzata come valore per la dimensione. Questo Dimension semplice visualizza l'ambiente in cui i server sono in esecuzione (purché configurato correttamente). <p><p>Nota:  Questa dimensione è impostata in insight_monitor_agent.cfg. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dekaseconds di sweep stimati</b> </td> 
   <td colname="col2"> Il campo x-Estimated-sweep-dekaseconds viene utilizzato in questo Dimension numerico. Si tratta del tempo di sweep stimato dei server diviso per dieci (risoluzione ridotta della misurazione di sweep per rendere la dimensione più ragionevole). <p><p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> Per questa dimensione viene utilizzato il valore cs-uri-query(b). Il valore della dimensione Semplice è l’ultima riga per un blocco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ultima chiamata</b> </td> 
   <td colname="col2"> x-last-ping è x-unixtime divide per 10 (per adattarsi ai vincoli di dimensione delle dimensioni numeriche). Ultimo ping è l'ultima riga per un determinato blocco e rappresenta l'ultima volta che l'agente di monitoraggio ha registrato l'integrità del sistema. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Media del carico</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per il valore cs-uri-query(i) di un server specificato. È condizionato se cs-uri-query(k) non è vuoto. Questa dimensione viene utilizzata per calcolare il carico medio sui server del sistema monitorato. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale file di pagina di memoria</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per un valore cs-uri-query(o) di un server specificato. È condizionato se cs-uri-query(k) non è vuoto. Questa dimensione viene utilizzata per calcolare la percentuale di utilizzo della memoria del file di pagina. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaByte fisici memoria totale</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per un valore cs-uri-query(ag) di un server specificato. È condizionato se cs-uri-query(k) non è vuoto. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale fisica memoria</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per un valore cs-uri-query(ag) di un server specificato. È condizionato se cs-uri-query(k) non è vuoto. Questa dimensione viene utilizzata per calcolare la percentuale di utilizzo della memoria fisica di ogni server. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale query memoria</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per un valore di query cs-uri-query di un server specificato. È condizionato se cs-uri-query(k) non è vuoto. Questa dimensione viene utilizzata per calcolare la percentuale di utilizzo della memoria della query di ogni server. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connessioni di rete</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per un valore cs-uri-query(q) di un server specificato. È condizionato se cs-uri-query(k) non è vuoto. Viene utilizzato per mostrare il numero di connessioni di rete per un determinato server. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Latenza sondaggio Centisecondi</b> </td> 
   <td colname="col2"> Questa dimensione viene utilizzata per calcolare la latenza del sondaggio. Il valore cs-uri-query(m) è diviso per 10 per ridurre le dimensioni della dimensione e copiato nel campo x-poll-latency-centiseconds. Si tratta di una dimensione numerica che prende l’ultima riga per un determinato server. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Controllo rapido riuscito</b> </td> 
   <td colname="col2"> Si tratta di una dimensione semplice creata dal valore cs-uri-query(g) dell'ultima riga per un determinato server. Viene utilizzato per calcolare la metrica di controllo rapido. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale spazio database temporaneo</b> </td> 
   <td colname="col2"> L'ultima riga del valore cs-uri-query(an) viene copiata nel campo x-temp-db-space-Percentuali. Si tratta di un Dimension numerico utilizzato per calcolare la percentuale di spazio del database temporaneo utilizzato su un determinato server. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versione di Insight</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(ab) viene utilizzato per questo Dimension semplice. Si tratta del valore Ultimo non vuoto per un server. Vengono visualizzate le versioni del server di Data Workbench in esecuzione su ciascun server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gruppo</b> </td> 
   <td colname="col2"> Parola di raggruppamento che offre un altro modo per filtrare il set di dati risultante. <p>Nota:  Questa dimensione è impostata in insight_monitor_agent.cfg. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Metriche</b> </td> 
   <td colname="col2"> Di seguito sono elencate le metriche incluse nel profilo di monitoraggio del profilo di Data Workbench e le relative modalità di derivazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Capacità complessiva</b> </td> 
   <td colname="col2"> È la metrica Dimensione capacità per due volte più la metrica Riga capacità divisa per 3. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Riga di capacità</b> </td> 
   <td colname="col2"> Somma della percentuale di riga di capacità per ogni server divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensione della capacità</b> </td> 
   <td colname="col2"> È la somma della percentuale di capacità per ogni server divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Controllo componente</b> </td> 
   <td colname="col2"> Questo è il numero di server in cui il controllo del componente è riuscito è uguale a uno, diviso per il server in cui il servizio è DPU o FSU, il tutto moltiplicato per 100 (per renderlo una percentuale). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Disco "x"</b> </td> 
   <td colname="col2"> Le metriche del disco vengono calcolate prendendo la somma della percentuale di utilizzo del disco per ogni server, divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Minuti di sweep stimati</b> </td> 
   <td colname="col2"> È la somma dei Dekasecond di sweep stimati per ogni server, divisi per la metrica Server in cui Dekaseconds di sweep stimato è maggiore di zero, tutti divisi per 6. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ora ultima chiamata</b> </td> 
   <td colname="col2"> La somma dell'ultimo ping per ogni blocco diviso per blocchi, quindi moltiplicata per 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Load</b> </td> 
   <td colname="col2"> Somma della media di carico per ogni server, divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>File della pagina di memoria</b> </td> 
   <td colname="col2"> Somma della percentuale del file della pagina di memoria per ogni server, divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memoria fisica</b> </td> 
   <td colname="col2"> È la somma della percentuale fisica della memoria per ogni server, divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Query di memoria</b> </td> 
   <td colname="col2"> Somma della percentuale di query di memoria per ogni server, divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connessioni di rete</b> </td> 
   <td colname="col2"> Somma delle connessioni di rete per ogni server divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Millisecondi di latenza del sondaggio</b> </td> 
   <td colname="col2"> Si tratta della somma dei centisecondi di di latenza del sondaggio per ogni server, divisi per la metrica Server, tutti moltiplicati per 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Controllo rapido</b> </td> 
   <td colname="col2"> Questo è il numero di server in cui il successo del controllo rapido è uguale a uno, diviso per la metrica Server, tutti moltiplicati per 100. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Server</b> </td> 
   <td colname="col2"> Somma di uno per ogni server o il numero totale di server monitorati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>DB temporaneo</b> </td> 
   <td colname="col2"> Somma della percentuale di spazio del database temporaneo per ogni server, divisa per la metrica Server. </td> 
  </tr> 
 </tbody> 
</table>
