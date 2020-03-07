---
description: L'accesso e le autorizzazioni all'interno del portale di report sono controllati utilizzando account utente e di gruppo singoli.
solution: Analytics
title: Modificare il file Email.asp
topic: Data workbench
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modificare il file Email.asp{#edit-the-email-asp-file}

L&#39;accesso e le autorizzazioni all&#39;interno del portale di report sono controllati utilizzando account utente e di gruppo singoli.

Ogni volta che aggiungete un nuovo account o modificate un account esistente, potete inviare un messaggio e-mail di conferma all’indirizzo e-mail specificato per tale account (consultate [Utilizzo degli account](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)) e copiarlo negli indirizzi e-mail specificati nel [!DNL email.asp] file.

>[!NOTE]
>
>Le e-mail di notifica vengono inviate agli utenti dell&#39;account solo quando avete specificato un indirizzo e-mail per l&#39;account e avete configurato correttamente il [!DNL email.asp] file. Se non desiderate inviare e-mail di notifica per un account, lasciate vuoto il campo e-mail dell’account.

Questo file risiede nella `\*PortalName*\PortalASP` cartella.

1. Nel computer in cui è in esecuzione IIS, aprite il [!DNL email.asp] file in un editor di testo come Blocco note.
1. Impostate le seguenti variabili:

<table id="table_44F52DA266364DF993C40678A28E0F0D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questa variabile. . . </th> 
   <th colname="col2" class="entry"> Fornire queste informazioni. . . </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> smtpserver </td> 
   <td colname="col2"> <p>Nome DNS o indirizzo IP del server SMTP tramite il quale vengono inviati i messaggi. </p> <p>Ad esempio: <span class="filepath"> mail.hq.omniture.com</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpserverport </td> 
   <td colname="col2"> La porta sulla quale il server SMTP ascolta le connessioni. Si tratta in genere della porta 25. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> spendaccione </td> 
   <td colname="col2"> <p>Indica la modalità di invio del messaggio. I valori sono: </p> <p>1 - Invia i messaggi utilizzando il servizio SMTP installato localmente. Utilizzare questo valore se il servizio SMTP è installato sul computer in cui è in esecuzione lo script. </p> <p>2 - Inviare messaggi utilizzando il servizio SMTP in rete. Utilizzare questo valore se il servizio SMTP non è installato nel computer in cui è in esecuzione lo script. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpconnectiontimeout </td> 
   <td colname="col2">Il tempo che <span class="wintitle"> il report</span> deve attendere per ricevere una risposta dal server SMTP prima che venga interrotta la connessione. </td> 
  </tr> 
 </tbody> 
</table>

1. Per le funzioni [!DNL NewUserEmail()] [!DNL UpdateUserEmail()] e, impostare le seguenti variabili:

   <table id="table_91C5E36B84A94C4097EE5993592BE587"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Per questa variabile. . . </th> 
      <th colname="col2" class="entry"> Fornire queste informazioni. . . </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Da </td> 
      <td colname="col2">Testo da visualizzare nella riga di intestazione Da nelle e-mail di conferma. Questo valore può essere lo stesso del <span class="wintitle"> valore CC</span> . </td> 
   </tr> 
   <tr> 
      <td colname="col1"> CC </td> 
      <td colname="col2"> <p>Facoltativo. L'indirizzo e-mail valido della persona o dell'alias che deve ricevere una copia di tutti i messaggi relativi agli account utente nuovi e modificati. Potete specificare più indirizzi e-mail separandoli con virgole (senza spazi). </p> <p>Ad esempio: <span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>Nota:  I destinatari ricevono copie dei messaggi e-mail contenenti password utente. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Oggetto </td> 
      <td colname="col2"> Testo che si desidera visualizzare nella riga dell'intestazione Oggetto nelle e-mail di conferma. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> WebPath </td> 
      <td colname="col2"> <p>Percorso effettivo del portale. </p> <p>Ad esempio: <span class="filepath"> http://portal.omniture.com/Example</span></p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Corpo </td> 
      <td colname="col2"> <p>Testo incluso nelle e-mail generate automaticamente. </p> <p>Ad esempio, di seguito è riportato il testo predefinito incluso nelle e-mail inviate per fornire le informazioni di login: 
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">Le informazioni di accesso al portale Web sono fornite di seguito: </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>NomeUtente: username </p><p>Nuova password: password </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>Potete accedere al portale utilizzando il seguente URL: </p><p><span class="filepath"> http://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">Dopo aver effettuato l'accesso al portale, potete modificare la password nella scheda <span class="wintitle"> Admin</span> . </li>
      </ul></p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Salvate e chiudete il file.
