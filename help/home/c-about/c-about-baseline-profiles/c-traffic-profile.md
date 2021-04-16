---
description: Il profilo Traffico contiene le metriche seguenti per identificare il traffico del visitatore.
title: Metriche del profilo di traffico
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
exl-id: 38f191e5-5b30-4fe0-a680-bcb33fe52eca
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 2%

---

# Metriche del profilo di traffico{#traffic-profile-metrics}

Il profilo Traffico contiene le metriche seguenti per identificare il traffico del visitatore.

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
   <td colname="col2">Formula: <span class="filepath"> Page_Views[no shift(None,Page_View, Session,-1)]</span><p>Livello: Visualizzazione a pagina </p></td> 
   <td colname="col3"> Il numero di sessioni entrate nel sito in ogni pagina. Questa metrica viene valutata solo sulla dimensione Pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tasso di uscita </td> 
   <td colname="col2">Formula: <span class="filepath"> Uscite/Page_Views </span><p>Livello: Visualizzazione a pagina </p></td> 
   <td colname="col3"> Percentuale di sessioni uscite dal sito da ogni pagina. La metrica Tasso di uscita può essere valutata solo sulla dimensione della pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uscite </td> 
   <td colname="col2">Formula:<span class="filepath"> Page_Views[no shift(None,Page_View, Session,1)] </span><p>Livello: Visualizzazione a pagina </p></td> 
   <td colname="col3"> Numero di sessioni uscite dal sito da ogni pagina. Questa metrica viene valutata solo sulla dimensione Pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">Formula: <span class="filepath"> (raw(Visitatori) - ((raw(Visitatori) + .69)^0.5 * 1.281551 - 1.2269))*(Visitatori/raw(Visitatori))</span><p>Livello: Visitatore </p></td> 
   <td colname="col3"> Misura del numero più basso di visitatori possibili come riportato da Insight. Matematicamente, specifica il numero più basso di visitatori con una probabilità del 90%. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durata visualizzazione pagina </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> somma (esatto_page_duration, page_view)*0.1/Page_Views[any Exact_Page_Duration]</span></p> <p>Livello: Visualizzazione a pagina </p> </td> 
   <td colname="col3"> Lunghezza media (MM:SS) utilizzata in una pagina o in un gruppo di pagine specifici. Questa metrica viene valutata solo sulla dimensione Pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzazioni pagina per sessione </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Page_Views/ (Sessioni per Page_View) </span></p> <p>Livello: Sessione </p> </td> 
   <td colname="col3"> Il numero medio di visualizzazioni di pagina in ogni sessione con visualizzazioni di pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzazioni pagina </td> 
   <td colname="col2">Formula: <span class="filepath"> sum(One, Page_View)</span><p>Livello: Visualizzazione a pagina </p></td> 
   <td colname="col3"> Il numero di visualizzazioni di pagina. Una visualizzazione di pagina è una richiesta per una pagina definita (l’accesso alle immagini e ad altri tipi di contenuto filtrato non viene conteggiato). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct delle visualizzazioni di pagina </td> 
   <td colname="col2">Formula: <span class="filepath"> Page_Views/total(Page_Views) </span><p>Livello: Visualizzazione a pagina </p></td> 
   <td colname="col3"> La percentuale di visualizzazioni di pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct of Sessions </td> 
   <td colname="col2">Formula: <span class="filepath"> Sessions/total(Sessions)</span><p>Livello: Sessione </p></td> 
   <td colname="col3"> Percentuale di sessioni. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Punto di visitatori </td> 
   <td colname="col2">Formula: <span class="filepath"> Visitatori/totale(Visitatori) </span><p>Livello: Visitatore </p></td> 
   <td colname="col3"> La percentuale di visitatori. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitatori Di Riferimento Pct </td> 
   <td colname="col2"> <p>Formula: Referred_Visitors/Visitors </p> <p>Livello: Visitatore </p> </td> 
   <td colname="col3"> La percentuale di visitatori a cui è stato fatto riferimento in questo sito da un altro sito. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessioni di riferimento </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Sessioni[Referente&lt;&gt; 'Nessuno' e Referente&lt;&gt;'bookmarks']</span></p> <p>Livello: Sessione </p> </td> 
   <td colname="col3"> Il numero di sessioni a cui è stato fatto riferimento a questo sito da un altro sito. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitatori di riferimento </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Visitatori[Visitor_ Referrer&lt;&gt;'None' e Visitor_Referrer&lt;&gt;'book marks']</span></p> <p>Livello: Visitatore </p> </td> 
   <td colname="col3"> Il numero di visitatori a cui è stato fatto riferimento a questo sito da un altro sito. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mantenimento </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Sessions[shift(None,Ses sion,Visitor,1) = ""] / Sessions</span></p> <p>Livello: Sessione </p> </td> 
   <td colname="col3"> La percentuale di sessioni che non sono le ultime sessioni dei visitatori. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durata sessione </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> (somma (Exact_Page_Duration, Session)*.1/Sessions)[Session_ Duration &lt;= '01:00:00']</span></p> <p>Livello: Sessione </p> </td> 
   <td colname="col3">La lunghezza media di tempo (MM:SS) che un visitatore trascorre in una sessione. <p><p>Nota: Puoi utilizzare questa metrica con la funzione <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> Esportazione segmento</a> . </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessioni per visualizzazione pagina </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Sessioni di Page_View</span></p> <p> Livello: Sessione </p> </td> 
   <td colname="col3"> Il numero di sessioni che avevano una visualizzazione di pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessions </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> sum(One, Session)</span></p> <p>Livello: Sessione </p> </td> 
   <td colname="col3"> Un conteggio delle sessioni dei visitatori. Una sessione è un periodo di attività per un visitatore di un sito web. Le sessioni individuali per ogni visitatore sono identificate utilizzando cookie, timeout e altre caratteristiche. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> affidabilità(sessioni) * 1.281551 / Sessions</span></p> <p>Livello: Visitatore </p> </td> 
   <td colname="col3"> Misura dell’affidabilità della metrica Sessions come riportata da Data Workbench. Matematicamente, si tratta di una percentuale +/- che specifica l'intervallo entro il quale la risposta effettiva sarà pari all'80% del tempo. Di regola, raddoppiando la percentuale di SCI80 si otterrà un intervallo entro il quale la risposta effettiva sarà il 99% del tempo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> ((raw(Visitatori) + .68)^0.5 * 1.281551 + 1.2269) + raw(Visitatori))*( Visitatori/raw(Visitatori))</span></p> <p>Livello: Visitatore </p> </td> 
   <td colname="col3"> Misura del numero più elevato di visitatori possibili come riportato da Insight. Matematicamente, specifica il numero più alto di visitatori con una probabilità del 90%. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">Formula: <span class="filepath"> ((raw(Visitatori) + .68)^0.5 * 1.281551 + 1.2269) / raw(Visitatori)</span><p>Livello: Visitatore </p></td> 
   <td colname="col3"> Una misura dell’affidabilità della metrica Visitatori come riportata da Insight. Matematicamente, si tratta di una percentuale +/- che specifica l'intervallo entro il quale la risposta effettiva sarà pari all'80% del tempo. Di regola, raddoppiando la percentuale VCI80 si otterrà un intervallo entro il quale la risposta effettiva sarà il 99% del tempo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitatori per visualizzazione pagina </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Visitatori per Page_View</span></p> <p>Livello: Visualizzazione a pagina </p> </td> 
   <td colname="col3"> Il numero di visitatori con una visualizzazione di pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitatori per sessione </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Visitatori per sessione </span></p> <p>Livello: Sessione </p> </td> 
   <td colname="col3"> Il numero di visitatori che hanno avuto una sessione. </td> 
  </tr> 
 </tbody> 
</table>
