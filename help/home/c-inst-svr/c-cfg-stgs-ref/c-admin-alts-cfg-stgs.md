---
description: Istruzioni per configurare gli avvisi amministrativi per Insight Server, Ripetitore o Trasforma.
solution: Analytics
title: Impostazioni di configurazione di avvisi amministrativi
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---


# Impostazioni di configurazione di avvisi amministrativi{#administrative-alerts-configuration-settings}

Istruzioni per configurare gli avvisi amministrativi per Insight Server, Ripetitore o Trasforma.

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
   <td colname="col2"> Nome della categoria. È richiesta una categoria di valore Predefinito. Vedere Categorie di errori in questa tabella. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Categorie di errori </td> 
   <td colname="col2"> Consente di classificare gli errori insieme al file di classificazione degli errori. Ogni categoria di errore può avere un proprio set di destinatari e un proprio ritardo di limitazione. Ad esempio, potete creare una categoria critica con un ritardo di 0, in modo che ogni errore critico venga inviato immediatamente ai destinatari specificati nell'elenco Destinatari. Gli errori che non corrispondono a una sottostringa nel file di classificazione degli errori vengono assegnati alla categoria Predefinito. Per aggiungere una nuova categoria, fare clic con il pulsante destro del mouse su un numero e scegliere <span class="uicontrol"> Aggiungi nuovo </span> &gt; <span class="uicontrol"> Categoria errore </span>. Potete anche copiarli o rimuoverli utilizzando l’azione di clic con il pulsante destro del mouse. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> File di classificazione errori </td> 
   <td colname="col2"> <p>Nome del file da utilizzare per classificare ogni avviso. Potete creare questo file utilizzando Notepad. Il file deve avere tre colonne su ogni riga, separate da tabulazioni. La prima colonna è una stringa che corrisponde a errori. Un segno ^ corrisponde all'inizio e un simbolo $ corrisponde alla fine della stringa; tutti gli altri caratteri vengono letteralmente associati. La seconda colonna è una categoria di errori corrispondenti, che si trova in Categorie di errori. Il terzo è un messaggio alternativo, che viene preceduto dal messaggio di errore effettivo nelle e-mail che vengono inviate. Se non viene specificato alcun file, tutti gli errori vengono classificati come predefiniti. </p> <p>Per visualizzare un esempio di questo file, vedere il file <span class="filepath"> Error Categories.txt </span> nella directory Searchups. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Da </td> 
   <td colname="col2"> <p>Indirizzo che viene visualizzato nel parametro "from" del messaggio e-mail. </p> <p>Esempio: <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Spazio minimo su disco (MB) </td> 
   <td colname="col2"> Il server genera un avviso e-mail quando l'archiviazione su disco disponibile in qualsiasi directory utilizzata dal server scende al di sotto di questo valore. Il valore predefinito è 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Timeout avviso sensore (min) </td> 
   <td colname="col2"> <p>Il server genera un avviso e-mail quando non ha ricevuto dati da un <span class="wintitle"> sensore configurato e connesso in precedenza </span> in questa finestra temporale. Il valore predefinito è 15. </p> <p> <p>Nota:  <span class="wintitle"> Timeout </span> avviso sensore funziona solo se viene persa una connessione esistente a un <span class="wintitle"> sensore </span> . Se il servizio del server viene arrestato e riavviato e i <span class="wintitle"> sensori </span> non si connettono, il server non genera avvisi e-mail. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo del server </td> 
   <td colname="col2"> <p>L'indirizzo del server SMTP per l'e-mail in uscita. </p> <p>Esempio: <span class="filepath"> mail.mycompany.com </span></p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Password server </td> 
   <td colname="col2"> <p>La password per accedere al server SMTP. Questo parametro è facoltativo, a meno che non sia necessario effettuare il login per inviare la posta elettronica. </p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utente server </td> 
   <td colname="col2"> <p>ID/nome utente per l'accesso al server SMTP. Questo parametro è facoltativo, a meno che non sia necessario effettuare il login per inviare la posta elettronica. </p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ritardo di limitazione (sec) </td> 
   <td colname="col2"> Il numero minimo di secondi che devono trascorrere tra due errori in quella categoria per l'invio di un'e-mail. Il valore 0 invia immediatamente l’e-mail. </td> 
  </tr> 
 </tbody> 
</table>

