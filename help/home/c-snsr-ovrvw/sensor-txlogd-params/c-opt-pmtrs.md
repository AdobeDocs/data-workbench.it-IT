---
description: Informazioni sui parametri opzionali del file Sensor txlogd.conf.
title: Parametri opzionali
uuid: 8515a571-93ce-49cd-9ded-c9273259d0ee
exl-id: 5141f215-979c-4eb8-8c2c-94eef5815743
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 0%

---

# Parametri opzionali{#optional-parameters}

{{eol}}

Informazioni sui parametri opzionali del file Sensor txlogd.conf.

<table id="table_5FF491A7A6C24E43A06A5C344BF05430"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> FiltroIndirizzo </td> 
   <td colname="col2"> <p>Consente di filtrare gli indirizzi IP specificati. </p> <p>Quando si filtra un indirizzo particolare, un "pacchetto" non viene registrato. Questa funzione elimina gli agenti interni o monitorati prima dell'elaborazione del registro, aumentando così la velocità di elaborazione del registro e riducendo i requisiti di archiviazione dei dati. È possibile utilizzare i caratteri jolly quando si specificano gli indirizzi. </p> <p>Esempio: <span class="filepath"> Filtro indirizzi 10.0.0.000</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ContentFilterInclude </p> <p>ContentFilterExclude </p> </td> 
   <td colname="col2"> <p>Specifica se includere o escludere determinati tipi di contenuto dalla registrazione. </p> <p>I valori dei parametri corrispondono al tipo di contenuto della risposta. </p> <p>Ad esempio, "image/" corrisponde a tutti i tipi di contenuto immagine, mentre "image/gif" corrisponde esattamente a quel tipo. Quando si verificano più corrispondenze per un determinato tipo di contenuto, viene utilizzata la corrispondenza più specifica. Pertanto, è possibile inserire "image/gif" nel parametro ContentFilterInclude e "image/" nel parametro ContentFilterExclude e le risposte "image/gif" sono consentite, ma tutti gli altri tipi di immagine vengono filtrati. </p> <p>Esempio: <span class="filepath"> ContentFilterInclude *</span> </p> <p>Esempio: <span class="filepath"> ContentFilterExclude image/,text/css,application/x-javascript</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DebugLogPath </td> 
   <td colname="col2"> <p>Impostare questo parametro solo quando si lavora con Adobe Consulting Services. </p> <p>Abilita la registrazione di debug per il modulo web e il trasmettitore. </p> <p>Questo parametro viene utilizzato quando <span class="wintitle"> Sensore</span> non funziona correttamente. Dopo aver impostato questo parametro, devi creare un file vuoto nel percorso specificato e assegnargli i diritti di "scrittura" per tutti gli utenti. Ad esempio (all’interno di una shell unix sul server web): 
     <ul id="ul_7A067014A78048BF9D2F23DC66FF9E24"> 
      <li id="li_11C51EB9B9CC431585ECE9E8648F6122"><span class="filepath"> % cd /var/log</span> </li> 
      <li id="li_C56B2B5D49A543DBB258C5DE099B4AE5"><span class="filepath"> % touch vslog.txt</span> </li> 
      <li id="li_DA914383F813453AB6EF4F89279FD786"><span class="filepath"> % chmod a+w vslog.txt</span> </li> 
     </ul> </p> <p>Abilita la registrazione di debug solo per un breve periodo di tempo, dopo di che il file di log deve essere inviato ad Adobe Consulting Services per essere analizzato. </p> <p>Esempio: <span class="filepath"> DebugLogPath /var/log/vslog.txt</span> </p> <p>Adobe consiglia di impostare prima questo parametro in un ambiente di test per determinare l'effetto sul sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DisableField </td> 
   <td colname="col2"> <p>Disattiva il campo specificato </p> <p>Gli utenti possono eliminare i campi che non utilizzano o che non desiderano archiviare. Se il campo accetta valori di stringa, la disabilitazione passa una stringa vuota. Se il campo accetta valori numerici, la disattivazione passa il numero zero (0). Puoi disattivare i campi seguenti: 
     <ul id="ul_4537B345EFAE449A9946DA0B52EA5C43"> 
      <li id="li_D674BC1982344C49B25A73EFF095C34A">sc-status </li> 
      <li id="li_6D647C845EB54B1B84C756DCDD7DD4CC">x-new-visitor </li> 
      <li id="li_65EB695B223040BCB9888375354B6E8B">x-trackingid </li> 
      <li id="li_41197A9CB961496B9CD26AA8457233FD">sc-byte </li> 
      <li id="li_DCD45D7E21964B959299494FA719F453">c-ip </li> 
      <li id="li_7650796C6246484C8267ED9923596AFB">cs-method </li> 
      <li id="li_8941FCBBAA5E42EA9F04DA06EB91CAC5">cs-uri-stem </li> 
      <li id="li_A10438D2DEBB4ADFB574BF7094F9F0C4">cs-uri-query </li> 
      <li id="li_1D83BA59AC8543319D1966BB8ED1D931">s-dns </li> 
      <li id="li_34A23CE1944F4AEFBE7D74E8D6D5BEE6">cs(referrer) </li> 
      <li id="li_B85D93C381BD440F82C711C9A6D56CE9">cs(cookie) </li> 
      <li id="li_18D9C084450149D6A8713EBDA0C02E5B">cs(user-agent) </li> 
      <li id="li_A175CAF03E51473E990BE4F31F198B42">cs(useragent) </li> 
      <li id="li_ED38ED31B2644F2FA1C86FF93ADB9CEF">sc(tipo di contenuto) </li> 
      <li id="li_1173C0027C8A4638BDF35E9719CD9D4C">esperimento x </li> 
     </ul> </p> <p>Esempio: <span class="filepath"> DisableField x-trackingid</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpFile </td> 
   <td colname="col2"> <p>Percorso del file di configurazione dell'esperimento controllato. </p> <p>Esempio: <span class="filepath"> ExpFile C:\VisualSensor\experiment.txt</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpCookieURL </td> 
   <td colname="col2"> <p>Risorsa che, se richiesta, causa la generazione di un nuovo ID di tracciamento e l’inserimento dell’utente in un gruppo di esperimenti. </p> <p> <p>Nota: Questa risorsa non deve necessariamente esistere fisicamente sul server web. </p> </p> <p>Esempio: <span class="filepath"> ExpCookieURL /setcookie.htm</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpPartialMatch </td> 
   <td colname="col2"> <p>Se desideri abilitare gli esperimenti controllati per rimappare l’intero sito o un’intera sottodirectory del sito a un’altra posizione, imposta questo parametro su "on". Il valore predefinito è "off". </p> <p>Esempio: <span class="filepath"> ExpPartialMatch disattivato</span> </p> <p> <p>Nota: Presta molta attenzione quando imposti questo parametro su "on". </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LogAllNewUsers </td> 
   <td colname="col2"> <p>Determina se registrare il primo clic di ogni nuovo utente anche se l'utente richiede un tipo di documento filtrato dal parametro ContentFilterExclude. </p> <p>Il valore predefinito è "no". </p> <p>In genere i file immagine vengono filtrati dal parametro ContentFilterExclude. Se LogAllNewUsers è impostato su "yes" e il primo documento ottenuto da un nuovo utente dal server è un'immagine, la richiesta viene registrata. Se il parametro LogAllNewUsers è impostato su "no" o non è impostato affatto (e presupponendo che le immagini siano filtrate dal parametro ContentFilterExclude) e il primo documento ottenuto da un nuovo utente dal server è un'immagine, tale richiesta non viene registrata. </p> <p>Esempio: <span class="filepath"> LogAllNewUsers no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MaxPageLoadTime </td> 
   <td colname="col2"> <p>Il tempo in secondi che il trasmettitore attende di inviare il successivo batch di pacchetti. </p> <p>Il valore predefinito è 15. </p> <p>Esempio: <span class="filepath"> MaxPageLoadTime 15</span> </p> <p> <p>Nota: Non modificare questo valore del parametro senza prima contattare Adobe Consulting Services. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PrivacyID </td> 
   <td colname="col2"> <p>Consente di disabilitare il tracciamento dei visitatori, che può essere utilizzato per rispettare i criteri di rinuncia. </p> <p>Quando abilitato, <span class="wintitle"> Sensore</span> non registra un "pacchetto" per qualsiasi visitatore il cui cookie V1st è impostato sul PrivacyID specificato. Poiché non vengono registrate informazioni per tali visitatori, non vengono inviate informazioni su tali visitatori al <span class="keyword"> server di Data Workbench</span> per l'elaborazione. </p> <p>Per abilitare questa funzione, devi completare i seguenti passaggi: 
     <ol id="ol_5D658C5E4AB14F419029E0FFC52F1310"> 
      <li id="li_BF056439F92148169BF592731264C3CD"> PrivacyID deve essere definito con un valore pari a 0 (zero) nel <span class="filepath"> txlogd.conf</span> per <span class="wintitle"> Sensore</span>. <p>Esempio: <span class="filepath"> PrivacyID 0</span> </p> </li> 
      <li id="li_3E20F068C2F94512A92F284C80273B1C">I proprietari del sito web devono scrivere il codice per impostare i cookie del visitatore (V1st) in modo che il valore dell'ID cookie corrisponda al valore PrivacyID definito "<span class="filepath"> txlogd.conf</span>." </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SiteTest </td> 
   <td colname="col2"> <p>Posizione a cui il trasmettitore (txlogd) invia periodicamente richieste per vedere se il sito web funziona correttamente. </p> <p>Nota che la posizione è specificata nel formato seguente, non come URL: </p> <p>http<i>serverAddress,port,/resource</i> </p> <p>dove <i>serverAddress</i> è il nome del server o l'indirizzo IP, <i>porta</i> è la porta di ascolto HTTP del server, e <i>risorsa</i> è la risorsa specifica da richiedere (può includere una stringa di query). </p> <p>È possibile specificare più righe di SiteTest. </p> <p>Esempio: <span class="filepath"> SiteTest http,localhost,80,/test.html</span> </p> <p> <p>Nota: Al momento è supportato solo http. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackingCookie </td> 
   <td colname="col2"> <p>Nome del cookie impostato sul browser del visitatore. </p> <p>Il valore predefinito è "v1st". </p> <p>Esempio: <span class="filepath"> TrackingCookie v1st</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VerifyCertName </td> 
   <td colname="col2"> <p>Indica se convalidare il server in base al parametro CertName </p> <p>Il valore predefinito è "on". </p> <p>Esempio: <span class="filepath"> VerifyCertName su</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_598C3CDA5AA440228AF88C3BE4A8F77C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> IISCaptureBytesSent </td> 
   <td colname="col2"> <p>Impostare questo parametro solo quando si lavora con Adobe Consulting Services. </p> <p>Indica l'IIS <span class="wintitle"> Sensore</span> quale dei due possibili "ganci" di registrazione deve essere utilizzato per registrare un pacchetto </p> <p>Utilizza questo parametro quando IIS <span class="wintitle"> Sensore</span> non registra correttamente i pacchetti. Questo parametro viene impostato su "off" se il gancio di registrazione predefinito non funziona correttamente. Il valore predefinito è "on". </p> <p>Esempio: <span class="filepath"> IISCaptureBytesSent on</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IISUseAlternateHandler </td> 
   <td colname="col2"> <p>Impostare questo parametro solo quando si lavora con Adobe Consulting Services. </p> <p>Indica il <span class="wintitle"> Sensore</span> quale dei due possibili "ganci" deve essere utilizzato per impostare il cookie v1st. </p> <p>Questo parametro viene utilizzato quando si utilizza IIS <span class="wintitle"> Sensore</span> non imposta correttamente il cookie v1st. Questo parametro verrebbe impostato su "yes" se l'hook predefinito non impostava correttamente il cookie v1st. Il valore predefinito è "no". </p> <p>Esempio: <span class="filepath"> IISUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>Per impostazione predefinita, <span class="wintitle"> Sensore</span> invia intestazioni di risposta del controllo cache su ogni richiesta. Quando la funzione di controllo della cache è abilitata <span class="wintitle"> Sensore</span> invia un'intestazione Expires con un valore di Thu, 01 dic 1994 16:00:00 GMT al browser. </p> <p>Puoi modificare le stringhe di risposta come desiderato modificando le due righe seguenti nel <span class="filepath"> txlogd.conf</span> file: </p> <p> <span class="filepath"> NewUserCacheControl</span> <i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span> <i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>Esempio: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl privato,max-age=0,must-revalidate</span> </p> <p>Per disabilitare l’invio di intestazioni di risposta del controllo cache, digita un trattino per ogni riga come mostrato di seguito: </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_88696CCA93874BB683538BD614E07890"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> In questo parametro.. </th> 
   <th colname="col2" class="entry"> Specifica... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Impostare questo parametro solo quando si lavora con Adobe Consulting Services. </p> <p>Indica il <span class="wintitle"> Sensore</span> quale dei due possibili "ganci" deve essere utilizzato per impostare il cookie v1st. </p> <p>Usa questo parametro quando Apache <span class="wintitle"> Sensore</span> non imposta correttamente il cookie v1st. Questo parametro verrebbe impostato su "yes" se l'hook predefinito non impostava correttamente il cookie v1st. Il valore predefinito è "no". </p> <p>Esempio: <span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBothHandlers </td> 
   <td colname="col2"> <p>Impostare questo parametro solo quando si lavora con Adobe Consulting Services. </p> <p>incarica la <span class="wintitle"> Sensore</span> provare a impostare il cookie v1st in entrambi gli hook. </p> <p>Usa questo parametro quando Apache <span class="wintitle"> Sensore</span> non imposta correttamente il cookie v1st. Il valore predefinito è "sì". </p> <p>Se impostato su "yes" e il cookie v1st non è impostato correttamente nel primo gancio, viene utilizzato il secondo gancio. Se impostato su "no", imposterai il parametro ApacheUseAlternateHandler per indicare quale hook utilizzare per impostare il cookie v1st. </p> <p>Esempio: <span class="filepath"> ApacheUseBothHandlers sì</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>Per impostazione predefinita, <span class="wintitle"> Sensore</span> invia intestazioni di risposta del controllo cache su ogni richiesta. Quando la funzione di controllo della cache è abilitata <span class="wintitle"> Sensore</span> invia un'intestazione Expires con un valore di Thu, 01 dic 1994 16:00:00 GMT al browser. </p> <p>Puoi modificare le stringhe di risposta come desiderato modificando le due righe seguenti nel <span class="filepath"> txlogd.conf</span> file: </p> <p> <span class="filepath"> NewUserCacheControl</span> <i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span> <i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>Esempio: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl privato,max-age=0,must-revalidate</span> </p> <p>Per disabilitare l’invio di intestazioni di risposta del controllo cache, digita un trattino per ogni riga come mostrato di seguito: </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> <p> <p>Nota: Adobe consiglia di non disabilitare questa funzione. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_BF01F6265B8544DA9D9AD2C80A64C0F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> In questo parametro.. </th> 
   <th colname="col2" class="entry"> Specifica... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Impostare questo parametro solo quando si lavora con Adobe Consulting Services. </p> <p>Indica il <span class="wintitle"> Sensore</span> quale dei due possibili "ganci" deve essere utilizzato per impostare il cookie v1st. </p> <p>Usa questo parametro quando Apache <span class="wintitle"> Sensore</span> non imposta correttamente il cookie v1st. Questo parametro verrebbe impostato su "yes" se l'hook predefinito non impostava correttamente il cookie v1st. Il valore predefinito è "no". </p> <p>Esempio: <span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBothHandlers </td> 
   <td colname="col2"> <p>Impostare questo parametro solo quando si lavora con Adobe Consulting Services. </p> <p>incarica la <span class="wintitle"> Sensore</span> provare a impostare il cookie v1st in entrambi gli hook. </p> <p>Usa questo parametro quando Apache <span class="wintitle"> Sensore</span> non imposta correttamente il cookie v1st. Il valore predefinito è "sì". </p> <p>Se impostato su "yes" e il cookie v1st non è impostato correttamente nel primo gancio, viene utilizzato il secondo gancio. Se impostato su "no", imposterai il parametro ApacheUseAlternateHandler per indicare quale hook utilizzare per impostare il cookie v1st. </p> <p>Esempio: <span class="filepath"> ApacheUseBothHandlers sì</span> </p> </td> 
  </tr> 
 </tbody> 
</table>
