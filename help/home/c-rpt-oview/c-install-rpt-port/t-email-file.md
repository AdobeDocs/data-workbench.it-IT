---
description: L'accesso e le autorizzazioni all'interno del Report Portal (Portale dei rapporti) sono controllate utilizzando account utente e di gruppo singoli.
title: Modificare il file Email.asp
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
exl-id: e984f12f-362a-4dee-9af3-6d7a38a178a4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 2%

---

# Modificare il file Email.asp{#edit-the-email-asp-file}

L&#39;accesso e le autorizzazioni all&#39;interno del Report Portal (Portale dei rapporti) sono controllate utilizzando account utente e di gruppo singoli.

Ogni volta che aggiungi un nuovo account o ne modifichi uno esistente, puoi inviare un messaggio e-mail di conferma all’indirizzo e-mail specificato per tale account (consulta [Utilizzo degli account](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)) e copiarlo negli indirizzi e-mail specificati nel file [!DNL email.asp] .

>[!NOTE]
>
>Le e-mail di notifica vengono inviate agli utenti dell’account solo quando hai specificato un indirizzo e-mail per l’account e hai configurato correttamente il file [!DNL email.asp] . Se non desideri inviare e-mail di notifica per un account, lascia vuoto il campo e-mail dell’account.

Questo file si trova nella cartella `\*PortalName*\PortalASP`.

1. Sul computer in cui è in esecuzione IIS, apri il file [!DNL email.asp] in un editor di testo come Blocco note.
1. Imposta le seguenti variabili:

<table id="table_44F52DA266364DF993C40678A28E0F0D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questa variabile . . . </th> 
   <th colname="col2" class="entry"> Fornisci queste informazioni . . . </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> smtpserver </td> 
   <td colname="col2"> <p>Nome DNS o indirizzo IP del server SMTP attraverso il quale vengono inviati i messaggi. </p> <p>Ad esempio: <span class="filepath"> mail.hq.omniture.com</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpserverport </td> 
   <td colname="col2"> La porta su cui il server SMTP ascolta le connessioni. Si tratta in genere della porta 25. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> invio </td> 
   <td colname="col2"> <p>Indica la modalità di invio del messaggio. I valori sono: </p> <p>1 - Invia messaggi utilizzando il servizio SMTP installato localmente. Utilizzare questo valore se il servizio SMTP è installato nel computer in cui è in esecuzione lo script. </p> <p>2 - Inviare messaggi utilizzando il servizio SMTP in rete. Utilizzare questo valore se il servizio SMTP non è installato nel computer in cui è in esecuzione lo script. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpconnectiontimeout </td> 
   <td colname="col2">Il tempo di attesa di una risposta dal server SMTP <span class="wintitle"> Report</span> prima che la connessione venga interrotta. </td> 
  </tr> 
 </tbody> 
</table>

1. Per le funzioni [!DNL NewUserEmail()] e [!DNL UpdateUserEmail()] , imposta le seguenti variabili:

   <table id="table_91C5E36B84A94C4097EE5993592BE587"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Per questa variabile . . . </th> 
      <th colname="col2" class="entry"> Fornisci queste informazioni . . . </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Da </td> 
      <td colname="col2">Testo da visualizzare nella riga di intestazione Da nelle e-mail di conferma. Questo valore potrebbe essere lo stesso del valore <span class="wintitle"> CC</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> CC </td> 
      <td colname="col2"> <p>Facoltativo. L'indirizzo e-mail valido della persona o dell'alias che deve ricevere una copia di tutti i messaggi relativi agli account utente nuovi e modificati. Puoi specificare più indirizzi e-mail separando gli indirizzi con virgole (senza spazi). </p> <p>Ad esempio: <span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>Nota:  I destinatari ricevono copie di e-mail contenenti password utente. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Oggetto </td> 
      <td colname="col2"> Testo da visualizzare nella riga dell’intestazione Oggetto nelle e-mail di conferma. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> WebPath </td> 
      <td colname="col2"> <p>Percorso effettivo del portale. </p> <p>Ad esempio: <span class="filepath"> http://portal.omniture.com/Example</span></p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Corpo </td> 
      <td colname="col2"> <p>Testo incluso nelle e-mail generate automaticamente. </p> <p>Ad esempio, di seguito è riportato il testo predefinito incluso nelle e-mail inviate per fornire informazioni di accesso: 
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">Di seguito sono riportate le informazioni di accesso al portale Web: </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>NomeUtente: username </p><p>Nuova password: password </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>Puoi accedere al portale utilizzando il seguente URL: </p><p><span class="filepath"> http://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">Dopo aver effettuato l'accesso al portale, puoi modificare la password nella scheda <span class="wintitle"> Admin</span> . </li>
      </ul></p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Salva e chiudi il file.
