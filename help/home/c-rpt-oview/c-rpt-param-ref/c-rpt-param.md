---
description: Informazioni sui parametri Report.cfg.
title: Parametri Report.cfg
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
exl-id: 31e4de5f-f7e8-4a35-b5c6-6ad8ef79a259
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2348'
ht-degree: 1%

---

# Parametri Report.cfg{#report-cfg-parameters}

{{eol}}

Informazioni sui parametri Report.cfg.

Il campione [!DNL Report.cfg] mostrato in [Configurare il set di rapporti](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) contiene solo i parametri inclusi nel [!DNL Report.cfg] per impostazione predefinita. La tabella seguente fornisce una descrizione di tutte le opzioni disponibili [!DNL Report.cfg] parametri del file.

Se devi aggiungere parametri aggiuntivi a un [!DNL Report.cfg] , è necessario utilizzare un editor di testo. Per i passaggi necessari, compresi esempi su come definire ogni voce di parametro, consulta [Modifica dei file Report.cfg esistenti](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

>[!NOTE]
>
>I parametri di questa tabella sono elencati in ordine alfabetico. Quando apri la [!DNL Report.cfg] file in Data Workbench, i vettori sono elencati in ordine alfabetico, seguiti da singoli parametri elencati in ordine alfabetico.

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
   <td colname="col2"> <p><i>Facoltativo</i>. Questo parametro si applica solo ai rapporti con indicatori di metrica. Numero di indicatori di metrica che devono essere visualizzati nel foglio di lavoro prima dell'invio di un rapporto di avviso. </p> <p>Se nel foglio di lavoro dell’indicatore della metrica viene monitorata solo una metrica, impostare la soglia su 1. Il rapporto viene generato quando la metrica nel foglio restituisce una freccia su/giù o una X. Se nel rapporto vengono monitorate più metriche, è possibile selezionare il numero di indicatori di metrica che devono essere valutati in una freccia su/giù o una X prima che il rapporto venga generato. Ad esempio, se vengono monitorate due metriche:
     <ul id="ul_A64E8A2306B14371A233D372B956F64D">
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">Se la soglia è impostata su 1, il rapporto viene generato se una delle metriche nel foglio restituisce una freccia su/giù o una X. </li>
      <li id="li_DA4EF4984880483DA48322D9D57B9240">Se la soglia è impostata su 2, entrambe le metriche devono restituire una freccia su/giù o una X prima che il rapporto venga generato. </li>
     </ul> </p> <p>Per ulteriori informazioni sugli indicatori di metrica, consulta la sezione <i>Guida utente di Data Workbench</i>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Consenti rigenerazione report </td>
   <td colname="col2"> <p>Indica se <span class="keyword"> Server di rapporto </span> genera o rigenera automaticamente rapporti specifici quando crei o modifichi tali rapporti. Le opzioni sono true o false. Se impostato su true, la creazione o la modifica di un'area di lavoro dei rapporti causa <span class="keyword"> Server di rapporto </span> per rigenerare il report per l'esecuzione più recente. </p> <p> <p>Nota: Modifica della <span class="filepath"> Report.cfg </span> cause dei file <span class="keyword"> Server di rapporto </span> per rigenerare tutti i rapporti controllati da <span class="filepath"> Report.cfg </span> file. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Allegati </td>
   <td colname="col2"> <p><i>Facoltativo</i>. Identificatore di sezione per il nome e il tipo di contenuto di eventuali allegati che vengono visualizzati con rapporti distribuiti tramite e-mail, incluso il numero di allegati. </p> <p>Per aggiungere un nuovo allegato:
     <ol id="ol_CBDC1E95D34A4D08A862680127438433">
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">Apri <span class="filepath"> Report.cfg </span> file in Data Workbench. </li>
      <li id="li_0709ADDDDF2E469FAB10761B46173136">Fai clic con il pulsante destro del mouse <span class="uicontrol"> Allegati </span> e fai clic su <span class="uicontrol"> Aggiungi nuovo figlio </span> &gt; <span class="uicontrol"> Allegato </span>. </li>
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
   <td colname="col1"> Set di colori </td>
   <td colname="col2"> Identifica la combinazione di colori per cui utilizzare <span class="filepath"> .png </span> file. 0 è per uno sfondo nero; 1 è per uno sfondo bianco; e 2 è per un'immagine in scala di grigi. </td>
  </tr>
  <tr>
   <td colname="col1"> Comando da eseguire </td>
   <td colname="col2"> <i>Facoltativo</i>. Comando batch o eseguibile che viene eseguito dopo la generazione del set di rapporti. Se è necessario avviare l'interprete della shell dei comandi, precedere il comando con cmd /c. </td>
  </tr>
  <tr>
   <td colname="col1"> Modello Excel predefinito </td>
   <td colname="col2"> <p><i>Facoltativo</i>. Nome file del file modello Excel generico ( <span class="filepath"> .xls </span> o <span class="filepath"> xlsx </span>) da utilizzare per la generazione di rapporti come file Excel. Questo parametro supporta percorsi di file completi, ad esempio <span class="filepath"> c:\templates\mytemplate.xls </span>. </p> <p>Questo file viene utilizzato per tutti i rapporti Excel a meno che non sia stato definito un modello specifico per un particolare rapporto. Vedi <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Utilizzo di un file modello </a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Nome dimensione </td>
   <td colname="col2"> <i>Facoltativo</i>. Nome della dimensione per la quale desideri generare in modo dinamico un rapporto. Se si immette un nome di dimensione in questo parametro, è necessario immettere un valore nel parametro File di ricerca o nei parametri Metrica N superiore e Valore N superiore. La dimensione denominata in questo parametro deve esistere nel set di dati per il quale vengono creati i rapporti. </td>
  </tr>
  <tr>
   <td colname="col1"> Solo e-mail se perfetto </td>
   <td colname="col2"> <i>Facoltativo</i>. Consente all'utente di specificare che un set di rapporti deve essere inviato solo quando non si sono verificati errori durante l'esecuzione. Le opzioni sono true e false. Il valore predefinito è false. </td>
  </tr>
  <tr>
   <td colname="col1"> Data di fine </td>
   <td colname="col2"> <p><i>Facoltativo</i>. Data e ora dell'ultima esecuzione del set di rapporti. Questa ora è basata sul data e ora del set di dati. </p> <p>Formato: MM/GG/AAAA hh:mm fuso orario, utilizzando la sintassi 24 ore per l'ora </p> <p>Esempio: 01/08/2007 12:01 EDT </p> <p>Per ulteriori informazioni sulle impostazioni del fuso orario, consulta la sezione <i>Guida alla configurazione del set di dati</i>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Ogni </td>
   <td colname="col2"> Frequenza della generazione del set di rapporti: giorno, settimana o mese. </td>
  </tr>
  <tr>
   <td colname="col1"> Timeout watchdog di Excel (secondi) </td>
   <td colname="col2"> <p><i>Facoltativo</i>. Il numero di secondi desiderati <span class="keyword"> Server di rapporto </span> attendere che Microsoft Excel risponda quando si genera un rapporto come file Excel prima di <span class="keyword"> Server di rapporto </span> decide che Excel non risponde e interrompe il processo. L'utilizzo di questo parametro abilita <span class="keyword"> Server di rapporto </span> per terminare Excel quando non risponde e continuare a elaborare i rapporti non Excel. Il valore predefinito è 300.0. Per disabilitare questa funzionalità, impostare questo parametro su 0.0. </p> <p>Assicurati che il valore definito sia sufficientemente lungo per consentire l’esportazione del rapporto in Excel. In caso contrario, <span class="keyword"> Server di rapporto </span> potrebbe terminare prematuramente Excel e il rapporto non verrà generato. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Formula filtro </td>
   <td colname="col2"> <p><i>Facoltativo</i>. Filtro applicato a ogni area di lavoro del set di rapporti. </p> <p>Per ulteriori informazioni, consulta la sezione <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external"> sintassi per la creazione di filtri </a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Correzione del gamma </td>
   <td colname="col2"> <p>Impostazione del gamma per <span class="filepath"> .png </span> output del file. Il valore predefinito è 1,6. </p> <p> <p>Nota: L'Adobe consiglia di non modificare questo valore. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Nascondi logo </td>
   <td colname="col2"> Indica se il server di rapporto nasconde i loghi durante la generazione dei rapporti. Le opzioni sono <span class="filepath"> true </span> o <span class="filepath"> false </span>. Se impostato su <span class="filepath"> false </span>, il rapporto viene generato con il logo Report. Il valore predefinito è <span class="filepath"> false </span>. </td>
  </tr>
  <tr>
   <td colname="col1"> File di ricerca </td>
   <td colname="col2"> <p><i>Facoltativo</i>. Quando questo parametro viene compilato, il server di rapporto viene eseguito in modalità dinamica e genera rapporti per ogni elemento della dimensione specificata nel parametro Nome Dimension. Questo file deve contenere due colonne delimitate da tabulazioni, senza una riga di intestazione. </p> <p>
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A">
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">La colonna 1 contiene un elenco di elementi dimensionali. </li>
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">La colonna 2 contiene gli indirizzi e-mail dei destinatari del rapporto. Un rapporto per un dato elemento nella colonna 1 viene inviato all’indirizzo e-mail nella stessa riga nella colonna 2. Puoi immettere più indirizzi e-mail separandoli con virgole (senza spazi). Se i rapporti non devono essere inviati via e-mail, questa colonna può essere vuota ma deve esistere. </li>
     </ul> </p> <p> <p>Nota: Se si immette un valore in questo parametro, è necessario immettere un valore nel parametro Nome Dimension. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Solo notifica </td>
   <td colname="col2"> Questo <span class="wintitle"> Server di rapporto </span> consente di configurare Data Workbench per l’invio di un’e-mail quando viene generato un rapporto. Impostazione di questo valore su <span class="filepath"> true </span> non invia il rapporto, ma invia un’e-mail di notifica all’utente iscritto che il rapporto è stato generato. </td>
  </tr>
  <tr>
   <td colname="col1"> Report posta </td>
   <td colname="col2"> <p>Identificatore di sezione per la distribuzione dei rapporti tramite e-mail. Per distribuire i rapporti tramite e-mail, completa i seguenti parametri per <span class="wintitle"> Report posta </span> voce. Tutti i rapporti del set di rapporti vengono inviati via e-mail in un messaggio agli indirizzi e-mail specificati nel parametro Recipients (Destinatari). </p> <p> <p>Nota: Il server di rapporto invia un'e-mail solo quando ha generato almeno un rapporto. </p> </p> <p>Per abilitare l’invio tramite e-mail dei rapporti, è necessario completare almeno i seguenti parametri per questa voce:
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8">
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">Server SMTP </li>
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">Recipients (Destinatari) </li>
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">Indirizzo mittente </li>
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">Solo notifica </li>
     </ul> </p> <p> <p>Nota: Per inviare i rapporti per e-mail dopo aver generato nuovamente un set di rapporti, vedi <a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887"> Modifica dei file Report.cfg esistenti </a>. </p> </p> <p>Il valore Solo notifica è disponibile nelle versioni 5.4x e 5.5x. </p> <p>Per un ampio set di destinatari da avvisare (più di 20), si consiglia vivamente di utilizzare le liste di distribuzione delle e-mail. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Modello XSL corpo </td>
   <td colname="col2"> <p><i>Facoltativo</i>. Percorso del file modello XSL da applicare al <span class="filepath"> reports.xml </span> file. L'utilizzo di questo parametro consente al server di rapporto di inviare i rapporti all'interno dell'e-mail distribuita anziché come allegati. Il testo risultante viene utilizzato come corpo del messaggio e-mail. </p> <p>Vedi <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> File di esempio del rapporto </a> per un file di esempio. </p> <p>Per informazioni su XSLT (Extensible Stylesheet Language), vedere <a href="https://www.w3.org/Style/XSL/" format="http" scope="external"> Famiglia di lingue per fogli di stile estensibili </a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Recipients (Destinatari) </td>
   <td colname="col2"> Indirizzi e-mail delle persone a cui desideri inviare il rapporto. </td>
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
   <td colname="col2"> Indirizzo del server SMTP e password e nome utente necessari per l’autenticazione. </td>
  </tr>
  <tr>
   <td colname="col1"> Oggetto </td>
   <td colname="col2"> <i>Facoltativo</i>. Oggetto che descrive l’e-mail da inviare. </td>
  </tr>
  <tr>
   <td colname="col1"> Solo notifica </td>
   <td colname="col2"> Consente di configurare Data Workbench per l’invio di un’e-mail quando viene generato un rapporto in background. L’impostazione di questo valore su True non invia il rapporto, ma invia un messaggio e-mail di collegamento dell’utente iscritto alla posizione del rapporto. </td>
  </tr>
  <tr>
   <td colname="col1"> Directory principale di output </td>
   <td colname="col2"> <p><i>Facoltativo</i>. Posizione di output dei set di rapporti generati. Il valore predefinito è <i>&lt;profile name=""&gt;</i>\Cartella Report nella directory di installazione del server di rapporto. </p> <p>Per configurare <span class="keyword"> Server di rapporto </span> per inviare i rapporti a un portale, imposta <span class="wintitle"> Directory principale di output </span> alla directory principale dei documenti del server Web utilizzato per il portale. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Filtro query di precaricamento </td>
   <td colname="col2"> <p><i>Facoltativo</i>. Questo parametro si applica solo al <span class="wintitle"> Elemento Dimension superiore </span> tipo di report. </p> <p>Nome del filtro da applicare alla query che deve essere eseguita per determinare i primi N elementi dimensionali prima che sia possibile generare il rapporto. Il valore predefinito è <span class="wintitle"> Broken_Session_Filter </span>. Per ulteriori informazioni sulla <span class="wintitle"> Filtro sessione interrotto </span>, vedi <i>Guida utente di Data Workbench</i>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <span class="wintitle"> Tipi di rapporti </span> </td>
   <td colname="col2"> <p>Formato in cui si desidera generare l'output. È possibile utilizzare una delle seguenti opzioni o tutte per generare il set di rapporti in più formati contemporaneamente:
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9">
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Viene creata una cartella di lavoro di Excel con una visualizzazione per foglio di lavoro. Come regola generale, utilizza i file Excel per la distribuzione delle e-mail. Vedi <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee"> Generazione di rapporti come file di Microsoft Excel </a>. Per informazioni sull'utilizzo di un file modello, vedi <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Utilizzo di un file modello </a>. </li>
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png crea file grafici di rete portatili. Come regola generale, utilizza <span class="filepath"> .png </span> file da visualizzare in un browser Web (portale). </li>
      <li id="li_869DA266E6A041A5BD343537743FAC79">La miniatura crea una miniatura ( <span class="filepath"> .jpg </span> file) dell'area di lavoro. La dimensione predefinita è 240x180. Per modificare le dimensioni predefinite, modifica i parametri Thumbnail X e Thumbnail Y . </li>
     </ul> </p> <p>Per aggiungere un nuovo tipo di rapporto durante la modifica <span class="filepath"> Report.cfg </span> in data workbench, fai clic con il pulsante destro del mouse su <span class="uicontrol"> Tipi di rapporti </span>, fai clic su <span class="uicontrol"> Aggiungi nuovo figlio </span>, quindi seleziona il tipo di rapporto desiderato. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Data di inizio </td>
   <td colname="col2"> <p>Data e ora della prima esecuzione del set di rapporti. Questa ora è basata sul data e ora del set di dati. </p> <p>Formato: MM/GG/AAAA hh:mm, utilizzando la sintassi a 24 ore per il tempo. </p> <p>Per ulteriori informazioni sulle impostazioni del fuso orario, consulta la sezione <i>Guida alla configurazione del set di dati</i>. </p> <p> <p>Nota: I rapporti iniziano a essere eseguiti quando le marche temporali dei dati nel profilo corrispondono alla data e all’ora specificate. </p> </p> <p>Esempio: </p> <p>Se la data di inizio è 08/08/2006 12:00 EST, i rapporti vengono eseguiti per i dati con una marca temporale pari a 08/08/2006 12:00 EST e versioni successive.
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1">
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">I rapporti giornalieri saranno eseguiti per il 08/08/2006 e in seguito ogni giorno per i dati con hh:mm = 12:00 EST. </li>
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">I rapporti settimanali saranno eseguiti per il 08/08/2006 e per ogni 7° giorno successivo per i dati con hh:mm = 12:00 EST. </li>
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">I rapporti mensili saranno eseguiti per il 08/08/2006 e per l’ottavo giorno di ogni mese successivo per i dati con hh:mm = 12:00 EST. </li>
     </ul> </p> <p>La <span class="wintitle"> Ora rapporto </span> Questa metrica influisce sulle dimensioni di reporting "Last N" (Ultimo numero N), come "Last 7 Days", "Ieri" e "3 settimane fa". Per le query nel server di rapporto, la <span class="wintitle"> Ora rapporto </span> metrica ( <span class="filepath"> Rapporto Time.metric </span>) identifica la data e l’ora di esecuzione dei rapporti. Si tratta inizialmente della data e dell'ora specificate nel parametro Data di inizio, che quindi viene incrementato del periodo specificato dal parametro Ogni. Per le query in Data Workbench, la <span class="wintitle"> Ora rapporto </span> è basato sulla mezzanotte della metrica A ( <span class="filepath"> A partire da </span>). A causa della differenza nelle definizioni della metrica Ora rapporto, se esegui una query su un’area di lavoro che utilizza una dimensione Ultima N, puoi ricevere risultati diversi in Data Workbench e <span class="keyword"> Server di rapporto </span> per la stessa area di lavoro. </p> </td>
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
   <td colname="col1"> Metrica N principale </td>
   <td colname="col2"> <p><i>Facoltativo</i>. Vedi la descrizione del parametro Top N Value. </p> <p> <p>Nota: Se si immette un valore in questo parametro, è necessario immettere un valore nel parametro Nome Dimension e nel parametro Valore N superiore. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Valore N superiore </td>
   <td colname="col2"> <p><i>Facoltativo</i>. Quando questo parametro viene popolato, <span class="keyword"> Server di rapporto </span> viene eseguito in modalità dinamica e genera rapporti per il numero principale (specificato in questo parametro) di elementi per la dimensione specificata nel parametro Nome Dimension, conteggiando per la metrica specificata nel parametro Metrica superiore N. </p> <p>Esempio: Se immetti Pagina nel parametro Nome Dimension, Sessions nel parametro N di metrica superiore e 5 in questo parametro, il rapporto generato elenca le cinque pagine principali con il numero più alto di sessioni. </p> <p> <p>Nota: Se immetti un valore in questo parametro, devi immettere un valore nel parametro Nome Dimension e nel parametro Metrica N superiore. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Usa solo campione locale </td>
   <td colname="col2"> <i>Facoltativo</i>. Indica se si desidera <span class="keyword"> Server di rapporto </span> per generare rapporti utilizzando solo il campione locale del set di dati. L’impostazione di questo parametro su true consente di visualizzare un esempio del set di rapporti (senza caricare un file su un server di Data Workbench) per verificare l’aspetto dell’output senza richiedere tutto il tempo necessario per elaborare completamente i dati. Questa funzione funziona come una funzione di test. Le opzioni sono true o false. Il valore predefinito è false. </td>
  </tr>
  <tr>
   <td colname="col1"> Percorso area di lavoro </td>
   <td colname="col2"> <p><i>Facoltativo</i>. Posizione di una raccolta di aree di lavoro per un determinato set di rapporti. È utile per mantenere una singola copia delle aree di lavoro che devono essere generate e distribuite in più modi, utilizzando <span class="filepath"> Report.cfg </span> file per più set di rapporti. La directory principale per questo percorso può essere qualsiasi cartella di profilo. Non inserire una barra (\) all'inizio della stringa del percorso. </p> <p>Esempio: È possibile salvare le aree di lavoro comuni per Set A e Set B nel <span class="filepath"> Rapporti\Comuni </span> , quindi definisci la <span class="filepath"> Report.cfg </span> file per due set di rapporti diversi, ciascuno con impostazioni di generazione e distribuzione diverse. In entrambi <span class="filepath"> Report.cfg </span> i file, impostando il parametro Percorso di Workspace su <i>nome profilo</i>\Reports\Common. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> File di output XSL </td>
   <td colname="col2"> <i>Facoltativo</i>. Percorso del file di output creato quando il <span class="wintitle"> Modello XSL </span> viene applicato all'indice del report. </td>
  </tr>
  <tr>
   <td colname="col1"> Modello XSL </td>
   <td colname="col2"> <p><i>Facoltativo</i>. Percorso del file modello XSL da applicare all'indice del report. Il risultato si è trasformato <span class="filepath"> .xml </span> viene scritto nel <span class="wintitle"> File di output XSL </span>. Vedi <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> File di esempio del rapporto </a> per un file di esempio. </p> <p> <p>Nota: A meno che non utilizzi un <span class="filepath"> xsl </span> durante la generazione dei rapporti, tutti i rapporti vengono distribuiti tramite e-mail come allegati. </p> </p> </td>
  </tr>
 </tbody>
</table>
