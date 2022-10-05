---
description: Informazioni sui campi di record dei dati dell’evento della linea di base registrati dal Sensor.
title: Campi record dati evento linea di base
uuid: aa36d332-089c-4ae2-98e2-a93d2fa023b7
exl-id: ad3d8806-863a-4871-a35b-6680163f00ac
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 2%

---

# Campi record dati evento linea di base{#baseline-event-data-record-fields}

{{eol}}

Informazioni sui campi di record dei dati dell’evento della linea di base registrati dal Sensor.

<table id="table_E29606BB010E4DB48C463979B7BEC769">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Campo </th>
   <th colname="col2" class="entry"> Descrizione </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> c-ip </td>
   <td colname="col2"> <p>Indirizzo IP del client incluso nella richiesta effettuata al server. </p> <p>Esempio: 207.68.146.68 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> <p>I cookie inviati dal client con la richiesta . </p> <p>Esempio: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFFIPLOJMKCAAEPM; </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> <p>Stringa di riferimento HTTP inviata dal client al server con la richiesta. </p> <p>Esempio: https://www.mysite.net/cgi-bin/websearch?qry </p> <p>Se utilizzi i tag pagina, cs(referrer) è l’URL completo del documento contenente l’immagine tag, compresi HTTP o HTTP. </p> <p>Inoltre, puoi configurare i sensori Apache (1.3, 2.0 e 2.2) e IIS per acquisire la porta utilizzata per la richiesta, che può identificare le richieste HTTP rispetto a HTTPS. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> <p>Stringa inviata dal client con la relativa richiesta al server che indica il tipo di agente utente del client. </p> <p>Esempio: Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-method </td>
   <td colname="col2"> <p>Tipo di metodo della richiesta HTTP </p> <p>Esempio: GET </p> <p>Riferimento: https://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> <p>Parte della stringa di query dell’URI (stem + stringa di query = URI) </p> <p>Questo è preceduto da un punto interrogativo (?) e può contenere una o più coppie nome-valore separate da e commerciale (&amp;). </p> <p>Esempio: page=homepage </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> <p>La parte di stelo dell’URI (stelo + stringa di query = URI) </p> <p>Lo stelo è il percorso effettivo o logico della risorsa richiesta sul server. </p> <p>Esempio: /index.asp </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc(tipo di contenuto) </td>
   <td colname="col2"> <p>Il tipo di contenuto della risorsa richiesta dal client come segnalato dal server. </p> <p>Esempi: text/html, image/png, image/gif, video/mpeg </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-byte </td>
   <td colname="col2"> <p>Il numero di byte di dati inviati dal server al client in risposta alla richiesta. </p> <p>Esempio: 4996 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> <p>Codice di stato restituito al client dal server. </p> <p>Esempio: 200 </p> <p>Riferimento: https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </p> </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> <p>Il nome di dominio o l'indirizzo IP completo dell'host della risorsa richiesta. </p> <p>Esempio: www.omniture.com </p> </td>
  </tr>
  <tr>
   <td colname="col1"> esperimento x </td>
   <td colname="col2"> <p>Elenco di tutti i nomi e i gruppi di esperimenti controllati di cui il cliente è membro al momento della richiesta. </p> <p>Esempio: Home_Exp.Group_1,Registration_Exp.Group_2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-timestamp </td>
   <td colname="col2"> <p>Data e ora (GMT) in cui la richiesta è stata ricevuta dal server. </p> <p>Il tempo è espresso come numero di 100 nanosecondi dal 1° gennaio 1600. </p> <p>Esempio: 127710989320000000 è il valore x-timestamp per 11:28:52.0000000 martedì 13 settembre 2005. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> <p>Il valore esadecimale a 64 bit dell'identificatore univoco del browser trovato in un cookie persistente impostato da un <span class="wintitle"> Sensore </span> e fornito dal client con una richiesta a un server. </p> <p>Esempio: 42FDF66DE610CF36 </p> </td>
  </tr>
 </tbody>
</table>

La [!DNL data workbench server] può ricavare una serie di variabili dai campi dei record dei dati evento della linea di base. Per ulteriori informazioni, consulta la sezione *Guida alla configurazione del set di dati*.
