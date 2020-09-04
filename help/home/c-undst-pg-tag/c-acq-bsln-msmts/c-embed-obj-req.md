---
description: Dopo che l’HTML di una pagina è richiesto da un browser, il browser richiede agli oggetti incorporati a cui si fa riferimento nell’HTML della pagina da un server Web di compilare la pagina visualizzata dal browser.
solution: Analytics
title: Acquisizione di richieste di oggetti incorporati (tag pagina)
topic: Data workbench
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 4%

---


# Acquisizione di richieste di oggetti incorporati (tag pagina){#acquiring-embedded-object-requests-page-tags}

Dopo che l’HTML di una pagina è richiesto da un browser, il browser richiede agli oggetti incorporati a cui si fa riferimento nell’HTML della pagina da un server Web di compilare la pagina visualizzata dal browser.

Tali richieste di oggetti incorporati sono più comunemente richieste per file di immagine o file JavaScript, anche se ci sono centinaia o forse migliaia di tipi di oggetti incorporati utilizzati oggi su Internet. Molte di queste richieste di oggetti incorporati non sono generalmente utili per l&#39;analisi o la generazione di rapporti sulle attività aziendali di un sito Internet; molte di queste richieste non sono quindi desiderabili per l&#39;acquisizione a meno che non abbiano uno scopo commerciale specifico, come presentare un annuncio pubblicitario o effettuare un&#39;altra misurazione dell&#39;attività del sito.

Ad esempio, un’immagine potrebbe essere un annuncio pubblicitario e potrebbe essere utile sapere che l’annuncio è stato colpito da un visitatore. Uno snippet JavaScript può essere utilizzato per misurare che il browser in questione ha una determinata caratteristica e riportarlo a una [!DNL Sensor] per l’acquisizione. Ogni pagina di un sito può contenere 10 o 100 richieste di oggetti incorporati. Se un sito memorizza le informazioni di registro per ciascuna di queste richieste, la quantità di memorizzazione dei dati necessaria per mantenere i dati di registro disponibili per l&#39;analisi futura viene moltiplicata per il numero di richieste di oggetti incorporati per ciascuna pagina richiesta. Per questo motivo, [!DNL Site] consente di mantenere le richieste importanti per l&#39;analisi e di scartare altre richieste prima di sostenere costi di storage superflui.

Utilizzando la funzione di esclusione fornita nelle funzionalità di filtraggio del tipo di contenuto di [!DNL Sensor] (aggiungendo &quot;Log=1&quot; alla stringa di query di un URL di richiesta di oggetto incorporato), è possibile acquisire una particolare richiesta di oggetto incorporato e i relativi dati di misurazione senza che sia necessario che il gestore del sito memorizzi tutte le richieste di quel tipo (ad esempio, tutte le `<image>` richieste).

[!DNL Sensor] raccoglie i dati di misurazione nella tabella seguente per ogni richiesta di oggetto incorporato eseguita dal server Web, partendo dal presupposto che non [!DNL Sensor] sia configurato per escluderlo o che il filtro sia stato ignorato. Le informazioni raccolte sono correlate al visitatore e alla sessione e alle sessioni successive attraverso le voci del campo di registro x-trackingid o cs(cookie).

<table id="table_11BE08A798E743EC8E76F738F0CE5884"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome W3C </th> 
   <th colname="col2" class="entry"> Dati raccolti </th> 
   <th colname="col3" class="entry"> Spiegazione </th> 
   <th colname="col4" class="entry"> Esempio </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> Identificatore di tracciamento (visitatore univoco) </td> 
   <td colname="col3"> Identificatore letto da un cookie inserito nel browser dell'utente da <span class="wintitle"> Sensor </span> su richiesta iniziale </td> 
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data </p> <p>Tempo </p> </td> 
   <td colname="col2"> Timestamp </td> 
   <td colname="col3"> Tempo di elaborazione della richiesta da parte del server (con precisione di 100 ns; la precisione dipende dall'ambiente del server e dall'NTP) </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-Type) </td> 
   <td colname="col2"> Tipo di contenuto </td> 
   <td colname="col3"> Tipo di oggetto restituito dal server </td> 
   <td colname="col4"> text/html </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> Codice stato risposta HTTP </td> 
   <td colname="col3"> Codice numerico generato dal server che nota lo stato della risposta del server HTTP </td> 
   <td colname="col4"> 200 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URI Stem </td> 
   <td colname="col3"> La parte "stem" dell'URI richiesto dal client </td> 
   <td colname="col4"> pagedir/page.asp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> IP client </td> 
   <td colname="col3"> Indirizzo IP del client richiedente </td> 
   <td colname="col4"> 127.0.0.1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> Nome dominio server </td> 
   <td colname="col3"> Nome di dominio del server Web che elabora la richiesta </td> 
   <td colname="col4"> <span class="filepath"> www.domain.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> URL di riferimento </td> 
   <td colname="col3"> Contenuto del campo referente HTTP inviato dal client </td> 
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> Agente utente </td> 
   <td colname="col3"> Dispositivo utilizzato per effettuare una richiesta al server HTTP </td> 
   <td colname="col4"> <p>Mozilla/4.0+(compatibile;+MSIE+6.0; </p> <p>+Windows+NT+5.1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Cookie client dal dominio </td> 
   <td colname="col3"> Contenuto di tutti i cookie dell’utente per il sito </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972 x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> Stringa di query </td> 
   <td colname="col3"> Eventuale porzione della stringa di query dell’URI richiesto dal client </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>

