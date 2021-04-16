---
description: Le dimensioni seguenti sono disponibili per l’utilizzo nel profilo di cronologia di Data Workbench.
title: Dimensioni nel profilo di cronologia di Data Workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
exl-id: 9df1f317-a985-4132-b32e-f2263e0c23b2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 1%

---

# Dimensioni nel profilo di cronologia di Data Workbench{#dimensions-in-the-data-workbench-historic-profile}

Le dimensioni seguenti sono disponibili per l’utilizzo nel profilo di cronologia di Data Workbench.

## Dimensioni nel profilo di cronologia di Data Workbench {#section-96f1b64f5cb84411b630f97f227d888d}

Le dimensioni seguenti sono disponibili per l’utilizzo nel profilo di cronologia di Data Workbench.

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Blocco</b> </td> 
   <td colname="col2">Questo è l'unico numerabile in questa configurazione, è la radice per tutte le dimensioni. Un blocco può essere considerato un server. Utilizza il campo x-trackingid . <p>Nota:  L'ID blocco è un hash del nome server più il nome host, quindi ci sarà circa un blocco per server per profilo. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> Questa è una dimensione numerabile costruita al di fuori del Contabile Blocco. Ogni riga di dati nel profilo è un ping dell’agente di monitoraggio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Avviso critico</b> </td> 
   <td colname="col2"> Dimension numerico generato dal valore cs-uri-query(ad). Viene costruito a livello di Ping a condizione che cs-uri-query(a) corrisponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Avviso non disponibile</b> </td> 
   <td colname="col2"> Dimension numerico generato dal valore cs-uri-query(ac). È costruito a livello di Ping, a condizione che cs-uri-query(a) corrisponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Avviso</b> </td> 
   <td colname="col2"> Dimension numerico generato dal valore cs-uri-query(ae). Viene costruito a livello di Ping a condizione che cs-uri-query(a) corrisponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Qualsiasi rielaborazione del profilo</b> </td> 
   <td colname="col2"> Dimension numerico generato dal valore cs-uri-query(aa). Viene generato a livello Ping a condizione che cs-uri-query(a) corrisponda a "1" e cs-uriquery(k) non sia vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A partire da minuti di ritardo</b> </td> 
   <td colname="col2"> cs-uri-query(bi) viene inserita nel campo x-as-of-delay-minutes e arrotondata al minuto più vicino. Viene costruito a livello di Ping a condizione che cs-uri-query(a) corrisponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale riga capacità</b> </td> 
   <td colname="col2"> Dimension numerico generato dal valore cs-uri-query(r). Viene generato a livello Ping a condizione che cs-uri-query(a) corrisponda a "1" e cs-uriquery(k) non sia vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale di capacità</b> </td> 
   <td colname="col2"> Dimension numerico generato dal valore cs-uri-query(n). Viene generato a livello Ping a condizione che cs-uri-query(a) corrisponda a "1" e cs-uriquery(k) non sia vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Controllo componente completato</b> </td> 
   <td colname="col2"> Dimension semplice creato dal valore cs-uri-query(v). È costruito a livello di Ping e condizionato che cs-uri-query(a) corrisponde a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Componenti in errore</b> </td> 
   <td colname="col2"> cs-uri-query(ao) viene divisa dal delimitatore "|" e copiata nel campo x-components-in-error. Da molti a molti Dimension generati dal campo x-components-in-error. Costruito a livello di Ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondi di controllo dettagliati</b> </td> 
   <td colname="col2"> Dimension numerico generato dal valore cs-uri-query(l). Viene generato al livello Ping a condizione che cs-uri-query(k) non sia vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Controllo dettagliato completato</b> </td> 
   <td colname="col2"> Dimension semplice creato dal valore cs-uri-query(k). Viene costruito a livello di Ping a condizione che cs-uri-query(a) corrisponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaBytes Dimension</b> </td> 
   <td colname="col2"> cs-uri-query(bc) viene copiato nel campo x-dimension-gigabyte. Il campo x-dimension-gigabyte è l'utente per questo Dimension semplice, condizionato su cs-uri-query(a) corrispondente a "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale di utilizzo del disco "x"</b> </td> 
   <td colname="col2"> Questi Dimension numerici sono configurati dai valori cs-uri-query(ah, ai, aj, ak, al). Sono costruiti a livello Ping e condizionati su cs-uri-query(a) corrisponde a "1" e cs-uri-query(k) non è vuoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dekaseconds di sweep stimati</b> </td> 
   <td colname="col2"> Il campo x-Estimated-sweep-dekaseconds viene utilizzato in questo Dimension numerico. Si tratta del tempo di sweep stimato dei server diviso per dieci (risoluzione ridotta della misurazione di sweep per rendere la dimensione più ragionevole). <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaByte in ingresso rapido al minuto</b> </td> 
   <td colname="col2"> Per questa dimensione viene utilizzato il valore cs-uri-query(bj). L’ultima riga per un blocco viene utilizzata come valore per la dimensione. Se il set di dati è in Fast Input, questo valore del Dimension numerico visualizza la MB al minuto in cui il sistema sta immettendo i dati. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaByte Fast Merge al minuto</b> </td> 
   <td colname="col2">Per questa dimensione viene utilizzato il valore cs-uri-query(bk). L’ultima riga per un blocco viene utilizzata come valore per la dimensione. Se il set di dati è in Fast Merge Questo valore del Dimension numerico visualizza la MB al minuto in cui il sistema sta unendo. <p><p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Byte campo</b> </td> 
   <td colname="col2">Per questa dimensione viene utilizzato il valore cs-uri-query(bg). Il valore è diviso per 1000 e arrotondato al numero intero più vicino. Questo valore del Dimension numerico visualizza la quantità di spazio utilizzato dai campi nel set di dati. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gruppo</b> </td> 
   <td colname="col2"> Dimension semplice costruito a livello Ping dal valore cs-uri-query(x). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> Per questa dimensione viene utilizzato il valore cs-uri-query(b). Il valore della dimensione Semplice è l’ultima riga per un blocco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ultima chiamata</b> </td> 
   <td colname="col2"> il campo x-unixtime viene copiato in x-last-ping e diviso per 10 per ridurre la cardinalità. Il Dimension numerico è generato a livello di blocco e utilizza il campo x-last-ping . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Media del carico</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza l'ultima riga per il valore cs-uri-query(i) di un server specificato. È condizionato se cs-uri-query(k) non è vuoto. Questa dimensione viene utilizzata per calcolare il carico medio sui server del sistema monitorato. <p><p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale di lettura del registro</b> </td> 
   <td colname="col2">il valore cs-uri-query(be) viene utilizzato per questa dimensione numerica, generata a livello di ping. Questa dimensione viene utilizzata per calcolare la percentuale di log letti. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale file di pagina di memoria</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza il valore cs-uri-query(o), generato a livello di ping. È condizionato sul fatto che cs-uri-query(k) non sia vuoto e che cs-uri-query(a) corrisponda a "1". Questa dimensione viene utilizzata per calcolare la percentuale di utilizzo della memoria del file di pagina. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaByte fisici memoria totale</b> </td> 
   <td colname="col2">Si tratta di una dimensione numerica che utilizza il valore cs-uri-query(ag), generato a livello Ping. È condizionata sul fatto che cs-uri-query(k) non sia vuota e che cs-uri-query(a) corrisponda a "1. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale fisica memoria</b> </td> 
   <td colname="col2">Si tratta di una dimensione numerica che utilizza il valore cs-uri-query(ag), generato a livello Ping. È condizionata sul fatto che cs-uri-query(k) non sia vuota e che cs-uri-query(a) corrisponda a "1. Questa dimensione viene utilizzata per calcolare la percentuale di utilizzo della memoria fisica di ogni server. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale query memoria</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza il valore cs-uri-query(s) a livello di ping. È condizionata sul fatto che cs-uri-query(k) non sia vuota e cs-uri-query(a) corrispondente a "1. Questa dimensione viene utilizzata per calcolare la percentuale di utilizzo della memoria della query di ogni server. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Connessioni di rete</b> </td> 
   <td colname="col2"> Si tratta di una dimensione numerica che utilizza il valore cs-uri-query(q) generato a livello Ping. È condizionata sul fatto che cs-uri-query(k) non sia vuota e cs-uri-query(a) corrispondente a "1. Viene utilizzato per mostrare il numero di connessioni di rete per un determinato server. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Righe di output</b> </td> 
   <td colname="col2"> il valore cs-uri-query(bh) è diviso per 100000 e copiato nel campo x-output-rows per ridurre le dimensioni della dimensione. X-output-rows viene utilizzato in un Dimension numerico costruito a livello Ping, a condizione che cs-uri-query(a) corrisponda a "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID tipo di ping</b> </td> 
   <td colname="col2"> Dimension semplice creato utilizzando il valore cs-uri-query(a) a livello di Ping. Questo mostra che tipo di Ping è stato registrato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Latenza sondaggio Centisecondi</b> </td> 
   <td colname="col2">Il valore cs-uri-query(m) è diviso per 10 per ridurre le dimensioni della dimensione e copiato nel campo x-poll-latency-centiseconds. Si tratta di una dimensione numerica creata a livello di ping, purché cs-uri-query(k) non sia vuota e cs-uri-query(a) corrisponda a "1"/ Questa dimensione viene utilizzata per calcolare la latenza del poll. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID modalità di elaborazione</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(bb) viene utilizzato per questo Dimension semplice, costruito a livello di Ping. È necessario che cs-uri-query(bb) non sia vuoto e che cs-uri-query(a) corrisponda a "2" Processing Mode ID (ID modalità di elaborazione) per verificare in che modo si trova il sistema (Fast Input, Fast Merge, Real Time). <p>Nota:  Questa dimensione viene nascosta e quindi riesposta con valori descrittivi nella modalità di elaborazione delle dimensioni lato client. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profilo</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(ba) viene utilizzato per questo Dimension semplice, viene generato a livello di Ping. Questa dimensione visualizza i nomi dei profili attualmente monitorati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondi di controllo rapido</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(h) viene utilizzato per questo Dimension numerico. Viene costruito a livello di Ping a condizione che cs-uri-query(a) corrisponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Controllo rapido riuscito</b> </td> 
   <td colname="col2"> Si tratta di una dimensione semplice creata dal valore cs-uri-query(g) generato a livello di Ping. Viene utilizzato per calcolare la metrica di controllo rapido. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale di elaborazione in tempo reale</b> </td> 
   <td colname="col2"> Dimension numerico utilizzando il valore cs-uri-query(t) generato a livello di ping. È subordinato che cs-uri-query(a) corrisponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Origine più indietro</b> </td> 
   <td colname="col2"> Dimension semplice costruito dal valore cs-uri-query(bl) costruito a livello Ping. Questa dimensione visualizza il quando si è verificato l’ultimo contatto con un’origine dati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale spazio database temporaneo</b> </td> 
   <td colname="col2">Dimension numerico generato utilizzando il valore cs-uri-query(an), generato a livello di Ping. È necessario che cs-uri-query(k) non sia vuoto e cs-uri-query(a) corrisponda a "1". Viene utilizzato per calcolare la percentuale di spazio del database temporaneo utilizzato su un determinato server. <p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Percentuale di trasformazione</b> </td> 
   <td colname="col2">il valore cs-uri-query(bf) viene utilizzato per questa dimensione numerica. È costruito a livello di Ping. Questa dimensione viene utilizzata per calcolare la percentuale di trasformazione dati completa. <p><p>Nota:  Questa dimensione è nascosta perché è utile solo se è stata calcolata la media in una metrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versione Data Workbench</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(ab) viene utilizzato per questo Dimension semplice. Viene generato a livello di Ping e viene impostato che cs-uri-query(ab) non sia vuoto e cs-uri-query(a) corrisponde a "1". Vengono visualizzate le versioni del server di Data Workbench in esecuzione su ciascun server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versione principale Data Workbench</b> </td> 
   <td colname="col2"> Il valore cs-uri-query(ab) è diviso e il valore della versione principale viene copiato nel campo x-insight-version-major. Si tratta di un Dimension semplice costruito a livello Ping e condizionato che x-insight-version-major non è vuoto e cs-uri-query(a) corrisponde a "1". </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->
