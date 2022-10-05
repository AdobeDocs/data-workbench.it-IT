---
description: Server Files Manager consente di amministrare e gestire in remoto i computer del server di Data Workbench da qualsiasi Data Workbench autorizzata fornendo l'accesso a tutte le directory e i file nella directory di installazione del prodotto, inclusi i file di configurazione e di ricerca.
title: Server Files Manager (Gestore dei file del server)
uuid: 62625b9d-587f-4a78-8328-2270869909f8
exl-id: 9ac7e95d-47e5-4862-a16e-bee0df1d3d15
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 2%

---

# Server Files Manager (Gestore dei file del server){#server-files-manager}

{{eol}}

Server Files Manager consente di amministrare e gestire in remoto i computer del server di Data Workbench da qualsiasi Data Workbench autorizzata fornendo l&#39;accesso a tutte le directory e i file nella directory di installazione del prodotto, inclusi i file di configurazione e di ricerca.

Puoi accedere al [!DNL Server Files Manager] utilizzando [!DNL Admin] e facendo clic con il pulsante destro del mouse sul nodo del computer del server di Data Workbench nel [!DNL Servers Manager] e facendo clic su **[!UICONTROL Server Files]**.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>È possibile creare nuovi gestori di file server che visualizzano le directory selezionate. Vedi [Creazione di nuovi gestori di file server](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816).

La colonna a sinistra di [!DNL Server Files Manager] elenca i nomi dei file e delle cartelle. I segni di spunta nelle colonne centrale e destra indicano dove si trovano nella struttura del file queste directory e questi file.

Se un file si trova nella directory di installazione del prodotto, il *nome server* (ad esempio, Data Workbench server) la colonna contiene un segno di spunta. Se un file si trova nel computer dell’utente della Data Workbench nel *Data Workbench directory di installazione*\Temp directory, la [!DNL Temp] La colonna contiene un segno di spunta. Il colore dei segni di spunta indica se i file che risiedono in posizioni diverse sono stati modificati contemporaneamente.

* Un segno di spunta rosso nella colonna del nome del server indica che la cartella o il file si trova nel computer del server di Data Workbench.
* Un segno di spunta rosso nel [!DNL Temp] indica che la copia locale del file o della cartella ha la stessa data e ora di modifica del file o della cartella sul computer del server di Data Workbench.
* Un segno di spunta bianco nel [!DNL Temp] indica che il file o la cartella nel *Data Workbench directory di installazione*\Temp directory ha una data e un’ora modificate diverse dal file o dalla cartella sul computer del server Data Workbench.

L’immagine seguente mostra il [!DNL Server Files Manager] con segni di spunta sia rossi che bianchi:

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
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sulla cella accanto alla directory nel nome del server o <span class="wintitle"> Temp.</span> colonna. Vengono visualizzate le seguenti informazioni: </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">Path. Percorso della directory. </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">Asciugare. Nome della directory. </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">Da. La posizione della directory, Remote o Temp. </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">Data (solo colonna Temp). Data di creazione o data dell'ultima revisione della copia locale. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare i dettagli di un file </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta accanto al file nel nome del server o <span class="wintitle"> Temp.</span> colonna. Vengono visualizzate le seguenti informazioni: </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">Percorso. Percorso del file. </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">File. Nome del file. </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">Da. La posizione della directory, Remote o Temp. </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">Data. Data dell'ultima revisione del file. </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">Dimensione. dimensione del file. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per scaricare una directory nel computer locale </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta nel <i>nome server</i> colonna per questa directory e fai clic su <span class="uicontrol"> Crea directory locale</span>. Un segno di spunta per la directory viene visualizzato nel <span class="wintitle"> Temp.</span> colonna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per scaricare un file nel computer locale </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta nel <i>nome server</i> e fai clic su <span class="uicontrol"> Rendi locale</span>. Nel <span class="wintitle"> Temp.</span> colonna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per scaricare l'ultima parte di un file di registro nel computer locale </p> </td> 
   <td colname="col2"> <p>Per evitare di dover scaricare un intero file di log (soprattutto quando si è a conoscenza che il messaggio di errore è vicino alla fine del file), fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per il file, fare clic su <span class="uicontrol"> Coda</span>, quindi seleziona la dimensione della porzione da scaricare. Nel <span class="wintitle"> Temp.</span> colonna. Il file locale contiene solo la quantità di dati specificata, a partire dalla fine del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per aprire una directory </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta per la directory nel <span class="wintitle"> Temp.</span> e fai clic su <span class="uicontrol"> Apri</span> &gt; <span class="uicontrol"> cartella</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per aprire un file </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta per il file nel <span class="wintitle"> Temp.</span> colonna, fai clic su <span class="uicontrol"> Apri</span>, quindi fai clic su in <span class="uicontrol"> Data Workbench</span>, <span class="uicontrol"> in Blocco note</span>oppure <span class="uicontrol"> cartella</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Salvare una copia locale di una directory sul server Data Workbench </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta per la directory nel <span class="wintitle"> Temp.</span> e fai clic su <span class="uicontrol"> Salva directory in</span> &gt; <i>&lt;<span class="uicontrol"> nome profilo</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Salvare una copia locale di un file sul server Data Workbench </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta per il file nel <span class="wintitle"> Temp.</span> e fai clic su <span class="uicontrol"> Salva in</span> &gt; <i>&lt;<span class="uicontrol"> nome profilo</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rimuovere una copia locale di una directory o di un file </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta per la directory o il file nel <span class="wintitle"> Temp.</span> e fai clic su <span class="uicontrol"> Rimuovi</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Copiare e incollare un file come allegato e-mail in Microsoft Outlook </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sul segno di spunta per il file nel <span class="wintitle"> Temp.</span> e fai clic su <span class="uicontrol"> Copia</span>. Nel corpo dell’e-mail, premere Ctrl+v per allegare il file. </p> </td> 
  </tr> 
 </tbody> 
</table>
