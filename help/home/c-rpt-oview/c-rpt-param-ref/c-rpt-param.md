---
description: Informazioni sui parametri Report.cfg.
solution: Analytics
title: Parametri Report.cfg
topic: Data workbench
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Parametri Report.cfg{#report-cfg-parameters}

Informazioni sui parametri Report.cfg.

L’esempio [!DNL Report.cfg] mostrato in [Configura set](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) di report contiene solo i parametri inclusi nel [!DNL Report.cfg] file per impostazione predefinita. La tabella seguente fornisce una descrizione di tutti i parametri di [!DNL Report.cfg] file disponibili.

Per aggiungere parametri aggiuntivi a un [!DNL Report.cfg] file, è necessario utilizzare un editor di testo. Per i passaggi necessari, compresi esempi di come definire ogni voce di parametro, vedere [Modifica di file](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)Report.cfg esistenti.

>[!NOTE]
>
>I parametri di questa tabella sono elencati in ordine alfabetico. Quando si apre il [!DNL Report.cfg] file in Workbench dati, i vettori sono elencati in ordine alfabetico, seguiti dai singoli parametri elencati in ordine alfabetico.

<table id="table_F55E925EA34F43B6832788BB6878BB4A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Soglia avvisi </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Questo parametro si applica solo ai report con indicatori di metrica. Numero di indicatori di metrica che devono essere visualizzati nel foglio di lavoro prima dell'invio di un rapporto di avviso. </p> <p>Se solo una metrica viene monitorata nel foglio di lavoro dell'indicatore metrica, imposta la soglia su 1. Il rapporto viene generato quando la metrica nel foglio restituisce una freccia su/giù o una X. Se nel rapporto è monitorata più di una metrica, puoi selezionare il numero di indicatori di metrica che devono essere valutati come una freccia su/giù o una X prima della generazione del rapporto. Ad esempio, se vengono monitorate due metriche: 
     <ul id="ul_A64E8A2306B14371A233D372B956F64D"> 
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">Se la soglia è impostata su 1, il rapporto viene generato se una delle metriche nel foglio restituisce una freccia su/giù o una X. </li> 
      <li id="li_DA4EF4984880483DA48322D9D57B9240">Se la soglia è impostata su 2, entrambe le metriche devono restituire una freccia su/giù o una X prima che il rapporto venga generato. </li> 
     </ul> </p> <p>Per ulteriori informazioni sugli indicatori delle metriche, consulta la Guida <i>utente di Workbench</i>dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Consenti rigenerazione report </td> 
   <td colname="col2"> <p>Indica se <span class="keyword"> Report Server genera </span> automaticamente o rigenera particolari report quando si creano o si modificano tali report. Le opzioni sono true o false. Se è impostato su true, la creazione o la modifica di un'area di lavoro report determina la rigenerazione del report da parte del server <span class="keyword"> report </span> per l'esecuzione più recente. </p> <p> <p>Nota:  La modifica del file <span class="filepath"> Report.cfg </span> causa la rigenerazione da parte del server <span class="keyword"> report </span> di tutti i report controllati da tale <span class="filepath"> file Report.cfg </span> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Allegati </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Identificatore di sezione per il nome e il tipo di contenuto di eventuali allegati che vengono inviati con rapporti distribuiti tramite e-mail, incluso il numero di allegati. </p> <p>Per aggiungere un nuovo allegato: 
     <ol id="ol_CBDC1E95D34A4D08A862680127438433"> 
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">Aprire il file <span class="filepath"> Report.cfg </span> in Workbench dati. </li> 
      <li id="li_0709ADDDDF2E469FAB10761B46173136">Fare clic con il pulsante destro del mouse su <span class="uicontrol"> Allegati </span> e scegliere <span class="uicontrol"> Aggiungi nuovo elemento secondario </span> &gt; <span class="uicontrol"> Allegati </span>. </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tipo di contenuto </td> 
   <td colname="col2"> <p>Tipo di contenuto del file da allegare. </p> <p>Esempio: image/jpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> NomeFile </td> 
   <td colname="col2"> <p>Posizione e nome del file da allegare. </p> <p>Esempio: <span class="filepath"> c:\myimage.jpg </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Set colori </td> 
   <td colname="col2"> Identifica la combinazione di colori da utilizzare per i <span class="filepath"> .png </span> file. 0 è per uno sfondo nero; 1 è per uno sfondo bianco; e 2 è per un’immagine in scala di grigio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comando Da Eseguire </td> 
   <td colname="col2"> <i>Facoltativo</i>. Un comando batch o eseguibile che viene eseguito dopo la generazione del set di report. Se è necessario avviare l'interprete della shell dei comandi, precedere il comando con cmd /c. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modello Excel predefinito </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Nome file del file modello Excel generico ( <span class="filepath"> .xls </span> o <span class="filepath"> .xlsx </span>) che si desidera utilizzare per la generazione dei rapporti come file Excel. Questo parametro supporta percorsi di file completi, ad esempio <span class="filepath"> c:\templates\mytemplate.xls </span>. </p> <p>Questo file viene utilizzato per tutti i rapporti Excel, a meno che non sia stato definito un modello specifico per un particolare rapporto. Consultate <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Utilizzo di un file di modello </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome dimensione </td> 
   <td colname="col2"> <i>Facoltativo</i>. Nome della dimensione per la quale si desidera generare in modo dinamico un rapporto. Se immettete un nome di dimensione in questo parametro, dovete immettere un valore nel parametro File di ricerca o nei parametri N superiore e N superiore. La dimensione denominata in questo parametro deve esistere nel set di dati per il quale vengono creati i rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Solo e-mail se perfetto </td> 
   <td colname="col2"> <i>Facoltativo</i>. Consente all'utente di specificare che un set di report deve essere inviato solo quando non si sono verificati errori durante l'esecuzione. Le opzioni sono true e false. Il valore predefinito è false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data fine </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Data e ora dell'ultima esecuzione del set di report. Questa ora è basata sul Data di ora del set di dati. </p> <p>Formato: MM/GG/AAAA hh:mm fuso orario, con sintassi di 24 ore per l'ora </p> <p>Esempio: 08/01/2007 12:01 EDT </p> <p>Per ulteriori informazioni sulle impostazioni del fuso orario, vedere la Guida alla configurazione del <i>set di dati</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ogni </td> 
   <td colname="col2"> Frequenza della generazione del set di report: giorno, settimana o mese. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Timeout controllo Excel (secondi) </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Il numero di secondi di attesa che <span class="keyword"> Report Server </span> attende la risposta di Microsoft Excel durante la generazione di un report come file Excel prima che <span class="keyword"> Report Server </span> decida che Excel non risponde e interrompa il processo. L'utilizzo di questo parametro consente <span class="keyword"> a Report Server </span> di terminare Excel quando non risponde e di continuare l'elaborazione dei rapporti non Excel. Il valore predefinito è 300.0. Per disattivare questa funzionalità, impostate questo parametro su 0.0. </p> <p>Accertatevi che il valore definito sia sufficientemente lungo da consentire l'esportazione del rapporto in Excel. In caso contrario, <span class="keyword"> il server di report </span> potrebbe arrestare prematuramente Excel e il report non verrà generato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtra formula </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Filtro applicato a ogni area di lavoro del set di rapporti. </p> <p>Per ulteriori informazioni, vedere la <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external"> sintassi per la creazione di filtri </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Correzione gamma </td> 
   <td colname="col2"> <p>Impostazione gamma per output di file <span class="filepath"> .png </span> . Il valore predefinito è 1,6. </p> <p> <p>Nota:  Adobe consiglia di non modificare questo valore. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nascondi logo </td> 
   <td colname="col2"> Indica se il server di report nasconde i logo durante la generazione dei report. Le opzioni sono <span class="filepath"> true </span> o <span class="filepath"> false </span>. Se impostato su <span class="filepath"> false </span>, il rapporto viene generato con il logo Report. The default is <span class="filepath"> false </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> File di ricerca </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Quando questo parametro viene popolato, il server di report viene eseguito in modalità dinamica e genera report per ogni elemento della dimensione specificata nel parametro Nome dimensione. Questo file deve contenere due colonne delimitate da tabulazioni, senza una riga di intestazione. </p> <p> 
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A"> 
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">La colonna 1 contiene un elenco di elementi dimensionali. </li> 
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">La colonna 2 contiene gli indirizzi e-mail dei destinatari del rapporto. Un rapporto per un dato elemento nella colonna 1 viene inviato all'indirizzo e-mail nella stessa riga della colonna 2. Potete immettere più indirizzi e-mail separandoli con virgole (senza spazi). Se i rapporti non devono essere inviati via e-mail, questa colonna può essere vuota ma deve esistere. </li> 
     </ul> </p> <p> <p>Nota:  Se immettete un valore in questo parametro, dovete immettere un valore nel parametro Nome dimensione. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Solo notifica </td> 
   <td colname="col2"> Questa <span class="wintitle"> impostazione Server </span> report consente di configurare il workbench dati per l'invio di un'e-mail quando viene generato un report. Impostando questo valore su <span class="filepath"> true </span> non viene inviato il rapporto, ma viene inviato un messaggio e-mail di notifica all’utente iscritto che il rapporto è stato generato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Report posta </td> 
   <td colname="col2"> <p>Identificatore di sezione per la distribuzione dei rapporti tramite e-mail. Per distribuire i rapporti via e-mail, completa i seguenti parametri per la voce Rapporto <span class="wintitle"> e-mail </span> . Tutti i rapporti del set di rapporti vengono inviati via e-mail in un messaggio agli indirizzi e-mail specificati nel parametro Recipients (Destinatari). </p> <p> <p>Nota:  Il server di report invia un'e-mail solo se ha generato almeno un report. </p> </p> <p>Per abilitare l'invio tramite e-mail di rapporti, devi completare almeno i seguenti parametri per questa voce: 
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8"> 
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">Server SMTP </li> 
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">Recipients (Destinatari) </li> 
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">Indirizzo mittente </li> 
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">Solo notifica </li> 
     </ul> </p> <p> <p>Nota:  Per inviare i rapporti per e-mail dopo aver rigenerato un set di rapporti, consulta <a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887"> Modifica dei file Report.cfg esistenti </a>. </p> </p> <p>Il valore Solo notifica è disponibile nelle release 5.4x e 5.5x. </p> <p>Per un ampio gruppo di destinatari a cui si desidera inviare una notifica (oltre 20), si consiglia vivamente di utilizzare elenchi di distribuzione tramite e-mail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modello XSL corpo </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Percorso del file modello XSL da applicare al file <span class="filepath"> Reports.xml </span> . Questo parametro consente al server di report di inviare i rapporti all'interno dell'e-mail distribuita invece che come allegati. Il testo risultante viene utilizzato come corpo del messaggio e-mail. </p> <p>Consultate <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> Report Sample Files (File di esempio dei rapporti) </a> per un file di esempio. </p> <p>Per informazioni sul linguaggio XSLT (Extensible Stylesheet Language), vedere <a href="http://www.w3.org/Style/XSL/" format="http" scope="external"> La famiglia di linguaggi per fogli di stile estensibili </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recipients (Destinatari) </td> 
   <td colname="col2"> Indirizzi e-mail delle persone a cui si desidera inviare il rapporto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo mittente </td> 
   <td colname="col2"> Indirizzo e-mail del mittente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome mittente </td> 
   <td colname="col2"> Facoltativo. Nome del mittente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server SMTP </td> 
   <td colname="col2"> Indirizzo del computer del server SMTP e password e nome utente richiesti per l’autenticazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oggetto </td> 
   <td colname="col2"> <i>Facoltativo</i>. Riga dell'oggetto che descrive l'e-mail da inviare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Solo notifica </td> 
   <td colname="col2"> Consente di configurare il workbench dati per l'invio di un'e-mail quando viene generato un rapporto in background. Impostando questo valore su True, il rapporto non viene inviato, ma viene inviato un messaggio e-mail che collega l'utente iscritto alla posizione del rapporto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Radice di output </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Posizione di output dei set di report generati. Il valore predefinito è la cartella <i>&lt;nome profilo&gt;</i>\Reports all'interno della directory di installazione del server di report. </p> <p>Per configurare <span class="keyword"> Report Server </span> per l'output dei report su un portale, impostare <span class="wintitle"> Output Root </span> sulla directory principale del documento del server Web utilizzato per il portale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro query di precaricamento </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Questo parametro si applica solo al tipo di rapporto <span class="wintitle"> Elemento dimensione principale </span> . </p> <p>Nome del filtro che si desidera applicare alla query che deve essere eseguita per determinare gli elementi N di dimensione principali prima che sia possibile generare il rapporto. Il valore predefinito è <span class="wintitle"> Broken_Session_Filter </span>. Per ulteriori informazioni sul filtro di sessione <span class="wintitle"> interrotta </span>, vedere la Guida <i>utente di Workbench</i>dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Tipi di rapporti </span> </td> 
   <td colname="col2"> <p>Formato/i in cui si desidera generare l'output. Potete utilizzare una delle seguenti opzioni o tutte le seguenti per restituire il set di rapporti in più formati contemporaneamente: 
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9"> 
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Viene creata una cartella di lavoro Excel con una visualizzazione per foglio di lavoro. Come regola generale, utilizzate i file Excel per la distribuzione delle e-mail. Vedere <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee"> Generazione di rapporti come file di Microsoft Excel </a>. Per informazioni sull'utilizzo di un file modello, vedere <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Utilizzo di un file modello </a>. </li> 
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png crea file grafici di rete portatili. Come regola generale, utilizzate <span class="filepath"> .png </span> file per la visualizzazione in un browser Web (portale). </li> 
      <li id="li_869DA266E6A041A5BD343537743FAC79">Miniatura crea una miniatura (file <span class="filepath"> .jpg </span> ) dell’area di lavoro. Le dimensioni predefinite sono 240x180. Per modificare le dimensioni predefinite, modificate i parametri Miniatura X e Miniatura Y. </li> 
     </ul> </p> <p>Per aggiungere un nuovo tipo di rapporto durante la modifica di <span class="filepath"> Report.cfg </span> nel workbench dati, fare clic con il pulsante destro del mouse su <span class="uicontrol"> Tipi di rapporto </span>, fare clic su <span class="uicontrol"> Aggiungi nuovo figlio </span>e selezionare il tipo di rapporto desiderato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data inizio </td> 
   <td colname="col2"> <p>La prima data e l'ora in cui si desidera che venga eseguito il set di report. Questa ora è basata sul Data di ora del set di dati. </p> <p>Formato: MM/GG/AAAA hh:mm, con sintassi di 24 ore per il fuso orario. </p> <p>Per ulteriori informazioni sulle impostazioni del fuso orario, vedere la Guida alla configurazione del <i>set di dati</i>. </p> <p> <p>Nota:  I report iniziano a essere eseguiti quando le marche temporali dei dati nel profilo corrispondono alla data e all'ora specificate. </p> </p> <p>Esempio: </p> <p>Se la data di inizio è 08/08/2006 12:00 EST, i report vengono eseguiti per i dati con marca temporale 08/08/2006 12:00 EST e versioni successive. 
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1"> 
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">I report giornalieri saranno eseguiti per il 08/08/2006 e, successivamente, ogni giorno per i dati con hh:mm = 12:00 EST. </li> 
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">I rapporti settimanali verranno eseguiti per il 08/08/2006 e ogni 7 giorni successivi per i dati con hh:mm = 12:00 EST. </li> 
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">I rapporti mensili saranno eseguiti per il 08/08/2006 e per l'ottavo giorno di ogni mese successivo per i dati con hh:mm = 12:00 EST. </li> 
     </ul> </p> <p>La <span class="wintitle"> metrica Ora rapporto </span> influisce sulle dimensioni di reporting "Ultima N", come "Ultimi 7 giorni" "Ieri" e "3 settimane fa". Per le query nel server di report, la <span class="wintitle"> metrica Ora rapporto </span> ( <span class="filepath"> Report Time.Metric </span>) identifica la data e l'ora di esecuzione dei report. Si tratta inizialmente della data e dell'ora specificate nel parametro Data inizio, che quindi si incrementa per il periodo specificato dal parametro Ogni. Per le query nel workbench dati, la <span class="wintitle"> metrica Ora rapporto </span> si basa sulla mezzanotte della metrica Come di ( <span class="filepath"> Come di.Metrica </span>). A causa della differenza nelle definizioni della metrica Tempo rapporto, se si esegue una query su un'area di lavoro che utilizza una dimensione Ultima N, è possibile ottenere risultati diversi in workbench dati e <span class="keyword"> Report Server </span> per la stessa area di lavoro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniatura X </td> 
   <td colname="col2"> <i>Facoltativo</i>. Numero intero che controlla le dimensioni (in pixel) dell’asse X delle miniature generate come output. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniatura Y </td> 
   <td colname="col2"> <i>Facoltativo</i>. Numero intero che controlla le dimensioni (in pixel) dell’asse Y delle miniature generate come output. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metrica N superiore </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Vedere la descrizione del parametro Top N Value. </p> <p> <p>Nota:  Se immettete un valore in questo parametro, dovete immettere un valore nel parametro Nome dimensione e nel parametro Valore N superiore. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valore N superiore </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Quando questo parametro viene popolato, <span class="keyword"> Report Server </span> viene eseguito in modalità dinamica e genera rapporti per il numero superiore (specificato in questo parametro) di elementi per la dimensione specificata nel parametro Dimension Name (Nome dimensione), contando per la metrica specificata nel parametro Top N Metric (Metrica superiore). </p> <p>Esempio: Se immetti Pagina nel parametro Nome dimensione, Sessioni nel parametro N massimo e 5 in questo parametro, il rapporto generato elenca le cinque pagine principali con il numero più alto di sessioni. </p> <p> <p>Nota:  Se immettete un valore in questo parametro, dovete immettere un valore nel parametro Nome dimensione e nel parametro Metrica N superiore. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usa solo esempio locale </td> 
   <td colname="col2"> <i>Facoltativo</i>. Indica se si desidera che <span class="keyword"> il server di report </span> generi i report utilizzando solo l'esempio locale del set di dati. Impostando questo parametro su true è possibile visualizzare un esempio del set di report (senza caricare un carico su un server workbench dati) per vedere l'aspetto dell'output senza richiedere tutto il tempo necessario per l'elaborazione completa dei dati. Funziona come funzione di prova. Le opzioni sono true o false. Il valore predefinito è false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Percorso area di lavoro </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Posizione di una raccolta di aree di lavoro per un determinato set di report. Questo è utile per mantenere una singola copia delle aree di lavoro che devono essere generate e distribuite in più modi, utilizzando i file <span class="filepath"> Report.cfg </span> per più set di report. La directory principale di questo percorso può essere qualsiasi cartella di profilo. Non immettete una barra (\) all'inizio della stringa percorso. </p> <p>Esempio: Potete salvare le aree di lavoro comuni per i set A e B nella cartella <span class="filepath"> Reports\Common </span> , quindi definire i file <span class="filepath"> Report.cfg </span> per due set di rapporti diversi, ciascuno con diverse impostazioni di generazione e distribuzione. In entrambi <span class="filepath"> i file Report.cfg </span> il parametro Workspace Path viene impostato sul nome del <i>profilo</i>\Reports\Common. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> File di output XSL </td> 
   <td colname="col2"> <i>Facoltativo</i>. Percorso del file di output creato quando il modello <span class="wintitle"> XSL viene applicato </span> all'indice del report. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modello XSL </td> 
   <td colname="col2"> <p><i>Facoltativo</i>. Percorso del file modello XSL da applicare all'indice del report. Il <span class="filepath"> .xml trasformato risultante </span> viene scritto nel file di output <span class="wintitle"> XSL specificato </span>. Consultate <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> Report Sample Files (File di esempio dei rapporti) </a> per un file di esempio. </p> <p> <p>Nota:  A meno che non venga utilizzato un modello <span class="filepath"> .xsl </span> per la generazione dei rapporti, tutti i rapporti vengono distribuiti tramite e-mail come allegati. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

