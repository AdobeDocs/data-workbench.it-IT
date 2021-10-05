---
description: I siti web progettati utilizzando il Flash richiedono particolare attenzione per quanto riguarda l’acquisizione delle azioni dei visitatori eseguite all’interno dei contenuti rich media.
title: Tracciamento delle attività dei visitatori all’interno dei contenuti flash multimediali
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
exl-id: f51c7034-a7fd-4575-80e1-18fc6513ca2b
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 5%

---

# Tracciamento delle attività dei visitatori all’interno dei contenuti flash multimediali{#tracking-visitor-activity-within-flash-rich-media-content}

I siti web progettati utilizzando il Flash richiedono particolare attenzione per quanto riguarda l’acquisizione delle azioni dei visitatori eseguite all’interno dei contenuti rich media.

Utilizzando [!DNL Flash] ActionScript, puoi apportare semplici modifiche ai filmati [!DNL Flash] esistenti per consentire il tracciamento di tutte le interazioni dei visitatori con il filmato, ad esempio i clic dei pulsanti o i movimenti del mouse.

Per facilitare il tracciamento delle attività dei visitatori all&#39;interno del filmato [!DNL Flash], segui i passaggi elencati di seguito:

1. Aggiungi il seguente codice ActionScript al filmato. Questo codice rappresenta una funzione che può essere richiamata dagli eventi all&#39;interno del filmato [!DNL Flash] che desideri monitorare.

   ```
   // FLASH TAG CODE BEGIN
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt";
   function tag(PAGENAME,VARIABLES) {
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0);
   }
   // FLASH TAG CODE END
   ```

1. Crea un file vuoto denominato [!DNL flashtag.txt] e inserisci il file sui server web.
1. Nella funzione del passaggio 1, sostituisci il segnaposto \[[!DNL PATH_TO_WEB_SERVER]\] con il percorso completo o relativo alla posizione del file [!DNL flashtag.txt]. Ad esempio:

   ```
   var FLASHTAGURI = https://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. Aggiungi il seguente codice ActionScript a tutti gli eventi da tracciare. Questo codice rappresenta una chiamata di funzione utilizzata per acquisire dati sull&#39;evento:

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Questo esempio illustra l’utilizzo dell’evento on(release); tuttavia, è possibile fare riferimento alla funzione tag() attraverso qualsiasi evento che si desidera monitorare, ad esempio un evento on(press), on(rollover), on(rollout) o on(keypress).

   Il segnaposto \[[!DNL PUT_PAGE_NAME_HERE]\] deve essere sostituito da una stringa che rappresenta il nome della pagina o dell&#39;evento di cui si sta eseguendo il tracciamento. La variabile \[[!DNL PUT_PAGE_NAME_HERE]\]può essere modificata manualmente o tramite riferimento a una variabile per indicare un nome univoco per la pagina o l&#39;evento all&#39;interno dell&#39;applicazione [!DNL Flash]. Il valore che sostituisce il segnaposto \[[!DNL PUT_PAGE_NAME_HERE]\] può essere costituito da un nome semplice o strutturato in modo da rappresentare una struttura gerarchica simile a un URI completo. Ad esempio:

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   L&#39;Adobe consiglia di compilare una specifica scritta per i nomi di pagina e di evento prima della distribuzione del codice per facilitare l&#39;allineamento dei requisiti aziendali e delle attività di sviluppo e ridurre il potenziale di ulteriori cicli di sviluppo.

1. Se lo desideri, è possibile raccogliere variabili aggiuntive e associarle a pagine o eventi nel filmato [!DNL Flash]. A questo scopo, sostituisci il segnaposto \[[!DNL PUT_ADDITIONAL_VAR_HERE]\] con un set di coppie nome=valore separate da una e commerciale (&amp;). Ad esempio:

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   Le variabili possono essere modificate manualmente o tramite riferimento a variabili per indicare gli attributi aggiuntivi da raccogliere e associare alla pagina o all’evento. Se non ci sono variabili aggiuntive applicabili da raccogliere, rimuovi \[[!DNL PUT_ADDITIONAL_VAR_HERE]\].

   La configurazione del tracciamento dei visitatori all’interno di [!DNL Flash] contenuti rich media è ora completa. Quando si richiama l’evento , viene chiamata la funzione tag [!DNL (PAGENAME,VARIABLES)] , con conseguente richiesta HTTP per il file seguente. Questa funzione verrà chiamata in aggiunta ad altre funzioni che possono essere attivate come definito nel filmato [!DNL Flash]:

   ```
   https://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

La richiesta HTTP derivante dalla funzione [!DNL Flash] Tag ActionScript restituisce la raccolta delle seguenti informazioni rispetto a ogni evento all&#39;interno del filmato [!DNL Flash] . L’ultima riga della tabella (W3C Name cs-uri-query) rappresenta le informazioni raccolte per le variabili aggiuntive specificate nella chiamata della funzione.

<table id="table_A7ED9D38F36B4405947B2F48EA94D3C4">
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
   <td colname="col3"> Identificatore letto da un cookie inserito nel browser dell’utente da <span class="wintitle"> Sensor </span> sulla richiesta iniziale del visitatore </td>
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Data </p> <p>Tempo </p> </td>
   <td colname="col2"> Timestamp </td>
   <td colname="col3"> il momento in cui la richiesta è stata elaborata dal server (con precisione di 100 ns; la precisione dipende dall'ambiente del server e da NTP) </td>
   <td colname="col4"> 2002-11-21 17:21:45.123 </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-Type) </td>
   <td colname="col2"> Tipo di contenuto </td>
   <td colname="col3"> Tipo di oggetto restituito dal server </td>
   <td colname="col4"> Testo/html </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> Codice di stato della risposta HTTP </td>
   <td colname="col3"> Codice numerico generato dal server che prende nota dello stato della risposta del server HTTP </td>
   <td colname="col4"> 200 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> Stile URI </td>
   <td colname="col3"> La parte di stelo dell'URI richiesto dal client </td>
   <td colname="col4"> /flashtag/flashtag.txt </td>
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
   <td colname="col4"> www.mysite.com </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> URL di riferimento </td>
   <td colname="col3"> Contenuto del campo referente HTTP inviato dal client </td>
   <td colname="col4"></td>
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
   <td colname="col3"> La porzione, se presente, dell'URI richiesto dal client </td>
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td>
  </tr>
 </tbody>
</table>
