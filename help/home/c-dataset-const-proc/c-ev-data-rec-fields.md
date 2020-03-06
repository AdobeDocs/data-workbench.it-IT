---
description: Informazioni sui campi di dati che il server workbench dati può elaborare per creare un dataset.
solution: Analytics
title: Campi record dati evento
topic: Data workbench
uuid: b0232bfa-0a3b-4e3d-876e-6a15a3764eae
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Campi record dati evento{#event-data-record-fields}

Informazioni sui campi di dati che il server workbench dati può elaborare per creare un dataset.

* [Informazioni sui dati evento](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-3a0705f8c1824017aa4effed9903efbe)
* [Campi record dati evento baseline](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-a882ed7aa6af41eeb45a55bf8c1ca3d7)
* [Campi derivati](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-b6c57ee2aa31469fbd5dab90e52bc677)

## Informazioni sui dati evento {#section-3a0705f8c1824017aa4effed9903efbe}

I dati evento utilizzati per creare un dataset risiedono in file denominati origini di registro. I dati disponibili nelle origini del registro sono denominati dati evento perché ogni record di dati rappresenta un record di transazione o una singola istanza di un evento con una marca temporale associata.

I dati evento di un&#39;origine di registro vengono raccolti in tempo reale da [!DNL Sensors]. I dati degli eventi raccolti dai server [!DNL Sensors] HTTP e applicazioni vengono trasmessi ai server workbench dati, che convertono i dati in file di registro compressi ( [!DNL .vsl]). I dati evento contenuti in un file semplice, in un file XML o in un&#39;origine dati ODBC vengono letti dal server workbench dati, che fornisce i decodificatori definiti dall&#39;utente per estrarre un set comune di campi dati da questi diversi formati.

Le sezioni seguenti forniscono informazioni sui campi dati (denominati campi record di dati evento o campi voce di registro) raccolti da [!DNL Sensors] o letti e resi disponibili al server workbench dati.

>[!NOTE]
>
>I nomi dei campi generalmente seguono le convenzioni di denominazione per il formato di file di registro esteso W3C. Molti campi presentano prefissi che indicano l&#39;origine delle informazioni contenute nel campo:

* cs indica la comunicazione dal client al server.
* sc indica la comunicazione dal server al client.
* s indica le informazioni provenienti dal server.
* c indica informazioni dal client.
* x indica le informazioni create da un prodotto software Adobe.

## Campi record dati evento baseline {#section-a882ed7aa6af41eeb45a55bf8c1ca3d7}

I file di registro ( [!DNL .vsl]) contengono i campi dei dati evento raccolti dai server [!DNL Sensors] e utilizzati dal server workbench dati nel processo di costruzione del dataset. La tabella seguente elenca i campi in un record di dati evento tipico come registrato da [!DNL Sensor]:

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
   <td colname="col2"> <p>L'indirizzo IP del client incluso nella richiesta inviata al server. </p> <p> Esempio: 207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>I cookie inviati dal client con la richiesta. </p> <p> Esempio: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFIPLOJMKCAAEPM; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> <p>Stringa di riferimento HTTP inviata dal client al server con la richiesta. </p> <p> Esempio: <span class="filepath"> http://www.mysite.net/cgi-bin/websearch?qry </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>Stringa inviata dal client con la richiesta al server che indica il tipo di agente utente del client. </p> <p> Esempio: Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>Il tipo di metodo della richiesta HTTP. </p> <p> Esempio: GET </p> <p> Riferimento: <span class="filepath"> http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>Parte della stringa di query dell'URI (stem + stringa di query = URI). Questo è preceduto da un punto interrogativo (?) e può contenere una o più coppie nome-valore separate da e commerciale (&amp;). </p> <p> Esempio: page=homepage </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> <p>La parte di stelo dell'URI (stem + stringa query = URI). L'origine è il percorso effettivo o logico della risorsa richiesta sul server. </p> <p> Esempio: <span class="filepath"> /index.asp </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>Il tipo di contenuto della risorsa richiesta dal client, come segnalato dal server. </p> <p> Esempi: text/html, image/png, image/gif, video/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-byte </td> 
   <td colname="col2"> <p>Numero di byte di dati inviati dal server al client in risposta alla richiesta </p> <p> Esempio: 4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>Il codice di stato restituito al client dal server. </p> <p> Esempio: 200 </p> <p> Riferimento: <span class="filepath"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>Il nome di dominio completo o l'indirizzo IP dell'host della risorsa richiesta. </p> <p> Esempio: <span class="filepath"> www.adobe.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-esperimento </td> 
   <td colname="col2"> <p>L'elenco di tutti i nomi e i gruppi controllati di cui il cliente è membro al momento della richiesta. </p> <p> Esempio: VSHome_Exp.Group_1,VSRegistration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>Data e ora (GMT) in cui la richiesta è stata ricevuta dal server. Il tempo è espresso come numero di 100 nanosecondi dal 1 gennaio 1600. </p> <p> Esempio: 127710989320000000 corrisponde al valore x-timestamp per 11:28:52.0000000 di martedì 13 settembre 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>Il valore esadecimale a 64 bit dell’identificatore univoco del browser trovato in un cookie persistente impostato da un <span class="wintitle"> sensore </span> e fornito dal client con una richiesta a un server. </p> <p> Esempio: 42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Campi derivati {#section-b6c57ee2aa31469fbd5dab90e52bc677}

Nella tabella seguente sono riportati alcuni esempi di campi derivati dal server workbench dati dai campi record dei dati evento baseline:

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
   <td colname="col2"> <p>Il nome di dominio o l'indirizzo IP dell'URI di provenienza HTTP. </p> <p> <p>Nota:  Questo campo è di sola lettura. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-host) </td> 
   <td colname="col2"> <p>L’intero nome host del referente. </p> <p> Esempio: Se cs(referrer) è <span class="filepath"> http://my.domain.com/my/page </span>, cs(referrer-host) è <span class="filepath"> my.domain.com </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-query)(name) </td> 
   <td colname="col2"> <p>Il valore di una stringa di query del referente. </p> <p> <p>Nota:  Non è possibile accedere al valore di una stringa di query del referente utilizzando il campo cs(referrer)(name). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri </td> 
   <td colname="col2"> <p>URI completo (stem + stringa query = intero URI). </p> <p> Esempio: <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query(name) </td> 
   <td colname="col2"> <p>Il valore associato al nome specificato. Se per il nome specificato esistono più valori, questo campo restituisce l'ultimo di tali valori. </p> Esempi: 
    <ul id="ul_47BBB2E3076A46629BFCDB2A460F700B"> 
     <li id="li_AC9BB29505A54AE4AFF49438530C9EA4"> Per l’URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span>, cs-uri-query(product3) restituirebbe cd. </li> 
     <li id="li_B036C1D0B25748E0A155DDC9B1B999CB"> Per l’URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product1=casette </span>, <span class="wintitle"> cs-uri-query(product1) </span> restituisce una casetta. </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ctime </td> 
   <td colname="col2"> x-timestamp espresso in secondi dal 1 gennaio 1970. Questo campo è anche chiamato x-unixtime. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> date </td> 
   <td colname="col2"> x-timestamp nel formato AAAA-MM-GG. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> time </td> 
   <td colname="col2"> x-timestamp nel formato HH:MM:SS. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-local-timestring </td> 
   <td colname="col2"> <p>x-timestamp convertito nel fuso orario locale specificato nel file <span class="filepath"> Transformation.cfg </span> per il dataset. Il formato è AAAA-MM-GG HH:MM:SS.mmm. </p> <p> <p>Nota:  È inoltre possibile definire conversioni temporali, ad esempio x-local-timestring nel file <span class="filepath"> Log Processing.cfg </span> . Per ulteriori informazioni, vedere <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> File di configurazione Elaborazione log </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-log-source-id </td> 
   <td colname="col2"> <p>Identificatore corrispondente all’origine del registro per una particolare voce di registro. Per registrare l'identificatore, è necessario specificarlo nel campo ID origine <span class="wintitle"> log </span> del file <span class="filepath"> Log Processing.cfg </span> quando si definisce <span class="wintitle"> Sensor </span>, file di registro o origini dati ODBC. Per ulteriori informazioni, vedere <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> File di configurazione Elaborazione log </a>. </p> <p> Esempio: da VSensor01. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-mask </td> 
   <td colname="col2"> Il pattern della maschera delle origini dati <span class="wintitle"> Sensor </span> (derivato dai nomi dei file <span class="filepath"> .vsl </span> ). Per un file il cui nome è nel formato <span class="filepath"> YYYYMMDD-SENSORID.VSL </span>, x-mask è SENSORID. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestring </td> 
   <td colname="col2"> x-timestamp nel formato AAAA-MM-GG HH:MM:SS.mmm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-unixtime </td> 
   <td colname="col2"> Tempo UNIX decimale derivato da x-timestamp. </td> 
  </tr> 
 </tbody> 
</table>

[!DNL Sensor], se utilizzato su un server, può raccogliere i campi dei dati evento da qualsiasi richiesta HTTP o intestazione di risposta o variabile valida a esso disponibile tramite l&#39;API del server. Per raccogliere tali campi di dati, è necessario specificare i campi di intestazione o le variabili desiderate nel file di [!DNL txlogd.conf]configurazione per [!DNL Sensor]. For more information, see the *Data Workbench[!DNL Sensor]Guide*.
