---
description: Le seguenti dimensioni sono disponibili per l'uso nel profilo Stato server workbench dati.
solution: Analytics
title: Dimensioni nel profilo Stato server Workbench dati
topic: Data workbench
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensioni nel profilo Stato server Workbench dati{#dimensions-in-the-data-workbench-server-status-profile}

Le seguenti dimensioni sono disponibili per l&#39;uso nel profilo Stato server workbench dati.

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Server</b> </td> 
   <td colname="col2"> Costruita dal campo x-trackingid, questa dimensione numerabile rappresenta il workbench dati attualmente in esecuzione dei server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versione agente</b> </td> 
   <td colname="col2"> Per questa dimensione semplice viene utilizzato il valore cs-uri-query(af). Si tratta del valore Last Nonblank per un server. Viene visualizzata la data e l'ora di compilazione per le versioni dell'agente di monitoraggio in esecuzione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Qualsiasi rielaborazione di profilo</b> </td> 
   <td colname="col2"> Il campo cs-uri-query(aa) è utilizzato per questa dimensione numerica, è il valore dell'ultima riga per un determinato server, condizionale su cs-uri-query(k) non è vuoto. Questa dimensione viene utilizzata per indicare se eventuali profili sono in fase di rielaborazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale riga capacità</b> </td> 
   <td colname="col2"> Il campo cs-uri-query(r) viene utilizzato per questa dimensione numerica, è il valore dell'ultima riga per un determinato server, condizionale su cs-uri-query(k) non è vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale dimensione capacità</b> </td> 
   <td colname="col2"> Il campo cs-uri-query(n) viene utilizzato per questa dimensione numerica, è il valore dell'ultima riga per un determinato server, condizionale su cs-uri-query(k) non è vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nome comune</b> </td> 
   <td colname="col2"> Il campo sc-ur-query(am) viene utilizzato per questa dimensione semplice, è il valore del valore Last Nonblank per un determinato server. Visualizza il Nome comune dei server monitorati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Controllo componente completato</b> </td> 
   <td colname="col2"> Il campo cs-uri-query(v) viene utilizzato per questa dimensione semplice, è il valore dell'ultima riga per un determinato server. Questa dimensione controlla i componenti del server per verificarne il corretto funzionamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Componenti in errore</b> </td> 
   <td colname="col2"> Una trasformazione Crossrows prende il valore Last Row della query cs-uri(ao) e lo copia nel campo x-components-in-error. Questa dimensione Da Molte a Molte visualizza tutti i componenti in errore sui server monitorati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ambiente</b> </td> 
   <td colname="col2">Il valore cs-uri-query(c) viene utilizzato per l'ID ambiente. L'ultima riga per un blocco viene utilizzata come valore per la dimensione. Questa dimensione semplice visualizzerà l'ambiente in cui i server sono in esecuzione (a condizione che sia configurata correttamente). <p><p>Nota:  Questa dimensione è impostata in insight_monitor_agent.cfg. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dekaseconds di sweep stimati</b> </td> 
   <td colname="col2"> Il campo x-Estimated-sweep-dekaseconds è utilizzato in questa dimensione numerica. Si tratta del tempo di sweep stimato dei server diviso per dieci (risoluzione ridotta della misurazione di sweep per rendere la dimensione più ragionevole). <p><p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> Per questa dimensione viene utilizzato il valore cs-uri-query(b). Il valore della dimensione Semplice è Ultima riga per un blocco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ultima chiamata</b> </td> 
   <td colname="col2"> x-last-ping è x-unixtime divide per 10 (per contenere vincoli di dimensioni numeriche). Last Ping è l'ultima riga per un determinato blocco e rappresenta l'ultima volta che l'agente di monitoraggio ha registrato lo stato del sistema. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Media caricamento</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per il valore cs-uri-query(i) di un server specificato. È condizionata in modo che cs-uri-query(k) non sia vuota. Questa dimensione viene utilizzata per calcolare il carico medio sui server del sistema monitorato. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale file pagina di memoria</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per il valore cs-uri-query(o) di un server specificato. È condizionata in modo che cs-uri-query(k) non sia vuota. Questa dimensione viene utilizzata per calcolare la percentuale di utilizzo della memoria del file di pagina. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaByte fisici memoria totale</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per il valore cs-uri-query(ag) di un server specificato. È condizionata in modo che cs-uri-query(k) non sia vuota. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale fisica memoria</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per il valore cs-uri-query(ag) di un server specificato. È condizionata in modo che cs-uri-query(k) non sia vuota. Questa dimensione viene utilizzata per calcolare la percentuale di utilizzo della memoria fisica di ogni server. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale query memoria</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per il valore di query cs-uri-query di un server specificato. È condizionata in modo che cs-uri-query(k) non sia vuota. Questa dimensione viene utilizzata per calcolare la percentuale di utilizzo della memoria della query per ogni server. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connessioni di rete</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per il valore cs-uri-query(q) di un server specificato. È condizionata in modo che cs-uri-query(k) non sia vuota. Viene utilizzato per visualizzare il numero di connessioni di rete per un determinato server. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Latenza sondaggio Centesimi di secondo</b> </td> 
   <td colname="col2"> Questa dimensione viene utilizzata per calcolare la latenza del sondaggio. Il valore cs-uri-query(m) è diviso per 10 per ridurre le dimensioni e copiato nel campo x-poll-latency-centiseconds. Si tratta di una dimensione Numerica che prende l'ultima riga per un determinato server. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verifica rapida completata</b> </td> 
   <td colname="col2"> Si tratta di una dimensione semplice basata sul valore cs-uri-query(g) dell'ultima riga per un determinato server. Viene utilizzato per calcolare la metrica di controllo rapido. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale spazio DB temporaneo</b> </td> 
   <td colname="col2"> L'ultima riga del valore cs-uri-query(an) viene copiata nel campo x-temp-db-space-percentuale. Si tratta di una dimensione numerica utilizzata per calcolare la percentuale di spazio DB temporaneo utilizzato su un determinato server. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versione di Insight</b> </td> 
   <td colname="col2"> Per questa dimensione semplice viene utilizzato il valore cs-uri-query(ab). Si tratta del valore Last Nonblank per un server. Vengono visualizzate le versioni del server workbench dati in esecuzione su ciascun server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gruppo</b> </td> 
   <td colname="col2"> Parola di raggruppamento che offre un altro modo per filtrare il set di dati risultante. <p>Nota:  Questa dimensione è impostata in insight_monitor_agent.cfg. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Metriche</b> </td> 
   <td colname="col2"> Di seguito sono elencate le metriche incluse nel profilo di monitoraggio del profilo del workbench dati e le relative modalità di derivazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Capacità</b> </td> 
   <td colname="col2"> È la metrica Dimensione capacità per due volte più la metrica Riga capacità divisa per 3. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Riga di capacità</b> </td> 
   <td colname="col2"> È la somma della percentuale di righe di capacità per ogni server divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensione capacità</b> </td> 
   <td colname="col2"> Si tratta della somma della percentuale di capacità per ogni server divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Controllo componente</b> </td> 
   <td colname="col2"> Questo è il numero di server in cui il controllo del successo del componente è uguale a uno, diviso per il server in cui il servizio è DPU o FSU, tutti moltiplicati per 100 (per renderlo una percentuale). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Disco "x"</b> </td> 
   <td colname="col2"> Le metriche del disco vengono calcolate prendendo la somma della percentuale di utilizzo del disco per ogni server, divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Minuti di sweep stimati</b> </td> 
   <td colname="col2"> Si tratta della somma dei Dekaseconds Sweep Estimated Dekaseconds per ogni Server, divisi per la metrica Server in cui Dekaseconds Sweep Estimated è maggiore di zero, tutti divisi per 6. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ora ultima chiamata</b> </td> 
   <td colname="col2"> La somma di Last Ping per ciascun Block diviso per Blocchi, quindi moltiplicata per 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Caricamento</b> </td> 
   <td colname="col2"> Si tratta della somma della media di carico per ogni server, divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>File della pagina di memoria</b> </td> 
   <td colname="col2"> Si tratta della somma della percentuale di file della pagina di memoria per ogni server, divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memoria fisica</b> </td> 
   <td colname="col2"> Si tratta della somma della percentuale di memoria fisica per ogni server, divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Query di memoria</b> </td> 
   <td colname="col2"> Si tratta della somma della percentuale di query di memoria per ogni server, divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connessioni di rete</b> </td> 
   <td colname="col2"> Si tratta della somma delle connessioni di rete per ogni server divisa per la metrica Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Latenza sondaggio millisecondi</b> </td> 
   <td colname="col2"> Si tratta della somma dei Centesimi di latenza del sondaggio per ogni server, divisi per la metrica Server, il cui valore viene moltiplicato per 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verifica rapida</b> </td> 
   <td colname="col2"> Questo è il numero di server in cui il successo della verifica rapida è uguale a uno, diviso per la metrica Server, il cui numero è moltiplicato per 100. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Server</b> </td> 
   <td colname="col2"> Si tratta della somma di uno per ogni server, o del numero totale di server monitorati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>DB temporaneo</b> </td> 
   <td colname="col2"> Si tratta della somma della percentuale di spazio DB temporaneo per ogni server, divisa per la metrica Server. </td> 
  </tr> 
 </tbody> 
</table>

