---
description: Istruzioni per configurare avvisi amministrativi per Insight Server, Repeater o Transform.
title: Impostazioni di configurazione di avvisi amministrativi
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
exl-id: c75e442e-33e6-4fc8-8368-29482f09e1cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# Impostazioni di configurazione di avvisi amministrativi{#administrative-alerts-configuration-settings}

Istruzioni per configurare avvisi amministrativi per Insight Server, Repeater o Transform.

Completa i parametri nel file seguente:

[!DNL Product Name installation directory\Components\Administrative Alerts.cfg]

<table id="table_5A2298906D5F4215B8FAC42CACBC0002"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Categoria </td> 
   <td colname="col2"> Nome della categoria. È richiesta una categoria di impostazione predefinita. Vedere Categorie di errori in questa tabella. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Categorie di errori </td> 
   <td colname="col2"> Consente di classificare gli errori insieme al file di categorizzazione degli errori. Ogni categoria di errore può avere un proprio set di destinatari e un proprio ritardo di limitazione. Ad esempio, puoi creare una categoria critica con un ritardo di velocità pari a 0, in modo che ogni errore critico venga inviato immediatamente ai destinatari specificati nell’elenco Destinatari. Gli errori che non corrispondono a una sottostringa nel file di categorizzazione degli errori vengono assegnati alla categoria Predefinito. Per aggiungere una nuova categoria, fai clic con il pulsante destro del mouse su un numero e fai clic su <span class="uicontrol"> Aggiungi nuovo </span> &gt; <span class="uicontrol"> Categoria errori </span>. Puoi anche copiarli o rimuoverli utilizzando l’azione di scelta rapida . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> File di categorizzazione degli errori </td> 
   <td colname="col2"> <p>Nome del file da utilizzare per classificare ogni avviso. Il file viene creato utilizzando Notepad. Questo file deve avere tre colonne su ogni riga, separate da tabulazioni. La prima colonna è una stringa corrispondente a errori. Un segno ^ corrisponde all'inizio e un $ corrisponde alla fine della stringa; tutti gli altri caratteri vengono letteralmente confrontati. La seconda colonna è una categoria per gli errori corrispondenti, che si trova in Categorie di errori. Il terzo è un messaggio alternativo, che viene preceduto dal messaggio di errore effettivo nelle e-mail inviate. Se non viene specificato alcun file, tutti gli errori vengono classificati come predefiniti. </p> <p>Per visualizzare un esempio di questo file, vedere il file <span class="filepath"> Error Categories.txt </span> nella directory Ricerche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Da </td> 
   <td colname="col2"> <p>Indirizzo visualizzato nel parametro "from" del messaggio e-mail. </p> <p>Esempio: <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Spazio minimo su disco (MB) </td> 
   <td colname="col2"> Il server genera un avviso e-mail quando l'archiviazione su disco disponibile in qualsiasi directory utilizzata dal server scende al di sotto di questo valore. Il valore predefinito è 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Timeout avviso sensore (min) </td> 
   <td colname="col2"> <p>Il server genera un avviso e-mail quando non ha ricevuto dati da un sensore <span class="wintitle"> configurato e connesso in precedenza </span> in questa finestra temporale. Il valore predefinito è 15. </p> <p> <p>Nota:  <span class="wintitle"> Sensore </span> Il timeout dell'avviso funziona solo se viene interrotta una connessione esistente a un <span class="wintitle"> sensore </span>. Se il servizio del server viene arrestato e riavviato e i <span class="wintitle"> Sensor </span> non si connettono, il server non genera avvisi e-mail. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo del server </td> 
   <td colname="col2"> <p>Indirizzo del server SMTP per l'e-mail in uscita. </p> <p>Esempio: <span class="filepath"> mail.mycompany.com </span></p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Password server </td> 
   <td colname="col2"> <p>Password per l'accesso al server SMTP. Questo parametro è facoltativo a meno che non sia necessario l’accesso per inviare la posta. </p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utente server </td> 
   <td colname="col2"> <p>ID/nome utente per l’accesso al server SMTP. Questo parametro è facoltativo a meno che non sia necessario l’accesso per inviare la posta. </p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ritardo di limitazione (sec) </td> 
   <td colname="col2"> Il numero minimo di secondi che devono trascorrere tra due errori in quella categoria per l’invio di un’e-mail. Il valore 0 invia immediatamente l’e-mail. </td> 
  </tr> 
 </tbody> 
</table>
