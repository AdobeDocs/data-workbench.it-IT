---
description: Sensor acquisisce tutti i dati di misurazione che vengono eseguiti sulle richieste di pagina (richieste di GET) effettuate ai server web in cui è stato installato.
title: Acquisizione dei dati della richiesta di pagina
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
exl-id: e42566a3-d5b4-4f1a-b8cd-1ea646041101
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 4%

---

# Acquisizione dei dati della richiesta di pagina{#acquiring-page-request-data}

{{eol}}

Sensor acquisisce tutti i dati di misurazione che vengono eseguiti sulle richieste di pagina (richieste di GET) effettuate ai server web in cui è stato installato.

[!DNL Sensor] acquisisce i dati di misurazione tramite l’interfaccia di programmazione dell’applicazione del server web, direttamente dall’istanza o dalle istanze del software del server web in esecuzione sul server web. [!DNL Sensor] non accede ai file di registro generati dal server web. Infatti, dopo [!DNL Sensor] e il server di Data Workbench è stato installato e testato, la funzione di registrazione nativa del server web può essere disabilitata senza influire sulla raccolta dei dati. In molti casi, la disabilitazione della registrazione dei file sui dischi locali dei computer server web migliora la capacità di servizio delle pagine di tali server web a causa della quantità relativamente grande di I/O disco fisso necessaria per registrare tali informazioni sul disco locale del computer server web.

[!DNL Sensor] raccoglie i dati di misurazione e richiesta web direttamente da ogni processo del server web e del server web virtuale (se applicabile) e scrive temporaneamente i dati in un file di coda, una coda di memoria a tolleranza di errore con supporto del disco fisso, sul server web. Il servizio Sensor Transmitter (o daemon a seconda della piattaforma) recupera i dati dal file di coda, quindi li comprime e li crittografa prima di trasmetterli al server di Data Workbench per l’archiviazione a lungo termine. Con [!DNL Sensor], i dati vengono accumulati sui computer server web nel file di coda solo se si ha un problema di rete o di altro tipo che ne impedisce la trasmissione. Il file di coda consente l’efficiente archiviazione locale di ore o giorni di dati di richiesta web per proteggere i dati se un errore di rete o di sistema non consente la trasmissione dei dati al server di Data Workbench in tempo reale.

[!DNL Sensor] raccoglie i dati di misurazione da ciascun processo del server web fisico e logico, li filtra per tipo di contenuto, li comprime, li crittografa e li invia in streaming al server di Data Workbench.

La tabella seguente contiene i campi delle informazioni di log acquisite da [!DNL Sensor] per ogni richiesta di GET che non viene filtrata in base a [!DNL Sensor’s] file di configurazione:

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
   <td colname="col3"> Identificatore letto da un cookie inserito nel browser dell’utente da <span class="wintitle"> Sensore </span> sulla richiesta iniziale del visitatore </td>
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Data </p> <p>Tempo </p> </td>
   <td colname="col2"> Marca temporale </td>
   <td colname="col3"> il momento in cui la richiesta è stata elaborata dal server (con precisione di 100 ns; la precisione dipende dall'ambiente del server e da NTP) </td>
   <td colname="col4"> 2002-11-21 17:21:45,123 </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-Type) </td>
   <td colname="col2"> Tipo di contenuto </td>
   <td colname="col3"> Tipo di oggetto restituito dal server </td>
   <td colname="col4"> text/html </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> Codice di stato della risposta HTTP </td>
   <td colname="col3"> Codice numerico generato dal server che prende nota dello stato della risposta del server HTTP </td>
   <td colname="col4"> 404 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> Stile URI </td>
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
   <td colname="col2"> Nome di dominio del server </td>
   <td colname="col3"> Nome di dominio del server web che elabora la richiesta </td>
   <td colname="col4"> <span class="filepath"> www.domain.com </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> URL di riferimento </td>
   <td colname="col3"> Contenuto del campo referente HTTP inviato dal client </td>
   <td colname="col4"> <span class="filepath"> https://www.referringsite.com </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> Agente utente </td>
   <td colname="col3"> Dispositivo utilizzato per effettuare una richiesta al server HTTP </td>
   <td colname="col4"> Mozilla/4.0+(compatibile;+MSIE+6.0; +Windows+NT+5.1) </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> Cookie client da dominio </td>
   <td colname="col3"> Contenuto di tutti i cookie dell’utente per il sito </td>
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> Stringa di query </td>
   <td colname="col3"> La porzione, se presente, dell'URI richiesto dal client </td>
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td>
  </tr>
 </tbody>
</table>
