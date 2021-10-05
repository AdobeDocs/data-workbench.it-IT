---
description: Informazioni sui campi di dati che il server di Data Workbench può elaborare per creare un set di dati.
title: Campi record dati evento
uuid: b0232bfa-0a3b-4e3d-876e-6a15a3764eae
exl-id: 35433b87-991a-4fb9-ba6a-3217e89eb769
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 2%

---

# Campi record dati evento{#event-data-record-fields}

Informazioni sui campi di dati che il server di Data Workbench può elaborare per creare un set di dati.

* [Informazioni sui dati evento](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-3a0705f8c1824017aa4effed9903efbe)
* [Campi record dati evento linea di base](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-a882ed7aa6af41eeb45a55bf8c1ca3d7)
* [Campi derivati](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-b6c57ee2aa31469fbd5dab90e52bc677)

## Informazioni sui dati evento {#section-3a0705f8c1824017aa4effed9903efbe}

I dati evento utilizzati per creare un set di dati risiedono in file denominati origini di registro. I dati disponibili nelle origini di registro sono chiamati dati evento perché ogni record di dati rappresenta un record di transazione o una singola istanza di un evento con una marca temporale associata.

I dati evento di un’origine di registro vengono raccolti in tempo reale da [!DNL Sensors]. I dati evento raccolti da [!DNL Sensors] dai server HTTP e application vengono trasmessi ai server di Data Workbench, che convertono i dati in file di log compressi ( [!DNL .vsl]). I dati evento contenuti in un file flat, in un file XML o in un’origine dati ODBC vengono letti dal server di Data Workbench, che fornisce decodificatori definiti per estrarre un set comune di campi dati da questi diversi formati.

Le sezioni seguenti forniscono informazioni sui campi dati (denominati campi record dati evento o campi voce registro ) raccolti da [!DNL Sensors] oppure letti e resi disponibili al server di Data Workbench.

>[!NOTE]
>
>I nomi dei campi generalmente seguono la convenzione di denominazione per il formato di file di registro esteso W3C. In molti campi sono presenti prefissi che indicano l’origine delle informazioni contenute nel campo:

* cs indica la comunicazione dal client al server.
* sc indica la comunicazione dal server al client.
* s indica le informazioni provenienti dal server.
* c indica le informazioni provenienti dal client.
* x indica le informazioni create da un prodotto software di Adobe.

## Campi record dati evento linea di base {#section-a882ed7aa6af41eeb45a55bf8c1ca3d7}

I file di registro ( [!DNL .vsl]) contengono i campi dei dati evento raccolti dai server da [!DNL Sensors] e utilizzati dal server di Data Workbench nel processo di costruzione del set di dati. Nella tabella seguente sono elencati i campi di un record di dati evento tipico registrato da [!DNL Sensor]:

<table id="table_98E135FE4EAF44D6ADEB3C6C1C0BF6A4">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Campo </th>
   <th colname="col2" class="entry"> Descrizione </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> c-ip </td>
   <td colname="col2"> <p>Indirizzo IP del client incluso nella richiesta effettuata al server. </p> <p> Esempio: 207.68.146.68 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> <p>I cookie inviati dal client con la richiesta . </p> <p> Esempio: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFFIPLOJMKCAAEPM; </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> <p>Stringa di riferimento HTTP inviata dal client al server con la richiesta. </p> <p> Esempio: <span class="filepath"> https://www.mysite.net/cgi-bin/websearch?qry </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> <p>Stringa inviata dal client con la relativa richiesta al server che indica il tipo di agente utente del client. </p> <p> Esempio: Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-method </td>
   <td colname="col2"> <p>Il tipo di metodo della richiesta HTTP. </p> <p> Esempio: GET </p> <p> Riferimento: <span class="filepath"> https://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> <p>La porzione della stringa di query dell’URI (stem + stringa di query = URI). Questo è preceduto da un punto interrogativo (?) e può contenere una o più coppie nome-valore separate da e commerciale (&amp;). </p> <p> Esempio: page=homepage </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> <p>La porzione di gambo dell’URI (stem + stringa di query = URI). Lo stelo è il percorso effettivo o logico della risorsa richiesta sul server. </p> <p> Esempio: <span class="filepath"> /index.asp </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc(tipo di contenuto) </td>
   <td colname="col2"> <p>Il tipo di contenuto della risorsa richiesta dal client come segnalato dal server. </p> <p> Esempi: text/html, image/png, image/gif, video/mpeg </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-byte </td>
   <td colname="col2"> <p>Numero di byte di dati inviati dal server al client in risposta alla richiesta </p> <p> Esempio: 4996 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> <p>Codice di stato restituito al client dal server. </p> <p> Esempio: 200 </p> <p> Riferimento: <span class="filepath"> https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> <p>Il nome di dominio o l'indirizzo IP completo dell'host della risorsa richiesta. </p> <p> Esempio: <span class="filepath"> www.adobe.com </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> esperimento x </td>
   <td colname="col2"> <p>Elenco di tutti i nomi e i gruppi di esperimenti controllati di cui il cliente è membro al momento della richiesta. </p> <p> Esempio: VSHome_Exp.Group_1,VSRegistration_Exp.Group_2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-timestamp </td>
   <td colname="col2"> <p>Data e ora (GMT) in cui la richiesta è stata ricevuta dal server. Il tempo è espresso come numero di 100 nanosecondi dal 1° gennaio 1600. </p> <p> Esempio: 127710989320000000 è il valore x-timestamp per 11:28:52.0000000 di martedì 13 settembre 2005. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> <p>Il valore esadecimale a 64 bit dell'identificatore univoco del browser trovato in un cookie persistente impostato da un <span class="wintitle"> Sensor </span> e fornito dal client con una richiesta a un server. </p> <p> Esempio: 42FDF66DE610CF36 </p> </td>
  </tr>
 </tbody>
