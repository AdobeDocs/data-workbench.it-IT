---
description: I siti Web creati con Flash richiedono particolare attenzione per l’acquisizione delle azioni dei visitatori all’interno del contenuto multimediale.
solution: Analytics
title: Tracciamento delle attività dei visitatori all’interno dei contenuti Flash multimediali
topic: Data workbench
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
translation-type: tm+mt
source-git-commit: 48892b1b4fc9e9fdeacee8ca318025f43f2d0064

---


# Tracciamento delle attività dei visitatori all’interno dei contenuti Flash multimediali{#tracking-visitor-activity-within-flash-rich-media-content}

I siti Web creati con Flash richiedono particolare attenzione per l’acquisizione delle azioni dei visitatori all’interno del contenuto multimediale.

Utilizzando [!DNL Flash] [!DNL Flash] ActionScript, potete apportare semplici modifiche ai filmati esistenti per consentire il tracciamento di tutte le interazioni dei visitatori con il filmato, ad esempio clic di un pulsante o movimenti del mouse.

Per facilitare il tracciamento dell&#39;attività dei visitatori all&#39;interno del [!DNL Flash] filmato, segui i passaggi elencati di seguito:

1. Aggiungete il seguente codice ActionScript al filmato. Questo codice rappresenta una funzione che può essere richiamata dagli eventi all&#39;interno del [!DNL Flash] filmato che si desidera tracciare.

   ```
   // FLASH TAG CODE BEGIN 
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt"; 
   function tag(PAGENAME,VARIABLES) { 
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0); 
   } 
   // FLASH TAG CODE END
   ```

1. Create un file vuoto denominato [!DNL flashtag.txt] e inserite il file sui server Web.
1. Nella funzione del passaggio 1, sostituire il segnaposto \[[!DNL PATH_TO_WEB_SERVER]\] con il percorso completo o relativo alla posizione del [!DNL flashtag.txt] file. Ad esempio:

   ```
   var FLASHTAGURI = http://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. Aggiungete il seguente codice ActionScript a tutti gli eventi da monitorare. Questo codice rappresenta una chiamata di funzione utilizzata per acquisire i dati sull&#39;evento:

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Questo esempio illustra l&#39;utilizzo dell&#39;evento on(release); tuttavia, è possibile fare riferimento alla funzione tag() attraverso qualsiasi evento che si desidera monitorare, ad esempio un evento on(press), on(rollover), on(rollout) o on(keypress).

   Il segnaposto \[[!DNL PUT_PAGE_NAME_HERE]\] deve essere sostituito con una stringa che rappresenta il nome della pagina o dell&#39;evento da tracciare. La variabile \[[!DNL PUT_PAGE_NAME_HERE]\] può essere modificata manualmente o mediante un riferimento di variabile per indicare un nome univoco per la pagina o l&#39;evento all&#39;interno dell&#39; [!DNL Flash] applicazione. Il valore che sostituisce il segnaposto \[[!DNL PUT_PAGE_NAME_HERE]\] può essere costituito da un nome semplice o strutturato in modo da rappresentare una struttura gerarchica simile a un URI completo. Ad esempio:

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe consiglia di compilare, prima della distribuzione del codice, una specifica scritta per i nomi delle pagine e gli eventi, in modo da facilitare l&#39;allineamento dei requisiti aziendali e delle attività di sviluppo e ridurre il potenziale per ulteriori cicli di sviluppo.

1. Se necessario, è possibile raccogliere ulteriori variabili e associarle alle pagine o agli eventi del [!DNL Flash] filmato. A questo scopo, sostituite il segnaposto \[[!DNL PUT_ADDITIONAL_VAR_HERE]\] con un set di coppie nome=valore separate da una e commerciale (&amp;). Ad esempio:

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   Le variabili possono essere modificate manualmente o mediante un riferimento variabile per indicare gli attributi aggiuntivi da raccogliere e associare alla pagina o all’evento. Se non sono presenti variabili aggiuntive applicabili da raccogliere, rimuovete \[[!DNL PUT_ADDITIONAL_VAR_HERE]\].

   La configurazione del tracciamento dei visitatori all&#39;interno dei contenuti [!DNL Flash] multimediali avanzati è ora completa. Quando l&#39;evento viene richiamato, viene chiamata la [!DNL (PAGENAME,VARIABLES)] funzione tag, con conseguente richiesta HTTP per il file seguente. Questa funzione viene chiamata in aggiunta ad altre funzioni che possono essere attivate come definito nel [!DNL Flash] filmato:

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

La richiesta HTTP derivante dalla funzione [!DNL Flash] Tag ActionScript genera la raccolta delle seguenti informazioni relative a ciascun evento all&#39;interno del [!DNL Flash] filmato. L&#39;ultima riga della tabella (W3C Name cs-uri-query) rappresenta le informazioni raccolte per le variabili aggiuntive specificate nella chiamata della funzione.

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
   <td colname="col3"> Identificatore letto da un cookie inserito nel browser dell'utente dal <span class="wintitle"> sensore </span> nella richiesta iniziale del visitatore </td> 
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td> 
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
   <td colname="col4"> Testo/html </td> 
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
   <td colname="col2"> Nome dominio server </td> 
   <td colname="col3"> Nome di dominio del server Web che elabora la richiesta </td> 
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
   <td colname="col2"> Stringa query </td> 
   <td colname="col3"> Eventuale porzione della stringa di query dell’URI richiesto dal client </td> 
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td> 
  </tr> 
 </tbody> 
</table>

