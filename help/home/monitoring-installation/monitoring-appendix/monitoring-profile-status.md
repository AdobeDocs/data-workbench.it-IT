---
description: Le dimensioni seguenti sono disponibili per l’utilizzo nel profilo dello stato del profilo di Data Workbench.
title: Dimensioni nel profilo dello stato del profilo di Data Workbench
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Dimensioni nel profilo dello stato del profilo di Data Workbench{#dimensions-in-the-data-workbench-profile-status-profile}

Le dimensioni seguenti sono disponibili per l’utilizzo nel profilo dello stato del profilo di Data Workbench.

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Blocco</b> </td> 
   <td colname="col2"> Questo è l'unico numerabile in questa configurazione ed esiste come radice per tutte le dimensioni. Un blocco può essere considerato un server. Utilizza il campo x-trackingid . L'ID blocco è un hash del nome server più il nome host, quindi ci sarà circa un blocco per server per profilo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A partire da minuti di ritardo</b> </td> 
   <td colname="col2"> cs-uri-query(bi) viene inserita nel campo x-as-of-delay-minutes e arrotondata al minuto più vicino. A partire da minuti di ritardo è una dimensione numerica che prende l’ultima riga da x-as-of-delay-minutes per un blocco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ambiente</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(c) viene utilizzato per l'ID ambiente. L’ultima riga per un blocco viene utilizzata come valore per la dimensione. Questo Dimension semplice visualizza l'ambiente in cui i server sono in esecuzione (purché configurato correttamente). <p>Questo può essere impostato nel file insight_monitor_agent.cfg </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaByte in ingresso rapido al minuto</b> </td> 
   <td colname="col2"> Per questa dimensione viene utilizzato il valore cs-uri-query(bj). L’ultima riga per un blocco viene utilizzata come valore per la dimensione. Se il set di dati è in Fast Input, questo valore del Dimension numerico visualizza la MB al minuto in cui il sistema sta immettendo i dati. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaByte Fast Merge al minuto</b> </td> 
   <td colname="col2">Per questa dimensione viene utilizzato il valore cs-uri-query(bk). L’ultima riga per un blocco viene utilizzata come valore per la dimensione. Se il set di dati è in Fast Merge Questo valore del Dimension numerico visualizza la MB al minuto in cui il sistema sta unendo. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Byte campo</b> </td> 
   <td colname="col2"> Per questa dimensione viene utilizzato il valore cs-uri-query(bg). Il valore è diviso per 1000 e arrotondato al numero intero più vicino. Questo valore del Dimension numerico visualizza la quantità di spazio utilizzato dai campi nel set di dati. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> Per questa dimensione viene utilizzato il valore cs-uri-query(b). Il valore della dimensione Semplice è l’ultima riga per un blocco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ultima chiamata</b> </td> 
   <td colname="col2">x-last-ping è x-unixtime divide per 10 (per adattarsi ai vincoli di dimensione delle dimensioni numeriche). Ultimo ping è l'ultima riga per un determinato blocco e rappresenta l'ultima volta che l'agente di monitoraggio ha registrato l'integrità del sistema. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale di lettura del registro</b> </td> 
   <td colname="col2">per questa dimensione numerica viene utilizzato il valore cs-uri-query(be) . È l’ultima riga per un determinato blocco. Questa dimensione viene utilizzata per calcolare la percentuale di log letti. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID modalità di elaborazione</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(bb) viene utilizzato per questo Dimension semplice. È l’ultima riga per un determinato blocco. L'ID della modalità di elaborazione consente di vedere in che modo si trova l'elaborazione del sistema (Fast Input, Fast Merge, Real Time). <p>Nota:  Questa dimensione viene nascosta e quindi riesposta con valori descrittivi nella modalità di elaborazione delle dimensioni lato client. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Elaborazione bloccata</b> </td> 
   <td colname="col2"> Il campo con elaborazione x bloccato viene creato in diverse condizioni per indicare se il profilo è attualmente in esecuzione o meno. È una dimensione semplice. <p>Nota:  Questa dimensione funziona al meglio quando ci sono un gran numero di registri di input da distribuire equamente tra le DPU. Se, ad esempio, è presente un solo file di grandi dimensioni caricato al giorno, Data Workbench può apparire in "stallo" per un’ora o più, dando luogo a una lettura falsa positiva da questa dimensione. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profilo</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(ba) viene utilizzato per questo Dimension semplice. Questa dimensione visualizza i nomi dei profili attualmente monitorati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Origine più indietro</b> </td> 
   <td colname="col2"> L'ultima riga di cs-uri-query(bl) viene copiata nel campo x-source-forthest-behind . Il Dimension semplice utilizza l'ultima riga per un determinato blocco. Questa dimensione visualizza il quando si è verificato l’ultimo contatto con un’origine dati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale di trasformazione</b> </td> 
   <td colname="col2"> il valore cs-uri-query(bf) viene utilizzato per questa dimensione numerica. È l’ultima riga per un determinato blocco. Questa dimensione viene utilizzata per calcolare la percentuale di trasformazione dati completa. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensioni temporali</b> </td> 
   <td colname="col2"> Ora, Giorno, Settimana, Mese, Ora del giorno e Giorno della settimana sono tutti derivati dal campo x-timestamp . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gruppo</b> </td> 
   <td colname="col2"> Parola di raggruppamento che offre un altro modo per filtrare il set di dati risultante. Impostato nel file insight_monitor_agent.cfg . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Metriche</b> </td> 
   <td colname="col2"> Di seguito sono elencate le metriche incluse nel profilo di monitoraggio del profilo di Data Workbench e le relative modalità di derivazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A Partire Da Minuti Di Ritardo</b> </td> 
   <td colname="col2"> Questa metrica è la somma dei minuti di ritardo come di per ogni blocco, quindi divisa per la metrica Blocchi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A Partire Da Secondi Di Ritardo</b> </td> 
   <td colname="col2"> Questa metrica è la somma dei secondi di ritardo per ciascun blocco e divisa per il numero totale di blocchi. (A partire dal Dimension dei secondi di ritardo non configurato) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Blocchi</b> </td> 
   <td colname="col2"> Somma uno per ogni blocco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MB di ingresso rapido al minuto</b> </td> 
   <td colname="col2"> La somma di MegaBytes di input rapido per minuto per ogni blocco divisa per il numero di blocchi quando MegaBytes di input rapido per minuto è maggiore di zero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MB di unione rapida al minuto</b> </td> 
   <td colname="col2"> La somma di MegaByte Fast Merge per minuto per ogni blocco divisa per il numero di blocchi quando MegaByte Fast Merge per Minuto è maggiore di zero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Byte campo</b> </td> 
   <td colname="col2"> La somma dei Gigabyte di campo per ogni blocco divisa per la metrica Blocchi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Età ultimo ping</b> </td> 
   <td colname="col2"> A partire dal tempo meno Tempo ultimo ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ora ultima chiamata</b> </td> 
   <td colname="col2"> La somma dell'ultimo ping per ogni blocco diviso per blocchi, quindi moltiplicata per 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lettura del registro</b> </td> 
   <td colname="col2"> Se la percentuale di lettura del registro è maggiore di zero, la percentuale di lettura del registro è la somma della percentuale di lettura del registro per ciascun blocco, divisa per la metrica Blocchi, divisa per 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Elaborazione bloccata</b> </td> 
   <td colname="col2"> La somma del Dimension di elaborazione in stallo per ogni blocco, divisa per la metrica Blocchi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Transformation (Trasformazione)</b> </td> 
   <td colname="col2"> La somma della percentuale di trasformazione per ogni blocco divisa per la metrica Blocchi, quando la percentuale di trasformazione è maggiore di zero, divisa per 10. </td> 
  </tr> 
 </tbody> 
</table>
