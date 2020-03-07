---
description: Le seguenti dimensioni sono disponibili per l'uso nel profilo storico workbench data.
solution: Analytics
title: Dimensioni nel profilo storico Workbench dati
topic: Data workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensioni nel profilo storico Workbench dati{#dimensions-in-the-data-workbench-historic-profile}

Le seguenti dimensioni sono disponibili per l&#39;uso nel profilo storico workbench data.

## Dimensioni nel profilo storico Workbench dati {#section-96f1b64f5cb84411b630f97f227d888d}

Le seguenti dimensioni sono disponibili per l&#39;uso nel profilo storico workbench data.

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Blocca</b> </td> 
   <td colname="col2">Questa è l'unica incalcolabile in questa configurazione, è la radice per tutte le dimensioni. Un blocco può essere considerato un server. Utilizza il campo x-trackingid. <p>Nota:  L'ID blocco è un hash del nome del server più il nome dell'host, pertanto per ogni server sarà presente circa un blocco per profilo. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerabile costruita fuori del piano di blocco calcolabile. Ogni riga di dati nel profilo è un ping dell'agente di monitoraggio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Avviso critico</b> </td> 
   <td colname="col2"> Dimensione numerica creata dal valore cs-uri-query(ad). È costruito al livello Ping condizionato che cs-uri-query(a) corrisponde a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Avviso in basso</b> </td> 
   <td colname="col2"> Dimensione numerica generata dal valore cs-uri-query(ac). È costruito a livello di Ping, a condizione che cs-uri-query(a) corrisponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Avviso</b> </td> 
   <td colname="col2"> Dimensione numerica generata dal valore cs-uri-query(ae). È costruito al livello Ping condizionato che cs-uri-query(a) corrisponde a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Qualsiasi rielaborazione di profilo</b> </td> 
   <td colname="col2"> Dimensione numerica generata dal valore cs-uri-query(aa). È costruito al livello Ping a condizione che cs-uri-query(a) corrisponda a "1" e cs-uriquery(k) non sia vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A partire da minuti ritardati</b> </td> 
   <td colname="col2"> cs-uri-query(bi) viene inserita nel campo x-as-of-delay-minute e arrotondata al minuto più vicino. È costruito al livello Ping condizionato che cs-uri-query(a) corrisponde a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale riga capacità</b> </td> 
   <td colname="col2"> Dimensione numerica generata dal valore cs-uri-query(r). È costruito al livello Ping a condizione che cs-uri-query(a) corrisponda a "1" e cs-uriquery(k) non sia vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale dimensione capacità</b> </td> 
   <td colname="col2"> Dimensione numerica generata dal valore cs-uri-query(n). È costruito al livello Ping a condizione che cs-uri-query(a) corrisponda a "1" e cs-uriquery(k) non sia vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Controllo componente completato</b> </td> 
   <td colname="col2"> Dimensione semplice basata sul valore cs-uri-query(v). È costruito a livello di Ping, e condizionato che cs-uri-query(a) corrisponde a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Componenti in errore</b> </td> 
   <td colname="col2"> cs-uri-query(ao) viene divisa dal delimitatore "|" e copiata nel campo x-components-in-error. Molte o molte dimensioni create dal campo x-components-in-error. Costruito a livello Ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondi controllo dettagliati</b> </td> 
   <td colname="col2"> Dimensione numerica generata dal valore cs-uri-query(l). È costruito al livello Ping a condizione che cs-uri-query(k) non sia vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Controllo dettagliato completato</b> </td> 
   <td colname="col2"> Dimensione semplice basata sul valore cs-uri-query(k). È costruito al livello Ping condizionato che cs-uri-query(a) corrisponde a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaByte dimensione</b> </td> 
   <td colname="col2"> cs-uri-query(bc) viene copiato nel campo x-Dimension-gigabyte. Il campo x-dimension-gigabyte è l’utente per questa dimensione semplice, condizionata su cs-uri-query(a) che corrisponde a "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale utilizzata disco "x"</b> </td> 
   <td colname="col2"> Queste dimensioni numeriche sono configurate dai valori cs-uri-query(ah, ai, aj, ak, al). Sono costruiti a livello Ping e condizionati su cs-uri-query(a) corrisponde a "1" e cs-uri-query(k) non è vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dekaseconds di sweep stimati</b> </td> 
   <td colname="col2"> Il campo x-Estimated-sweep-dekaseconds è utilizzato in questa dimensione numerica. Si tratta del tempo di sweep stimato dei server diviso per dieci (risoluzione ridotta della misurazione di sweep per rendere la dimensione più ragionevole). <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaByte di input rapido per minuto</b> </td> 
   <td colname="col2"> Per questa dimensione viene utilizzato il valore cs-uri-query(bj). L'ultima riga di un blocco viene utilizzata come valore per la dimensione. Se il set di dati è in Fast Input, il valore di questa dimensione numerica verrà visualizzato l'MB al minuto in cui il sistema inserisce i dati. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Unione veloce megaByte al minuto</b> </td> 
   <td colname="col2">Per questa dimensione viene utilizzato il valore cs-uri-query(bk). L'ultima riga per un blocco viene utilizzata come valore per la dimensione. Se il set di dati è in Unione veloce, il valore di questa dimensione numerica sarà visualizzato in MB al minuto in cui il sistema sta unendo. <p><p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaBytes campo</b> </td> 
   <td colname="col2">Per questa dimensione viene utilizzato il valore cs-uri-query(bg). Il valore è diviso per 1000 e arrotondato al numero intero più vicino. Il valore di questa dimensione numerica mostrerà la quantità di spazio che i campi del set di dati stanno utilizzando. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gruppo</b> </td> 
   <td colname="col2"> Dimensioni semplici costruite a livello Ping dal valore cs-uri-query(x). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> Per questa dimensione viene utilizzato il valore cs-uri-query(b). Il valore della dimensione Semplice è Ultima riga per un blocco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ultima chiamata</b> </td> 
   <td colname="col2"> il campo x-unixtime viene copiato in x-last-ping e diviso per 10 per ridurre la cardinalità. La dimensione numerica è creata a livello di blocco e utilizza il campo x-last-ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Media caricamento</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per il valore cs-uri-query(i) di un server specificato. È condizionata in modo che cs-uri-query(k) non sia vuota. Questa dimensione viene utilizzata per calcolare il carico medio sui server del sistema monitorato. <p><p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale lettura log</b> </td> 
   <td colname="col2">il valore cs-uri-query(be) viene utilizzato per questa dimensione numerica, creata a livello di Ping. Questa dimensione viene utilizzata per calcolare la percentuale di log in lettura. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale file pagina di memoria</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza il valore cs-uri-query(o), creato a livello di Ping. È condizionata su cs-uri-query(k) non essere vuota, e cs-uri-query(a) corrispondente a "1". Questa dimensione viene utilizzata per calcolare la percentuale di utilizzo della memoria del file di pagina. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaByte fisici memoria totale</b> </td> 
   <td colname="col2">Si tratta di una dimensione numerica che utilizza il valore cs-uri-query(ag), creato a livello di Ping. È condizionata sul fatto che cs-uri-query(k) non sia vuota, e cs-uri-query(a) corrispondente a "1. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale fisica memoria</b> </td> 
   <td colname="col2">Si tratta di una dimensione numerica che utilizza il valore cs-uri-query(ag), creato a livello di Ping. È condizionata sul fatto che cs-uri-query(k) non sia vuota, e cs-uri-query(a) corrispondente a "1. Questa dimensione viene utilizzata per calcolare la percentuale di utilizzo della memoria fisica di ogni server. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale query memoria</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza il valore cs-uri-query(s) a livello Ping. È condizionata su cs-uri-query(k) non essere vuota e cs-uri-query(a) corrispondente a "1. Questa dimensione viene utilizzata per calcolare la percentuale di utilizzo della memoria della query per ogni server. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connessioni di rete</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza il valore cs-uri-query(q) generato al livello Ping. È condizionata su cs-uri-query(k) non essere vuota e cs-uri-query(a) corrispondente a "1. Viene utilizzato per visualizzare il numero di connessioni di rete per un determinato server. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Righe di output</b> </td> 
   <td colname="col2"> il valore cs-uri-query(bh) è diviso per 100000 e copiato nel campo x-output-rows per ridurre le dimensioni della dimensione. Le righe di output X vengono utilizzate in una dimensione numerica creata al livello Ping, a condizione che cs-uri-query(a) corrisponda a "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID tipo ping</b> </td> 
   <td colname="col2"> Dimensione semplice creata utilizzando il valore cs-uri-query(a) a livello di Ping. Questo mostra che tipo di Ping è stato registrato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Latenza sondaggio Centesimi di secondo</b> </td> 
   <td colname="col2">Il valore cs-uri-query(m) è diviso per 10 per ridurre le dimensioni e copiato nel campo x-poll-latency-centiseconds. Si tratta di una dimensione numerica creata al livello Ping, con la condizione che cs-uri-query(k) non sia vuota, e cs-uri-query(a) corrisponda a "1"/ Questa dimensione viene utilizzata per calcolare la latenza del sondaggio. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID modalità di elaborazione</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(bb) viene utilizzato per questa dimensione semplice, creata a livello di Ping. È condizionato che cs-uri-query(bb) non sia vuoto, e che cs-uri-query(a) corrisponda a "2" ID modalità di elaborazione consente di vedere in che modo è elaborato il sistema (Fast Input, Fast Merge, Real Time). <p>Nota:  Questa dimensione viene nascosta e quindi riesposta con valori descrittivi nella modalità di elaborazione delle dimensioni lato client. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profilo</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(ba) viene utilizzato per questa dimensione semplice, è costruito a livello di Ping. Questa dimensione visualizza i nomi dei profili attualmente monitorati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondi controllo rapido</b> </td> 
   <td colname="col2"> Per questa dimensione numerica viene utilizzato il valore cs-uri-query(h). È costruito al livello Ping condizionato che cs-uri-query(a) corrisponde a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verifica rapida completata</b> </td> 
   <td colname="col2"> Si tratta di una dimensione semplice basata sul valore cs-uri-query(g) generato al livello Ping. Viene utilizzato per calcolare la metrica di controllo rapido. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale di elaborazione in tempo reale</b> </td> 
   <td colname="col2"> Dimensione numerica utilizzando il valore cs-uri-query(t) generato al livello Ping. È condizionato che cs-uri-query(a) corrisponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Origine dietro</b> </td> 
   <td colname="col2"> Dimensione semplice basata sul valore cs-uri-query(bl) generato al livello Ping. Questa dimensione visualizza il momento in cui si è verificato l'ultimo contatto con un'origine dati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale spazio DB temporaneo</b> </td> 
   <td colname="col2">Dimensione numerica creata utilizzando il valore cs-uri-query(an), costruito a livello di Ping. È condizionato che cs-uri-query(k) non sia vuoto e cs-uri-query(a) corrisponda a "1". Viene utilizzato per calcolare la percentuale di spazio DB temporaneo utilizzato su un determinato server. <p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale di trasformazione</b> </td> 
   <td colname="col2">per questa dimensione numerica viene utilizzato il valore cs-uri-query(bf). È costruito a livello di Ping. Questa dimensione viene utilizzata per calcolare la percentuale di trasformazione dati completa. <p><p>Nota:  Questa dimensione è nascosta perché è utile solo quando viene calcolata la media in una metrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versione Workbench dati</b> </td> 
   <td colname="col2"> Per questa dimensione semplice viene utilizzato il valore cs-uri-query(ab). È costruito a livello di Ping e condizionato che cs-uri-query(ab) non è vuoto, e cs-uri-query(a) corrisponde a "1". Vengono visualizzate le versioni del server workbench dati in esecuzione su ciascun server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versione principale di Workbench dati</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(ab) viene diviso e il valore di rilascio principale viene copiato nel campo x-insight-version-major. Si tratta di una dimensione semplice costruita a livello di Ping e condizionata che x-insight-version-major non è vuoto, e cs-uri-query(a) corrisponde a "1". </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->

