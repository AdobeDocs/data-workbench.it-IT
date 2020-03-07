---
description: Sensor acquisisce tutti i dati di misurazione eseguiti sulle richieste di pagina (richieste GET) effettuate ai server Web in cui è stata installata.
solution: Analytics
title: Acquisizione dati richiesta pagina
topic: Data workbench
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Acquisizione dati richiesta pagina{#acquiring-page-request-data}

Sensor acquisisce tutti i dati di misurazione eseguiti sulle richieste di pagina (richieste GET) effettuate ai server Web in cui è stata installata.

[!DNL Sensor] acquisisce questi dati di misurazione attraverso l&#39;interfaccia di programmazione dell&#39;applicazione del server Web, direttamente dall&#39;istanza o dalle istanze del software del server Web in esecuzione sul server Web. [!DNL Sensor] non accede ai file di registro generati dal server Web. Infatti, dopo che [!DNL Sensor] e dopo che il server workbench dati è stato installato e testato, la funzione di registrazione nativa del server Web può essere disattivata senza influire sulla raccolta dei dati. In molti casi, la disabilitazione della registrazione di file ai dischi locali dei computer server Web migliora la capacità di trasmissione delle pagine di tali server Web, a causa della quantità relativamente grande di I/O disco fisso richiesto per registrare queste informazioni sul disco locale del server Web.

[!DNL Sensor] raccoglie i dati delle misurazioni e delle richieste Web direttamente da ogni processo del server Web e del server Web virtuale (se applicabile) e scrive temporaneamente i dati su un file di coda, una coda di memoria tollerante agli errori con supporto del disco fisso, nel server Web. Il servizio Sensor Transmitter (o demone a seconda della piattaforma) recupera i dati dal file di coda, quindi li comprime e li codifica prima di trasmetterlo al server del workbench dati per l&#39;archiviazione a lungo termine. Con [!DNL Sensor], i dati vengono accumulati sui computer del server Web nel file coda solo se si ha un problema di rete o di altro tipo che ne impedisce la trasmissione. Il file di coda consente l&#39;efficiente archiviazione locale di ore a giorni di dati di richiesta web per proteggere i dati se un errore di rete o di sistema non consente la trasmissione dei dati al server workbench dati in tempo reale.

[!DNL Sensor] raccoglie i dati di misurazione da ciascun processo del server Web fisico e logico, li filtra per tipo di contenuto, li comprime, li cifra e li invia in streaming al server del workbench dati.

La tabella seguente contiene i campi delle informazioni di registro acquisite da [!DNL Sensor] per ogni richiesta GET che non viene filtrata in base al file di [!DNL Sensor’s] configurazione:

<table id="table_5F65474150EC41648B35D0B031FB9B15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome W3C </th> 
   <th colname="col2" class="entry"> Dati raccolti </th> 
   <th colname="col3" class="entry"> Spiegazione </th> 
   <th colname="col4" class="entry"> Spiegazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> Identificatore di tracciamento (visitatore univoco) </td> 
   <td colname="col3"> Identificatore letto da un cookie inserito nel browser dell'utente dal <span class="wintitle"> sensore </span> nella richiesta iniziale del visitatore </td> 
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
   <td colname="col4"> 404 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URI Stem </td> 
   <td colname="col3"> La parte di stelo dell'URI richiesto dal client </td> 
   <td colname="col4"> <span class="filepath"> pagedir/page.asp </span> </td> 
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
   <td colname="col4"> Mozilla/4.0+(compatibile;+MSIE+6.0; +Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Cookie client dal dominio </td> 
   <td colname="col3"> Contenuto di tutti i cookie dell’utente per il sito </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> Stringa di query </td> 
   <td colname="col3"> Eventuale porzione della stringa di query dell’URI richiesto dal client </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>

