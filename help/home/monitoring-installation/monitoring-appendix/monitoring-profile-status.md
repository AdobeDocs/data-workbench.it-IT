---
description: Le seguenti dimensioni sono disponibili per l'uso nel profilo Stato profilo workbench dati.
solution: Analytics
title: Dimensioni nel profilo Stato profilo Workbench dati
topic: Data workbench
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensioni nel profilo Stato profilo Workbench dati{#dimensions-in-the-data-workbench-profile-status-profile}

Le seguenti dimensioni sono disponibili per l&#39;uso nel profilo Stato profilo workbench dati.

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Blocca</b> </td> 
   <td colname="col2"> Questa è l'unica incalcolabile in questa configurazione ed esiste come radice per tutte le dimensioni. Un blocco può essere considerato un server. Utilizza il campo x-trackingid. L'ID blocco è un hash del nome del server più il nome dell'host, pertanto per ogni server sarà presente circa un blocco per profilo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A partire da minuti ritardati</b> </td> 
   <td colname="col2"> cs-uri-query(bi) viene inserita nel campo x-as-of-delay-minute e arrotondata al minuto più vicino. A partire da Minuti ritardo è una dimensione numerica che prende l'Ultima riga da x-come-di-ritardo-minuti per un blocco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ambiente</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(c) viene utilizzato per l'ID ambiente. L'ultima riga per un blocco viene utilizzata come valore per la dimensione. Questa dimensione semplice visualizzerà l'ambiente in cui i server sono in esecuzione (a condizione che sia configurata correttamente). <p>Può essere impostato nel file insight_monitor_agent.cfg </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaByte di input rapido per minuto</b> </td> 
   <td colname="col2"> Per questa dimensione viene utilizzato il valore cs-uri-query(bj). L'ultima riga di un blocco viene utilizzata come valore per la dimensione. Se il set di dati è in Fast Input, il valore di questa dimensione numerica verrà visualizzato l'MB al minuto in cui il sistema inserisce i dati. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Unione veloce megaByte al minuto</b> </td> 
   <td colname="col2">Per questa dimensione viene utilizzato il valore cs-uri-query(bk). L'ultima riga per un blocco viene utilizzata come valore per la dimensione. Se il set di dati è in Unione veloce, il valore di questa dimensione numerica sarà visualizzato in MB al minuto in cui il sistema sta unendo. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaBytes campo</b> </td> 
   <td colname="col2"> Per questa dimensione viene utilizzato il valore cs-uri-query(bg). Il valore è diviso per 1000 e arrotondato al numero intero più vicino. Il valore di questa dimensione numerica mostrerà la quantità di spazio che i campi del set di dati stanno utilizzando. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> Per questa dimensione viene utilizzato il valore cs-uri-query(b). Il valore della dimensione Semplice è Ultima riga per un blocco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ultima chiamata</b> </td> 
   <td colname="col2">x-last-ping è x-unixtime divide per 10 (per contenere vincoli di dimensioni numeriche). Last Ping è l'ultima riga per un determinato blocco e rappresenta l'ultima volta che l'agente di monitoraggio ha registrato lo stato del sistema. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale lettura log</b> </td> 
   <td colname="col2">il valore cs-uri-query(be) è utilizzato per questa dimensione numerica. È l'ultima riga per un determinato blocco. Questa dimensione viene utilizzata per calcolare la percentuale di log in lettura. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID modalità di elaborazione</b> </td> 
   <td colname="col2"> Per questa dimensione semplice viene utilizzato il valore cs-uri-query(bb). È l'ultima riga per un determinato blocco. L'ID della modalità di elaborazione permette di vedere in che modo si trova il sistema (Fast Input, Fast Merge, Real Time). <p>Nota:  Questa dimensione viene nascosta e quindi riesposta con valori descrittivi nella modalità di elaborazione delle dimensioni lato client. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Elaborazione bloccata</b> </td> 
   <td colname="col2"> Il campo x-processing-stached viene creato attraverso varie condizioni per indicare se il profilo è attualmente in esecuzione o meno. È una dimensione semplice. <p>Nota:  Questa dimensione funziona al meglio quando ci sono un gran numero di registri di input da distribuire equamente tra i DPU. Se, ad esempio, è stato caricato un solo file di grandi dimensioni al giorno, il workbench dati può apparire "fermo" per un'ora o più, dando luogo a una lettura falsa positiva da questa dimensione. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profilo</b> </td> 
   <td colname="col2"> Per questa dimensione semplice viene utilizzato il valore cs-uri-query(ba). Questa dimensione visualizza i nomi dei profili attualmente monitorati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Origine dietro</b> </td> 
   <td colname="col2"> L'ultima riga di cs-uri-query(bl) viene copiata nel campo x-source-furthest-behind. La dimensione semplice utilizza l'ultima riga per un determinato blocco. Questa dimensione visualizza il momento in cui si è verificato l'ultimo contatto con un'origine dati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale di trasformazione</b> </td> 
   <td colname="col2"> per questa dimensione numerica viene utilizzato il valore cs-uri-query(bf). È l'ultima riga per un determinato blocco. Questa dimensione viene utilizzata per calcolare la percentuale di trasformazione dati completa. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensioni tempo</b> </td> 
   <td colname="col2"> Ora, Giorno, Settimana, Mese, Ora del giorno e Giorno della settimana sono tutti derivati dal campo x-timestamp. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gruppo</b> </td> 
   <td colname="col2"> Parola di raggruppamento che offre un altro modo per filtrare il set di dati risultante. Impostato nel file insight_monitor_agent.cfg. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Metriche</b> </td> 
   <td colname="col2"> Di seguito sono elencate le metriche incluse nel profilo di monitoraggio del profilo del workbench dati e le relative modalità di derivazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A Partire Da Minuti Di Ritardo</b> </td> 
   <td colname="col2"> Questa metrica è la somma dei minuti di ritardo Come per ogni blocco, quindi divisa per la metrica Blocchi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A Partire Da Secondi Di Ritardo</b> </td> 
   <td colname="col2"> Questa metrica è la somma dei secondi di ritardo Come per ogni blocco e divisa per il numero totale di blocchi. (a partire dalla dimensione dei secondi di ritardo non configurata) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Blocchi</b> </td> 
   <td colname="col2"> Somma uno per ogni blocco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MB di ingresso rapido al minuto</b> </td> 
   <td colname="col2"> La somma di MegaBytes di input rapido per minuto per ciascun blocco diviso per il numero di Blocchi quando MegaByte di input rapido per minuto è maggiore di zero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Unione veloce MB per minuto</b> </td> 
   <td colname="col2"> La somma di MegaByteUnione Rapida per Minuto per ciascun Blocco diviso per il numero di Blocchi quando MegaByteUnione Rapida per Minuto è maggiore di zero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaBytes campo</b> </td> 
   <td colname="col2"> La somma di Gigabyte di campo per ciascun blocco diviso per la metrica Blocchi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ultima età ping</b> </td> 
   <td colname="col2"> L'Ora Di Tempo Meno L'Ora Di Ultima Ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ora ultima chiamata</b> </td> 
   <td colname="col2"> La somma di Last Ping per ciascun Block diviso per Blocchi, quindi moltiplicata per 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lettura log</b> </td> 
   <td colname="col2"> Se la percentuale di lettura del registro è maggiore di zero, la lettura del registro è la somma della percentuale di lettura del registro per ciascun blocco, divisa per la metrica Blocchi, divisa per 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Elaborazione bloccata</b> </td> 
   <td colname="col2"> La somma della dimensione di elaborazione bloccata per ciascun blocco, divisa per la metrica Blocchi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Trasformazione</b> </td> 
   <td colname="col2"> La somma della percentuale di trasformazione per ciascun blocco diviso per la metrica Blocchi, quando la percentuale di trasformazione è maggiore di zero, tutti divisi per 10. </td> 
  </tr> 
 </tbody> 
</table>

