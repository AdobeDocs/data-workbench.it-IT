---
description: Passaggi per modificare il file Log Processing.cfg per un profilo di set di dati.
title: Modifica del file di configurazione dell’elaborazione del registro
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
exl-id: 294063ef-6771-4310-8198-df57fab1e2b4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 2%

---

# Modifica del file di configurazione dell’elaborazione del registro{#editing-the-log-processing-configuration-file}

Passaggi per modificare il file Log Processing.cfg per un profilo di set di dati.

1. Quando lavori nel profilo del set di dati, apri il [!DNL Profile Manager] e fai clic su **[!UICONTROL Dataset]** per visualizzarne il contenuto.

   Per informazioni sull&#39;apertura e l&#39;utilizzo di [!DNL Profile Manager], vedere la *Guida utente alla Data Workbench*.

   >[!NOTE]
   >
   >All’interno della directory Dataset potrebbe esistere una sottodirectory Elaborazione registro. Questa sottodirectory contiene i file [!DNL Log Processing Dataset Include] creati per uno o più profili ereditati. Consulta [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md) (File inclusi nel set di dati).

1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Log Processing.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Viene visualizzata la finestra [!DNL Log Processing.cfg].

   Puoi anche aprire il file [!DNL Log Processing.cfg] da un [!DNL Transformation Dependency Map]. Per informazioni sulle mappe delle dipendenze di trasformazione, vedere [Strumenti di configurazione del set di dati](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Modifica i parametri nel file di configurazione utilizzando la seguente tabella come guida.

   Quando modifichi il file [!DNL Log Processing.cfg] all’interno di una finestra di Data Workbench, puoi utilizzare i tasti di scelta rapida per le funzioni di modifica di base, tra cui Taglia ( Ctrl+x ), Copia ( Ctrl+c) , Incolla ( Ctrl+v ), Annulla ( Ctrl+z ), Ripristina ( Ctrl+Maiusc+Z ), seleziona la sezione (clic+trascina) e seleziona tutto ( Ctrl+a ). È inoltre possibile utilizzare le scelte rapide per copiare e incollare il testo da un file di configurazione ( [!DNL .cfg]) a un altro.

   >[!NOTE]
   >
   >Un file [!DNL Log Processing Dataset Include] per un profilo ereditato contiene un sottoinsieme dei parametri descritti nella tabella seguente e alcuni parametri aggiuntivi. Consulta [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md) (File inclusi nel set di dati).

   <table id="table_BC7D3635C94049A9B608463AC1DBFA69">
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parametro </th> 
      <th colname="col2" class="entry"> Descrizione </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Origini del registro </td> 
      <td colname="col2"> Le fonti di dati. Vedere <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Origini del registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ora di fine </td> 
      <td colname="col2"> <p>Facoltativo. Filtrare i dati per includere voci di registro con marche temporali fino a questo momento, ma non incluso. L'Adobe consiglia di utilizzare per il tempo uno dei seguenti formati: </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">1 gennaio 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">1 gennaio 2013 OH:MM:SS GMT </li> 
      </ul> <p>Ad esempio, specificando 29 luglio 2013 00:00:00 EDT come Ora di fine vengono inclusi i dati fino al 28 luglio 2013, alle 11:59:59 PM EDT. Consulta <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtri dati </a>. </p> <p>È necessario specificare un fuso orario. Il fuso orario non viene impostato su GMT se non viene specificato. Per un elenco delle abbreviazioni del fuso orario supportate dal server di Data Workbench, consulta <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codici del fuso orario </a>. </p> <p> <p>Nota:  Il parametro Use Start/End Times per <span class="wintitle"> Sensor </span>, file di registro e origini XML è correlato a questo parametro. Consulta le sezioni di <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Origini di log </a> che illustrano questi tipi di origine. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Campi </td> 
      <td colname="col2"> Facoltativo. L’Adobe consiglia di definire <span class="wintitle"> i campi </span> in uno o più <span class="wintitle"> Dataset di elaborazione del registro che includono </span> file. Consulta <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Elaborazione del registro Dataset Include Files (File inclusi nel set di dati) </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Byte chiave massimi del gruppo </td> 
      <td colname="col2"> <p>Quantità massima di dati evento che il server può elaborare per un singolo ID di tracciamento. I dati che superano questo limite vengono filtrati dal processo di costruzione del set di dati. Questo valore deve essere impostato su 2e6 quando la suddivisione dei tasti è attiva e su 1e6 quando la suddivisione dei tasti non è attiva. Vedere <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisione tasti </a>. </p> <p> <p>Nota:  Non modificare questo valore senza consultare un Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Soglia hash </td> 
      <td colname="col2"> <p>Facoltativo. Un fattore di campionamento per il sottocampionamento casuale delle righe. Se è impostato su un numero n, solo uno su ogni n ID di tracciamento entra nel set di dati, riducendo il numero totale di righe nel set di dati di un fattore n. </p> <p>Per creare un set di dati che richiede una precisione del 100% (ovvero per includere tutte le righe), imposta la soglia hash su 1. </p> <p>Valori: </p> <span class="filepath"> Soglia hash = 1  </span> (100% dei dati, comprese tutte le righe). <p> <span class="filepath"> Soglia hash = 2  </span> (1/2 di dati e include metà delle righe). </p> <p> <span class="filepath"> Soglia hash = 3  </span>(1/3 di dati e include una delle tre righe, ma arrotonda al 34% in Completamento query) </p> <p> <span class="filepath"> Soglia hash = 4  </span>(1/4 dei dati e include una riga su quattro). </p> <p> </p> <p> <p>Nota:  Utilizzando una <span class="filepath"> Hash Threshold = 8 </span> si fornisce 1/8 dei dati, che è del 12,5%. Tuttavia il valore <span class="uicontrol"> Completamento query </span> viene arrotondato al 13% per questo valore. Altri esempi includono una <span class="filepath"> soglia hash = 6 </span> che restituisce una risoluzione query del 17%. Una <span class="filepath"> Soglia hash = 13 </span>restituisce una risoluzione query dell'8%. </p> </p> <p>Se <span class="wintitle"> Hash Threshold </span> è specificato nei file <span class="filepath"> Log Processing.cfg </span> e <span class="filepath"> Transformation.cfg </span>, non viene applicato in sequenza; si applica il valore massimo impostato in entrambi i file di configurazione. Consulta <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtri dati </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condizione voce di registro (Log Entry Condition) </td> 
      <td colname="col2"> Facoltativo. Definisce le regole in base alle quali le voci di registro vengono considerate per l’inclusione nel set di dati. Vedere <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condizione voce di registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rielaborazione </td> 
      <td colname="col2"> <p>Facoltativo. È possibile inserire qui qualsiasi carattere o combinazione di caratteri. La modifica di questo parametro e il salvataggio del file nel computer server di Data Workbench avvia la rielaborazione dei dati. </p> <p>Vedere <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Rielaborazione e riconversione </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Spazio a blocchi della chiave di divisione </td> 
      <td colname="col2"> <p>Parametro coinvolto nella suddivisione chiave. Il valore deve essere 6e6 quando la suddivisione chiave è attiva. Vedere <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split"> Divisione tasti </a>. </p> <p> <p>Nota:  Non modificare questo valore senza consultare un Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Byte chiave divisi </td> 
      <td colname="col2"> <p>Parametro coinvolto nella suddivisione chiave. Il valore deve essere 1e6 quando la suddivisione chiave è attiva e 0 quando la suddivisione chiave non è attiva. Vedere <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisione tasti </a>. </p> <p> <p>Nota:  Non modificare questo valore senza consultare un Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rapporto spazio chiave diviso </td> 
      <td colname="col2"> <p>Parametro coinvolto nella suddivisione chiave. Il valore deve essere 10 quando la suddivisione chiave è attiva. Vedere <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisione tasti </a>. </p> <p> <p>Nota:  Non modificare questo valore senza consultare un Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fasi </td> 
      <td colname="col2"> <p>Facoltativo. I nomi delle fasi di elaborazione che possono essere utilizzate nei file <span class="wintitle"> Dataset di elaborazione del registro Includono </span>. Le fasi di elaborazione forniscono un modo per ordinare le trasformazioni definite in <span class="wintitle"> Log Processing Dataset Include </span> files . Questo parametro è molto utile se hai definito una o più trasformazioni all’interno di più file di inclusione del set di dati di elaborazione del registro </span> e desideri che trasformazioni specifiche vengano eseguite in punti specifici durante l’elaborazione del registro.<span class="wintitle"> </span></p> <p>L'ordine in cui si elencano le fasi qui determina l'ordine in cui le trasformazioni nei file <span class="wintitle"> Dataset di elaborazione del registro Dataset Include </span> vengono eseguite durante l'elaborazione del registro. La preelaborazione e la postelaborazione sono fasi integrate. La preelaborazione è sempre la prima fase e la Postelaborazione è sempre l’ultima fase. Per impostazione predefinita, è disponibile una fase denominata Predefinito. </p> <p> <b>Per aggiungere una nuova fase di elaborazione</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">Nella finestra <span class="filepath"> Log Processing.cfg </span>, fai clic con il pulsante destro del mouse su <span class="uicontrol"> Stages </span> e fai clic su <span class="uicontrol"> Add New </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">Immettere un nome per il nuovo passaggio. </li> 
      </ul> </p> <p> <b>Per eliminare una fase di elaborazione esistente</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">Fare clic con il pulsante destro del mouse sul numero corrispondente all'area di visualizzazione che si desidera eliminare e fare clic su <span class="uicontrol"> Rimuovi </span><i>&lt; <span class="uicontrol"> #stage_number </span></i>. </li> 
      </ul> </p> <p> <p>Nota:  Quando si specifica un <span class="wintitle"> stage </span> in un <span class="wintitle"> Dataset Include </span> di elaborazione del registro, il nome dell’area di visualizzazione deve corrispondere esattamente al nome immesso qui. Consulta <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Dataset Include Files (File inclusi nel set di dati) </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ora di inizio </td> 
      <td colname="col2"> <p>Facoltativo. Filtrare i dati per includere voci di registro con marche temporali in o dopo questo momento. L'Adobe consiglia di utilizzare per il tempo uno dei seguenti formati: </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 1 gennaio 2013 HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 1 gennaio 2013 OH:MM:SS GMT </li> 
      </ul> </p> <p> Ad esempio, specificando "29 luglio 2013 00:00:00 EDT" come Ora di inizio sono inclusi i dati a partire dal 29 luglio 2013, alle 12:00:00 EDT. Consulta <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtri dati </a>. </p> <p> È necessario specificare un fuso orario. Il fuso orario non viene impostato su GMT se non viene specificato. Per un elenco delle abbreviazioni del fuso orario supportate dal server di Data Workbench, consulta <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codici del fuso orario </a>. </p> <p> <p>Nota:  Il parametro Use Start/End Times per <span class="wintitle"> Sensor </span>, file di registro e origini XML è correlato a questo parametro. Consulta le sezioni di <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Origini di log </a> che illustrano questi tipi di origine. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuso orario </td> 
      <td colname="col2"> <p>Facoltativo. Fuso orario del server di Data Workbench utilizzato per le conversioni temporali (come la conversione rappresentata dal campo x-local-timestring) durante l’elaborazione del registro. </p> <p> <p>Nota:  È necessario specificare il fuso orario se si desidera accedere al campo del tempo convertito durante la fase di elaborazione del registro della costruzione del set di dati. In caso contrario, il server di Data Workbench registra un errore nei registri eventi. </p> </p> <p>Vedere <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fusi orari </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Trasformazioni </td> 
      <td colname="col2"> Facoltativo. L’Adobe consiglia di definire le trasformazioni per l’elaborazione del registro in uno o più <span class="wintitle"> Dataset Include </span> dell’elaborazione del registro. Consulta <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Elaborazione del registro Dataset Include Files (File inclusi nel set di dati) </a>. </td> 
   </tr> 
   </tbody> 
   </table>

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL Log Processing.cfg]nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>* per rendere effettive le modifiche apportate localmente. La rielaborazione dei dati inizia dopo la sincronizzazione del profilo del set di dati.

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.

   Per ulteriori informazioni sulla rielaborazione dei dati, vedere [Rielaborazione e ritrasformazione](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