</table>

## Campi derivati {#section-b6c57ee2aa31469fbd5dab90e52bc677}

Nella tabella seguente sono riportati alcuni esempi di campi derivati dal server di Data Workbench dai campi del record dati evento linea di base:

<table id="table_3B008F1314804A69AE69E8F94908F497">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Campo </th>
   <th colname="col2" class="entry"> Descrizione </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> cs(cookie)(name) </td>
   <td colname="col2"> Il valore di una coppia nome-valore specificata all'interno di un cookie. </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer-domain) </td>
   <td colname="col2"> <p>Nome di dominio o indirizzo IP dell’URI di riferimento HTTP. </p> <p> <p>Nota:  Questo campo è di sola lettura. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer-host) </td>
   <td colname="col2"> <p>L'intero nome host del referrer. </p> <p> Esempio: Se cs(referrer) è <span class="filepath"> https://my.domain.com/my/page </span>, cs(referrer-host) è <span class="filepath"> my.domain.com </span>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer-query)(name) </td>
   <td colname="col2"> <p>Il valore di una stringa di query referrer. </p> <p> <p>Nota:  Non è possibile accedere a un valore della stringa di query referrer utilizzando il campo cs(referrer)(name) . </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri </td>
   <td colname="col2"> <p>URI completo (stelo + stringa di query = intero URI). </p> <p> Esempio: <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query(name) </td>
   <td colname="col2"> <p>Il valore associato al nome specificato. Se esistono più valori per il nome specificato, questo campo restituisce l'ultimo di tali valori. </p> Esempi:
    <ul id="ul_47BBB2E3076A46629BFCDB2A460F700B">
     <li id="li_AC9BB29505A54AE4AFF49438530C9EA4"> Per l’URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span>, cs-uri-query(product3) restituirà cd. </li>
     <li id="li_B036C1D0B25748E0A155DDC9B1B999CB"> Per l’URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product1=casette </span>, <span class="wintitle"> cs-uri-query(product1) </span> restituirebbe una casetta. </li>
    </ul> <p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ctime </td>
   <td colname="col2"> x-timestamp espresso in secondi dal 1° gennaio 1970. Questo campo è anche chiamato x-unixtime. </td>
  </tr>
  <tr>
   <td colname="col1"> data </td>
   <td colname="col2"> x-timestamp in formato AAAA-MM-GG. </td>
  </tr>
  <tr>
   <td colname="col1"> time </td>
   <td colname="col2"> x-timestamp in formato HH:MM:SS. </td>
  </tr>
  <tr>
   <td colname="col1"> x-local-timestring </td>
   <td colname="col2"> <p>x-timestamp convertito nel fuso orario locale specificato nel file <span class="filepath"> Transformation.cfg </span> per il set di dati. Il formato è AAAA-MM-GG HH:MM:SS.mmm. </p> <p> <p>Nota:  Puoi anche definire conversioni temporali come x-local-timestring nel file <span class="filepath"> Log Processing.cfg </span> . Per informazioni, vedere <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> File di configurazione dell’elaborazione del registro </a>. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-log-source-id </td>
   <td colname="col2"> <p>Identificatore corrispondente all'origine del registro per una particolare voce di registro. Affinché l'identificatore possa essere registrato, è necessario specificarlo nel campo <span class="wintitle"> ID origine registro </span> del file <span class="filepath"> Log Processing.cfg </span> quando si definisce <span class="wintitle"> Sensore </span>, file di registro o origini dati ODBC. Per ulteriori informazioni, vedere <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> File di configurazione dell’elaborazione del registro </a>. </p> <p> Esempio: da VSensor01. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-mask </td>
   <td colname="col2"> Il pattern della maschera delle origini dati <span class="wintitle"> Sensor </span> (derivate dai nomi di file <span class="filepath"> .vsl </span>). Per un file il cui nome è del formato <span class="filepath"> YYYYMMDD-SENSORID.VSL </span>, x-mask è SENSORID. </td>
  </tr>
  <tr>
   <td colname="col1"> x-timestamp </td>
   <td colname="col2"> x-timestamp in formato AAAA-MM-GG HH:MM:SS.mmm. </td>
  </tr>
  <tr>
   <td colname="col1"> x-unixtime </td>
   <td colname="col2"> Tempo UNIX decimale derivato da x-timestamp. </td>
  </tr>
 </tbody>
</table>

[!DNL Sensor], se utilizzato su un server, può raccogliere i campi dei dati evento da qualsiasi intestazione o variabile di richiesta o risposta HTTP valida disponibile tramite l’API del server. Per raccogliere tali campi di dati, devi specificare i campi di intestazione o le variabili desiderate nel file di configurazione [!DNL txlogd.conf]per [!DNL Sensor]. Per ulteriori informazioni, vedere la *Guida alla Data Workbench [!DNL Sensor]*.
