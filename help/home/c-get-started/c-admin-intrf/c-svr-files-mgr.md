---
description: Server Files Manager consente di amministrare e gestire in remoto i computer del server Workbench dati da qualsiasi Workbench dati autorizzato fornendo l'accesso a tutte le directory e i file nella directory di installazione del prodotto, compresi i file di configurazione e di ricerca.
solution: Analytics
title: Server Files Manager
topic: Data workbench
uuid: 62625b9d-587f-4a78-8328-2270869909f8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Server Files Manager{#server-files-manager}

Server Files Manager consente di amministrare e gestire in remoto i computer del server Workbench dati da qualsiasi Workbench dati autorizzato fornendo l&#39;accesso a tutte le directory e i file nella directory di installazione del prodotto, compresi i file di configurazione e di ricerca.

È possibile accedere al [!DNL Server Files Manager] menu e [!DNL Admin] fare clic con il pulsante destro del mouse sul nodo del computer del server Workbench dati [!DNL Servers Manager] e fare clic **[!UICONTROL Server Files]**.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>È possibile creare nuovi gestori di file server che visualizzano directory selezionate. Consultate [Creazione di nuovi gestori](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816)di file server.

Nella colonna a sinistra sono [!DNL Server Files Manager] elencati i nomi dei file e delle cartelle. I segni di spunta nelle colonne centrale e destra indicano dove risiedono tali directory e file nella struttura del file.

Se un file risiede nella directory di installazione del prodotto, la colonna nome *del* server (ad esempio, server Workbench dati) contiene un segno di spunta. Se un file risiede nel computer dell&#39;utente di Workbench dati nella directory *\Temp di installazione di Workbench* dati, la [!DNL Temp] colonna contiene un segno di spunta. Il colore dei segni di spunta indica se i file che risiedono in posizioni diverse sono stati modificati contemporaneamente.

* Un segno di spunta rosso nella colonna del nome del server indica che la cartella o il file risiede nel computer server Workbench dati.
* Un segno di spunta rosso nella [!DNL Temp] colonna indica che la copia locale del file o della cartella ha la stessa data e ora di modifica del file o della cartella sul computer del server Workbench dati.
* Un segno di spunta bianco nella [!DNL Temp] colonna indica che il file o la cartella nella directory *di installazione di Workbench* dati\Temp ha una data e un&#39;ora diverse da quelle del file o della cartella sul computer del server Workbench dati.

L’immagine seguente mostra [!DNL Server Files Manager] con indicatori di spunta sia rossi che bianchi:

![](assets/vis_FileManager_RedWhiteChecks.png)

**Per gestire directory e file tramite l&#39;operatore[!DNL Server Files Manager]**

È possibile utilizzare [!DNL Server Files Manager] per manipolare directory e file su un computer server Workbench dati.

Nella tabella seguente sono elencate le attività che è possibile completare utilizzando [!DNL Server Files Manager]:

<table id="table_D217AE5A878542EC8B604812A61819C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per eseguire questa operazione... </th> 
   <th colname="col2" class="entry"> Fai questo... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Visualizzazione dei file all'interno di qualsiasi directory </p> </td> 
   <td colname="col2"> <p>Fate clic sul nome della directory per visualizzarne il contenuto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nascondere il contenuto di una directory </p> </td> 
   <td colname="col2"> <p>Fate clic sul nome della directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare i dettagli di una directory </p> </td> 
   <td colname="col2"> <p>Fare clic con il pulsante destro del mouse sulla cella accanto alla directory nel nome del server o nella colonna <span class="wintitle"> Temp</span> . Vengono visualizzate le informazioni seguenti: </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">Percorso. Percorso della directory. </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">Dir. Nome della directory. </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">Da. La posizione della directory, Remote o Temp. </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">Data (solo colonna Temp). Data di creazione o data dell'ultima revisione alla copia locale. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare i dettagli di un file </p> </td> 
   <td colname="col2"> <p>Fare clic con il pulsante destro del mouse sul segno di spunta accanto al file nella colonna <span class="wintitle"> Temp</span> o Nome del server. Vengono visualizzate le informazioni seguenti: </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">Percorso. Percorso del file. </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">File. Nome del file. </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">Da. La posizione della directory, Remote o Temp. </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">Data. Data dell’ultima revisione del file. </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">Dimensione. Dimensione del file. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per scaricare una directory nel computer locale </p> </td> 
   <td colname="col2"> <p>Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome <i>del</i> server relativa a questa directory e scegliere <span class="uicontrol"> Rendi directory locale</span>. Nella colonna <span class="wintitle"> Temp</span> viene visualizzato un segno di spunta per la directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per scaricare un file nel computer locale </p> </td> 
   <td colname="col2"> <p>Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome <i>del</i> server relativa a questo file, quindi fare clic su <span class="uicontrol"> Rendi locale</span>. Nella colonna <span class="wintitle"> Temp</span> viene visualizzato un segno di spunta per il file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per scaricare l'ultima parte di un file di registro nel computer locale </p> </td> 
   <td colname="col2"> <p>Per evitare di dover scaricare un intero file di registro (soprattutto quando si è a conoscenza che il messaggio di errore è vicino alla fine del file), fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server relativa al file, fare clic su <span class="uicontrol"> Coda</span>e selezionare la dimensione della porzione da scaricare. Nella colonna <span class="wintitle"> Temp</span> viene visualizzato un segno di spunta per il file. Il file locale contiene solo la quantità di dati specificata, a partire dalla fine del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per aprire una directory </p> </td> 
   <td colname="col2"> <p>Fate clic con il pulsante destro del mouse sul segno di spunta della directory nella colonna <span class="wintitle"> Temp</span> e fate clic su <span class="uicontrol"> Apri</span> &gt; <span class="uicontrol"> cartella</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per aprire un file </p> </td> 
   <td colname="col2"> <p>Fare clic con il pulsante destro del mouse sul segno di spunta per il file nella <span class="wintitle"> colonna Temp</span> , fare clic su <span class="uicontrol"> Open</span>, quindi su <span class="uicontrol"> Workbench</span>dati, <span class="uicontrol"> in Blocco note</span>o <span class="uicontrol"> nella cartella</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Salvare una copia locale di una directory nel server Workbench dati </p> </td> 
   <td colname="col2"> <p>Fare clic con il pulsante destro del mouse sul segno di spunta della directory nella colonna <span class="wintitle"> Temp</span> e scegliere <span class="uicontrol"> Salva directory in &gt;</span> &lt; <i>nome<span class="uicontrol"> profilo&gt;</span></i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Salvare una copia locale di un file nel server Workbench dati </p> </td> 
   <td colname="col2"> <p>Fare clic con il pulsante destro del mouse sul segno di spunta del file nella colonna <span class="wintitle"> Temp</span> e scegliere <span class="uicontrol"> Salva in &gt;</span> &lt; <i>nome<span class="uicontrol"> profilo&gt;</span></i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rimozione di una copia locale di una directory o di un file </p> </td> 
   <td colname="col2"> <p>Fare clic con il pulsante destro del mouse sul segno di spunta per la directory o il file nella colonna <span class="wintitle"> Temp</span> e scegliere <span class="uicontrol"> Rimuovi</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Copiare e incollare un file come allegato e-mail in Microsoft Outlook </p> </td> 
   <td colname="col2"> <p>Fare clic con il pulsante destro del mouse sul segno di spunta del file nella colonna <span class="wintitle"> Temp</span> e scegliere <span class="uicontrol"> Copia</span>. Nel corpo dell’e-mail, premere Ctrl+v per allegare il file. </p> </td> 
  </tr> 
 </tbody> 
</table>

