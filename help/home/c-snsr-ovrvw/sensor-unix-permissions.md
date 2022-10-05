---
description: Informazioni sulle autorizzazioni del file UNIX di Sensor come il modulo di raccolta, il processo del trasmettitore, il file di configurazione e altro ancora.
title: Autorizzazioni del file UNIX di Sensor
uuid: 04d159b5-6569-48b6-a2db-9a0b40118ffe
exl-id: 07cbc7df-c628-437d-9ca1-b006da8de242
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 3%

---

# Autorizzazioni del file UNIX di Sensor{#sensor-unix-file-permissions}

{{eol}}

Informazioni sulle autorizzazioni del file UNIX di Sensor come il modulo di raccolta, il processo del trasmettitore, il file di configurazione e altro ancora.

## Il modulo di raccolta {#section-49c855baece24c4695184bfcbeeddebf}

<table id="table_0B972ABD2A5342CA8A6FE80EB666298A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualità </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nome file </p> </td> 
   <td colname="col2"> <p>mod_visual_sciences.so (su server web Apache e server HTTP IBM) </p> <p>libvisual_sciences.so e J2EECollector.jar (su server di applicazioni J2EE) </p> <p>aol_visual_sciences.so (su server web AOL) </p> <p>saf_visual_sciences.so (su server web Sun Java) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorizzazioni predefinite </p> </td> 
   <td colname="col2"> <p>rwx r-x r-x (IBM HTTP e Apache 1.3.x) </p> <p>rwx rwx r-x (Apache 2.0.x) </p> <p>rwx —x —x (server web J2EE, AOL e Sun Java) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Leggi da </p> </td> 
   <td colname="col2"> <p>Il server web, che a volte viene eseguito come utente principale, ma più spesso viene eseguito con un account utente specifico </p> <p>Se il server web viene eseguito con un account non root, le autorizzazioni su questo file devono consentire a tale account di leggerlo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Viene eseguito come </p> </td> 
   <td colname="col2"> <p>Un processo figlio nel server web </p> <p>I processi secondari vengono eseguiti con un account utente specificato nella configurazione del server web. Su molti server, questo è un account speciale con privilegi molto limitati chiamato "nessuno" — ma non tutti i server web utilizzano questo account. Controlla il file di configurazione del server web per determinare quale account utente è impostato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Letture da </p> </td> 
   <td colname="col2"> <p>txlogd.conf </p> <p>File diskQueue </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scrive in </td> 
   <td colname="col2"> File diskQueue </td> 
  </tr> 
 </tbody> 
</table>

## Il processo del trasmettitore {#section-8af432472e9d4bd9a42270bf27adf33a}

<table id="table_3028CC9640D54016BD8CA7F9CAA34280"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualità </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome file </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorizzazioni predefinite </p> </td> 
   <td colname="col2"> <p>rw- r— r— (server web IBM HTTP, AOL e Sun Java) </p> <p>rw- rw- r— (server web Apache e server applicativi J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Leggi da </td> 
   <td colname="col2"> Il programma del trasmettitore </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scritto da </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## Il file di configurazione {#section-341d85f2abf34a69970a0ff91b7e9123}

<table id="table_79AC614F5435443CB3CFB457B8375704"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualità </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome file </td> 
   <td colname="col2"> txlogd.conf </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorizzazioni predefinite </p> </td> 
   <td colname="col2"> <p>rw- r— r— (server web IBM HTTP, AOL e Sun Java) </p> <p>rw- rw- r— (server web Apache e server applicativi J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Leggi da </td> 
   <td colname="col2"> <p>Modulo di raccolta </p> <p>Il programma del trasmettitore </p> <p>Amministratore responsabile dell'installazione, della configurazione e della manutenzione del sensore </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scritto da </td> 
   <td colname="col2"> Amministratore responsabile dell'installazione, della configurazione e della manutenzione del sensore </td> 
  </tr> 
 </tbody> 
</table>

## File dell’autorità di certificazione {#section-2818dff887b8456992bdc589fd8510f3}

<table id="table_ED8BEEEFA91245C3A6645D27B148A5A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualità </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome file </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorizzazioni predefinite </p> </td> 
   <td colname="col2"> <p>rw- r— r— (server web IBM HTTP, AOL e Sun Java) </p> <p>rw- rw- r— (server web Apache e server applicativi J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Leggi da </td> 
   <td colname="col2"> Il programma del trasmettitore </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scritto da </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## Coda disco {#section-0407c52744de41af867d0b7933a69256}

<table id="table_35DB32228E7443FF90BE24AB14CBE54B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualità </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome file </td> 
   <td colname="col2"> Definito dall'utente </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Autorizzazioni predefinite </td> 
   <td colname="col2"> rw- rw- rw- (tutti i tipi di server) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Leggi da </p> </td> 
   <td colname="col2"> <p>Modulo di raccolta </p> <p>Il programma del trasmettitore </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scritto da </p> </td> 
   <td colname="col2"> <p>Modulo di raccolta </p> <p>Il programma del trasmettitore </p> </td> 
  </tr> 
 </tbody> 
</table>
