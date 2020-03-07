---
description: Il profilo Traffico contiene le metriche seguenti per identificare il traffico dei visitatori.
solution: Analytics
title: Metriche del profilo di traffico
topic: Data workbench
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Metriche del profilo di traffico{#traffic-profile-metrics}

Il profilo Traffico contiene le metriche seguenti per identificare il traffico dei visitatori.

<table id="table_D981FB9F8B734E3C845A9628548565F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Formula e livello della metrica </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Voci </td> 
   <td colname="col2">Formula: <span class="filepath"> Page_Views[no shift(None,Page_View, Session,-1)]</span><p>Livello: Visualizzazione pagina </p></td> 
   <td colname="col3"> Il numero di sessioni entrate nel sito in ogni pagina. Questa metrica viene valutata solo sulla dimensione Pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Frequenza di uscita </td> 
   <td colname="col2">Formula: <span class="filepath"> Exits/Page_Views </span><p>Livello: Visualizzazione pagina </p></td> 
   <td colname="col3"> Percentuale di sessioni uscite dal sito da ogni pagina. La metrica Frequenza di uscita può essere valutata solo sulla dimensione della pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uscite </td> 
   <td colname="col2">Formula:<span class="filepath"> Page_Views[no shift(None,Page_View, Session,1)] </span><p>Livello: Visualizzazione pagina </p></td> 
   <td colname="col3"> Numero di sessioni uscite dal sito da ogni pagina. Questa metrica viene valutata solo sulla dimensione Pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">Formula: <span class="filepath"> (raw(Visitatori) - (raw(Visitatori) + .69)^0.5 * 1.281551 - 1.2269)*(Visitatori/raw(Visitatori))</span><p>Livello: Visitatore </p></td> 
   <td colname="col3"> Una misura del numero più basso di visitatori possibili come segnalato da Insight. Matematicamente, specifica il numero più basso di visitatori con una probabilità del 90%. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durata visualizzazione pagina </td> 
   <td colname="col2"> <p>Formula: somma <span class="filepath"> (esatta_durata_pagina, visualizzazione_pagina)*0.1/Page_Views[qualsiasi Exact_Page_Duration]</span></p> <p>Livello: Visualizzazione pagina </p> </td> 
   <td colname="col3"> Durata media (MM:SS) impiegata per una pagina o un gruppo di pagine particolari. Questa metrica viene valutata solo sulla dimensione Pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzazioni pagina per sessione </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Page_Views/ (sessioni per Page_View) </span></p> <p>Livello: Sessione </p> </td> 
   <td colname="col3"> Numero medio di visualizzazioni di pagina in ciascuna sessione con visualizzazioni di pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzazioni pagina </td> 
   <td colname="col2">Formula: <span class="filepath"> sum(One, Page_View)</span><p>Livello: Visualizzazione pagina </p></td> 
   <td colname="col3"> Numero di visualizzazioni di pagina. Una visualizzazione di pagina è una richiesta per una pagina definita (l'accesso alle immagini e ad altri tipi di contenuto filtrato non viene conteggiato). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct di visualizzazioni pagina </td> 
   <td colname="col2">Formula: <span class="filepath"> Page_Views/total(Page_Views) </span><p>Livello: Visualizzazione pagina </p></td> 
   <td colname="col3"> Percentuale di visualizzazioni di pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Punto delle sessioni </td> 
   <td colname="col2">Formula: <span class="filepath"> Sessioni/totali(Sessioni)</span><p>Livello: Sessione </p></td> 
   <td colname="col3"> Percentuale di sessioni. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct of Visitors </td> 
   <td colname="col2">Formula: <span class="filepath"> Visitatori/totali(Visitatori) </span><p>Livello: Visitatore </p></td> 
   <td colname="col3"> La percentuale di visitatori. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitatori Di Riferimento Pct </td> 
   <td colname="col2"> <p>Formula: Referred_Visitors/Visitors </p> <p>Livello: Visitatore </p> </td> 
   <td colname="col3"> La percentuale di visitatori cui è stato fatto riferimento a questo sito da un altro sito. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessioni di riferimento </td> 
   <td colname="col2"> <p>Formula: Sessioni <span class="filepath"> [Referente&lt;&gt; 'Nessuno' e Referente&lt;&gt;'bookmarks']</span></p> <p>Livello: Sessione </p> </td> 
   <td colname="col3"> Numero di sessioni a cui è stato fatto riferimento in questo sito da un altro sito. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitatori di riferimento </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Visitatori[Visitor_Referrer&lt;&gt;'None' and Visitor_Referrer&lt;&gt;'book marks']</span></p> <p>Livello: Visitatore </p> </td> 
   <td colname="col3"> Numero di visitatori a cui è stato fatto riferimento in questo sito da un altro sito. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mantenimento </td> 
   <td colname="col2"> <p>Formula: Sessioni <span class="filepath"> [shift(None,Ses session,Visitor,1) = ""] / Sessioni</span></p> <p>Livello: Sessione </p> </td> 
   <td colname="col3"> Percentuale di sessioni che non sono i visitatori delle ultime sessioni. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durata sessione </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> (somma (Exact_Page_Duration, Session)*.1/Sessions)[Session_ Duration &lt;= '01:00:00']</span></p> <p>Livello: Sessione </p> </td> 
   <td colname="col3">La durata media (MM:SS) di un visitatore in una sessione. <p><p>Nota: Puoi usare questa metrica con la funzione <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> Esportazione</a> segmenti. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessioni per visualizzazione pagina </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Sessioni per Page_View</span></p> <p> Livello: Sessione </p> </td> 
   <td colname="col3"> Il numero di sessioni con una visualizzazione pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessioni </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> sum(Una, Sessione)</span></p> <p>Livello: Sessione </p> </td> 
   <td colname="col3"> Numero totale di sessioni di visitatori. Una sessione è un periodo di attività per un visitatore di un sito Web. Le singole sessioni per ogni visitatore vengono identificate utilizzando cookie, timeout e altre caratteristiche. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> trust(Sessioni) * 1.281551 / Sessioni</span></p> <p>Livello: Visitatore </p> </td> 
   <td colname="col3"> Misura della confidenza della metrica Sessioni come riportata dal workbench dati. Matematicamente, si tratta di una percentuale +/- che specifica l'intervallo entro il quale la risposta effettiva sarà pari all'80% del tempo. Di regola, raddoppiando la percentuale di SCI80 si ottiene un intervallo entro il quale la risposta effettiva sarà pari al 99% del tempo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> ((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) + raw(Visitors)*( Visitors/raw(Visitors))</span></p> <p>Livello: Visitatore </p> </td> 
   <td colname="col3"> Misura del numero più elevato di visitatori possibili come segnalato da Insight. Matematicamente, specifica il numero più alto di visitatori con una probabilità del 90%. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">Formula: <span class="filepath"> (raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) / raw(Visitatori)</span><p>Livello: Visitatore </p></td> 
   <td colname="col3"> Una misura di confidenza della metrica Visitatori come segnalata da Insight. Matematicamente, si tratta di una percentuale +/- che specifica l'intervallo entro il quale la risposta effettiva sarà pari all'80% del tempo. Come regola di base, raddoppiando la percentuale VCI80 si ottiene un intervallo entro il quale la risposta effettiva sarà pari al 99% del tempo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitatori per visualizzazione pagina </td> 
   <td colname="col2"> <p>Formula: Visitatori per <span class="filepath"> Page_View</span></p> <p>Livello: Visualizzazione pagina </p> </td> 
   <td colname="col3"> Il numero di visitatori con una visualizzazione pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitatori per sessione </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Visitatori per sessione </span></p> <p>Livello: Sessione </p> </td> 
   <td colname="col3"> Numero di visitatori che hanno avuto una sessione. </td> 
  </tr> 
 </tbody> 
</table>

