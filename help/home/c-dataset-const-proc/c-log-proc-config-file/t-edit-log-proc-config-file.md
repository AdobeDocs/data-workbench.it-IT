---
description: Passaggi per modificare il file Log Processing.cfg per un profilo dataset.
solution: Analytics
title: Modifica del file di configurazione dell'elaborazione del registro
topic: Data workbench
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Modifica del file di configurazione dell&#39;elaborazione del registro{#editing-the-log-processing-configuration-file}

Passaggi per modificare il file Log Processing.cfg per un profilo dataset.

1. Quando lavori nel profilo del set di dati, apri il set di dati [!DNL Profile Manager] e fai clic **[!UICONTROL Dataset]** per visualizzarne il contenuto.

   Per informazioni sull&#39;apertura e l&#39;utilizzo di [!DNL Profile Manager], vedere la Guida *utente di Workbench* dati.

   >[!NOTE]
   >
   >All&#39;interno della directory Dataset potrebbe esistere una sottodirectory Elaborazione log. Questa sottodirectory contiene i [!DNL Log Processing Dataset Include] file creati per uno o più profili ereditati. Consulta [Set di dati Includi file](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Log Processing.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Viene [!DNL Log Processing.cfg] visualizzata la finestra.

   È inoltre possibile aprire il [!DNL Log Processing.cfg] file da un [!DNL Transformation Dependency Map]. Per informazioni sulle mappe delle dipendenze di trasformazione, vedere Strumenti [di configurazione](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)DataSet.

