---
description: Server Files Manager consente di amministrare e gestire in remoto i computer server di Data Workbench da qualsiasi Data Workbench autorizzata fornendo l'accesso a tutte le directory e i file nella directory di installazione del prodotto, inclusi i file di configurazione e di ricerca.
title: Server Files Manager (Gestore dei file del server)
uuid: 62625b9d-587f-4a78-8328-2270869909f8
exl-id: 9ac7e95d-47e5-4862-a16e-bee0df1d3d15
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 1%

---

# Server Files Manager (Gestore dei file del server){#server-files-manager}

Server Files Manager consente di amministrare e gestire in remoto i computer server di Data Workbench da qualsiasi Data Workbench autorizzata fornendo l&#39;accesso a tutte le directory e i file nella directory di installazione del prodotto, inclusi i file di configurazione e di ricerca.

È possibile accedere a [!DNL Server Files Manager] utilizzando il menu [!DNL Admin], facendo clic con il pulsante destro del mouse sul nodo del computer del server di Data Workbench in [!DNL Servers Manager] e facendo clic su **[!UICONTROL Server Files]**.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>È possibile creare nuovi gestori di file server che visualizzano le directory selezionate. Vedere [Creazione di nuovi gestori di file server](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816).

La colonna a sinistra di [!DNL Server Files Manager] elenca i nomi dei file e delle cartelle. I segni di spunta nelle colonne centrale e destra indicano dove si trovano nella struttura del file queste directory e questi file.

Se un file risiede nella directory di installazione del prodotto, la colonna *nome server* (ad esempio, Data Workbench server) contiene un segno di spunta. Se un file si trova sul computer dell&#39;utente della Data Workbench nella directory di installazione *Data Workbench*\Temp, la colonna [!DNL Temp] contiene un segno di spunta. Il colore dei segni di spunta indica se i file che risiedono in posizioni diverse sono stati modificati contemporaneamente.

* Un segno di spunta rosso nella colonna del nome del server indica che la cartella o il file si trova nel computer del server di Data Workbench.
* Un segno di spunta rosso nella colonna [!DNL Temp] indica che la copia locale del file o della cartella ha la stessa data e ora di modifica del file o della cartella sul computer del server di Data Workbench.
* Un segno di spunta bianco nella colonna [!DNL Temp] indica che il file o la cartella nella directory di installazione *Data Workbench*\Temp ha una data e un&#39;ora modificate diverse rispetto al file o alla cartella nel computer del server Data Workbench.

L&#39;immagine seguente mostra il [!DNL Server Files Manager] con segni di spunta sia rossi che bianchi:

![](assets/vis_FileManager_RedWhiteChecks.png)

**Per gestire le directory e i file utilizzando il comando[!DNL Server Files Manager]**

È possibile utilizzare [!DNL Server Files Manager] per manipolare directory e file su un computer server Data Workbench.

Nella tabella seguente sono elencate le attività che possono essere completate utilizzando [!DNL Server Files Manager]:

<table id="table_D217AE5A878542EC8B604812A61819C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per eseguire questa operazione.. </th> 
   <th colname="col2" class="entry"> Fai questo... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Visualizzazione dei file in qualsiasi directory </p> </td> 
   <td colname="col2"> <p>Fai clic sul nome della directory per visualizzarne il contenuto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nascondere il contenuto di una directory </p> </td> 
   <td colname="col2"> <p>Fai clic sul nome della directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare i dettagli di una directory </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sulla cella accanto alla directory nel nome del server o nella colonna <span class="wintitle"> Temp</span> . Vengono visualizzate le seguenti informazioni: </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">Path. Percorso della directory. </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">Asciugare. Nome della directory. </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">Da. La posizione della directory, Remote o Temp. </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">Data (solo colonna Temp). Data di creazione o data dell'ultima revisione della copia locale. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare i dettagli di un file </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta accanto al file nella colonna <span class="wintitle"> Temp</span> o nel nome del server. Vengono visualizzate le seguenti informazioni: </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">Percorso. Percorso del file. </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">File. Nome del file. </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">Da. La posizione della directory, Remote o Temp. </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">Data. Data dell'ultima revisione del file. </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">Dimensione. Dimensione del file. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per scaricare una directory nel computer locale </p> </td> 
   <td colname="col2"> <p>Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna <i>nome server</i> per questa directory e fare clic su <span class="uicontrol"> Make Directory Local</span>. Nella colonna <span class="wintitle"> Temp</span> viene visualizzato un segno di spunta per la directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per scaricare un file nel computer locale </p> </td> 
   <td colname="col2"> <p>Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna <i>nome server</i> del file e fare clic su <span class="uicontrol"> Rendi locale</span>. Nella colonna <span class="wintitle"> Temp</span> viene visualizzato un segno di spunta per il file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per scaricare l'ultima parte di un file di registro nel computer locale </p> </td> 
   <td colname="col2"> <p>Per evitare di dover scaricare un intero file di registro (soprattutto quando si è a conoscenza che il messaggio di errore è vicino alla fine del file), fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server del file, fare clic su <span class="uicontrol"> Tail</span> e selezionare la dimensione della porzione che si desidera scaricare. Nella colonna <span class="wintitle"> Temp</span> viene visualizzato un segno di spunta per il file. Il file locale contiene solo la quantità di dati specificata, a partire dalla fine del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per aprire una directory </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta per la directory nella colonna <span class="wintitle"> Temp</span> e fai clic su <span class="uicontrol"> Apri</span> &gt; <span class="uicontrol"> folder</span> (Apri cartella). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per aprire un file </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna <span class="wintitle"> Temp</span>, fai clic su <span class="uicontrol"> Apri</span>, quindi fai clic su <span class="uicontrol"> Data Workbench</span>, <span class="uicontrol"> in Blocco note</span> o nella cartella <span class="uicontrol"></span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Salvare una copia locale di una directory sul server Data Workbench </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta per la directory nella colonna <span class="wintitle"> Temp</span> e fai clic su <span class="uicontrol"> Salva directory in</span> &gt; <i>&lt;<span class="uicontrol"> nome profilo</span></i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Salvare una copia locale di un file sul server Data Workbench </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna <span class="wintitle"> Temp</span> e fai clic su <span class="uicontrol"> Salva su</span> &gt; <i>&lt;<span class="uicontrol"> nome profilo</span></i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rimuovere una copia locale di una directory o di un file </p> </td> 
   <td colname="col2"> <p>Fare clic con il pulsante destro del mouse sul segno di spunta per la directory o il file nella colonna <span class="wintitle"> Temp</span> e fare clic su <span class="uicontrol"> Rimuovi</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Copiare e incollare un file come allegato e-mail in Microsoft Outlook </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna <span class="wintitle"> Temp</span> e fai clic su <span class="uicontrol"> Copia</span>. Nel corpo dell’e-mail, premere Ctrl+v per allegare il file. </p> </td> 
  </tr> 
 </tbody> 
</table>