1. Modificate i parametri nel file di configurazione utilizzando la seguente tabella come guida.

   Quando si modifica il [!DNL Log Processing.cfg] file all&#39;interno di una finestra del workbench dati, è possibile utilizzare i tasti di scelta rapida per le funzioni di modifica di base, inclusi Taglia ( Ctrl+x ), Copia ( Ctrl+c), Incolla ( Ctrl+v ), Annulla ( Ctrl+z ), Ripristina ( Ctrl+Maiusc+Z ), Seleziona la sezione (clic+trascinamento) e seleziona tutto ( Ctrl+a ). Potete anche utilizzare i collegamenti per copiare e incollare il testo da un file di configurazione ( [!DNL .cfg]) a un altro.

   >[!NOTE]
   >
   >Un [!DNL Log Processing Dataset Include] file per un profilo ereditato contiene un sottoinsieme dei parametri descritti nella tabella seguente e alcuni parametri aggiuntivi. Consulta [Set di dati Includi file](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

   <table id="table_BC7D3635C94049A9B608463AC1DBFA69">
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parametro </th> 
      <th colname="col2" class="entry"> Descrizione </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Origini log </td> 
      <td colname="col2"> Le origini dei dati. Vedere <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Origini di registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ora di fine </td> 
      <td colname="col2"> <p>Facoltativo. Filtrare i dati per includere voci di registro con marche temporali fino a questa ora, ma non incluse. Adobe consiglia di utilizzare per il momento uno dei seguenti formati: </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">1 gennaio 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">1 gen 2013 HH:MM:SS GMT </li> 
      </ul> <p>Ad esempio, se specificate il 29 luglio 2013 00:00:00 EDT come Ora di fine, i dati sono inclusi fino al 28 luglio 2013, alle 11:59:59 PM EDT. Consulta <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtri dati </a>. </p> <p>È necessario specificare un fuso orario. Il fuso orario predefinito non è GMT se non specificato. Per un elenco delle abbreviazioni del fuso orario supportate dal server workbench dati, vedere <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codici del fuso orario </a>. </p> <p> <p>Nota:  Il parametro Use Start/End Times per <span class="wintitle"> Sensor </span>, file di registro e origini XML è correlato a questo parametro. Vedere le sezioni di <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Origini di registro </a> che illustrano questi tipi di origine. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Campi </td> 
      <td colname="col2"> Facoltativo. Adobe consiglia di definire <span class="wintitle"> i campi </span> in uno o più file di <span class="wintitle"> dati di elaborazione del registro Include </span> . Consulta <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Log Processing Dataset Includi file </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Numero massimo di byte chiave del gruppo </td> 
      <td colname="col2"> <p>Quantità massima di dati evento che il server può elaborare per un singolo ID di tracciamento. I dati che superano questo limite vengono filtrati dal processo di costruzione dell'insieme di dati. Questo valore deve essere impostato su 2e6 quando la divisione dei tasti è attiva e su 1e6 quando la divisione dei tasti non è attiva. Vedere <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisione tasti </a>. </p> <p> <p>Nota:  Non modificate questo valore senza consultare Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Soglia hash </td> 
      <td colname="col2"> <p>Facoltativo. Fattore di campionamento per il sottocampionamento casuale delle righe. Se è impostato su un numero n, solo uno su ogni n ID di tracciamento entra nel dataset, riducendo il numero totale di righe nel dataset di un fattore n. </p> <p>Per creare un set di dati che richiede una precisione del 100% (ovvero per includere tutte le righe), impostare Soglia hash su 1. </p> <p>Valori: </p> <span class="filepath"> Soglia hash = 1 </span> (100% dei dati, comprese tutte le righe). <p> <span class="filepath"> Soglia hash = 2 </span> (1/2 di dati e metà delle righe.) </p> <p> <span class="filepath"> Soglia hash = 3 </span>(1/3 di dati e include una delle tre righe, ma arrotonda al 34% in Completamento query) </p> <p> <span class="filepath"> Soglia hash = 4 </span>(1/4 di dati e include una riga su quattro). </p> <p> </p> <p> <p>Nota:  L'utilizzo di una soglia <span class="filepath"> hash = 8 </span> fornisce 1/8 dei dati, pari al 12,5%. Tuttavia, il valore <span class="uicontrol"> Completamento query </span> viene arrotondato al 13% per questo valore. Altri esempi includono una soglia <span class="filepath"> hash = 6 </span> che restituisce una risoluzione query del 17%. Una soglia <span class="filepath"> hash = 13 </span>restituisce una risoluzione query dell'8%. </p> </p> <p>Se <span class="wintitle"> Hash Threshold </span> è specificato nei file <span class="filepath"> Log Processing.cfg </span> e <span class="filepath"> Transformation.cfg </span> , non viene applicato in sequenza; viene applicato il valore massimo impostato in uno dei file di configurazione. Consulta <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtri dati </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condizione voce di registro </td> 
      <td colname="col2"> Facoltativo. Definisce le regole in base alle quali le voci di registro vengono considerate per l'inclusione nel set di dati. Vedere <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condizione di voce di registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rielabora </td> 
      <td colname="col2"> <p>Facoltativo. È possibile inserire qui qualsiasi carattere o combinazione di caratteri. La modifica di questo parametro e il salvataggio del file nel computer del workbench dati avvia la rielaborazione dei dati. </p> <p>Vedere <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Rielaborazione e trasformazione </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dividi spazio parentesi </td> 
      <td colname="col2"> <p>Parametro coinvolto nella divisione chiave. Il valore deve essere 6e6 quando è attiva la divisione chiave. Vedere <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split"> Divisione tasti </a>. </p> <p> <p>Nota:  Non modificate questo valore senza consultare Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dividi byte chiave </td> 
      <td colname="col2"> <p>Parametro coinvolto nella divisione chiave. Il valore deve essere 1e6 quando la divisione dei tasti è attiva e 0 quando la divisione dei tasti non è attiva. Vedere <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisione tasti </a>. </p> <p> <p>Nota:  Non modificate questo valore senza consultare Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rapporto spazio chiave </td> 
      <td colname="col2"> <p>Parametro coinvolto nella divisione chiave. Il valore deve essere 10 se è attiva la divisione chiave. Vedere <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisione tasti </a>. </p> <p> <p>Nota:  Non modificate questo valore senza consultare Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Stadi </td> 
      <td colname="col2"> <p>Facoltativo. I nomi delle fasi di elaborazione che possono essere utilizzate nel set di dati di elaborazione dei <span class="wintitle"> log includono </span> i file. Le fasi di elaborazione consentono di ordinare le trasformazioni definite in <span class="wintitle"> Log Processing Dataset Include </span> i file. Questo parametro è molto utile se avete definito una o più trasformazioni all'interno di più file <span class="wintitle"> Log Processing Dataset Include e desiderate che </span> le trasformazioni specifiche vengano eseguite in punti specifici durante l'elaborazione del registro. </p> <p>L'ordine in cui si elencano le fasi qui determina l'ordine in cui le trasformazioni nei file <span class="wintitle"> </span> Log Processing Dataset Include vengono eseguite durante l'elaborazione del registro. La preelaborazione e la postelaborazione sono fasi integrate. La preelaborazione è sempre la prima fase e la postelaborazione è sempre l'ultima fase. Per impostazione predefinita, è presente uno stage denominato Default. </p> <p> <b>Per aggiungere una nuova fase di elaborazione</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">Nella finestra <span class="filepath"> Log Processing.cfg </span> , fare clic con il pulsante destro del mouse su <span class="uicontrol"> Stages </span> e scegliere <span class="uicontrol"> Aggiungi nuovo </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">Immettete un nome per il nuovo passaggio. </li> 
      </ul> </p> <p> <b>Per eliminare una fase di elaborazione esistente</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">Fare clic con il pulsante destro del mouse sul numero corrispondente all'area di visualizzazione da eliminare e scegliere <span class="uicontrol"> Rimuovi </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Nota:  Quando si specifica uno <span class="wintitle"> stage </span> in un file <span class="wintitle"> Log Processing Dataset Include, </span> il nome dell'area di visualizzazione deve corrispondere esattamente al nome immesso qui. Consulta <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Set di dati Includi file </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ora di inizio </td> 
      <td colname="col2"> <p>Facoltativo. Filtrare i dati per includere voci di registro con marche temporali all’ora o dopo. Adobe consiglia di utilizzare per il momento uno dei seguenti formati: </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 1 gennaio 2013 HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 1 gen 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Ad esempio, se specificate "29 luglio 2013 00:00:00 EDT" come Ora di inizio, i dati iniziano il 29 luglio 2013, alle 01:00:00 EDT. Consulta <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtri dati </a>. </p> <p> È necessario specificare un fuso orario. Il fuso orario predefinito non è GMT se non specificato. Per un elenco delle abbreviazioni del fuso orario supportate dal server workbench dati, vedere <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codici del fuso orario </a>. </p> <p> <p>Nota:  Il parametro Use Start/End Times per <span class="wintitle"> Sensor </span>, file di registro e origini XML è correlato a questo parametro. Vedere le sezioni di <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Origini di registro </a> che illustrano questi tipi di origine. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuso orario </td> 
      <td colname="col2"> <p>Facoltativo. Fuso orario del server workbench dati utilizzato per le conversioni temporali (come la conversione rappresentata dal campo x-local-timestring) durante l'elaborazione del registro. </p> <p> <p>Nota:  È necessario specificare il Fuso orario se si desidera accedere al campo del tempo convertito durante la fase di elaborazione del registro della costruzione del dataset. In caso contrario, il server workbench dati registra un errore nei registri eventi. </p> </p> <p>Consultate <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fusi orari </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Trasformazioni </td> 
      <td colname="col2"> Facoltativo. Adobe consiglia di definire le trasformazioni per l'elaborazione del registro in uno o più <span class="wintitle"> </span> file di inclusione del set di dati di elaborazione del registro. Consulta <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Log Processing Dataset Includi file </a>. </td> 
   </tr> 
   </tbody> 
   </table>

1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.
1. Fare [!DNL Profile Manager]clic con il pulsante destro del mouse sul segno di spunta [!DNL Log Processing.cfg]nella [!DNL User] colonna, quindi scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>* per rendere attive le modifiche locali. La rielaborazione dei dati inizia dopo la sincronizzazione del profilo del dataset.

   >[!NOTE]
   >
   >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe, in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti per tali profili.

   Per ulteriori informazioni sulla rielaborazione dei dati, vedere [Rielaborazione e trasformazione](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
