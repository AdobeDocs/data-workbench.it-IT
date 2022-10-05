---
description: Il file data workbenchTransform.cfg contiene i parametri che definiscono le origini di registro, le trasformazioni dei dati e gli esportatori.
title: Il file Transform.cfg
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
exl-id: e84f2536-cb22-4c47-a7a8-270b3c37ece6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 2%

---

# Il file Transform.cfg{#the-transform-cfg-file}

{{eol}}

Il file data workbenchTransform.cfg contiene i parametri che definiscono le origini di registro, le trasformazioni dei dati e gli esportatori.

Le trasformazioni definite manipolano i dati non elaborati raccolti da Sensor ( [!DNL .vsl] file) o contenuti in file di testo, file XML o database conformi a ODBC e inviarli in campi esistenti, sovrascrivendo i dati correnti o in campi definiti di recente.

Per configurare la funzionalità di trasformazione, è necessario modificare Data Workbench [!DNL Transform.cfg] all’interno della cartella Dataset per il profilo per il quale desideri esportare i dati dell’evento. In genere, questo profilo è dedicato alla funzionalità di trasformazione (ovvero, l’elaborazione dei dati non viene eseguita se non in base a quanto definito all’interno di Data Workbench) [!DNL Transform.cfg] file). È importante notare che tutte le istruzioni di elaborazione specificate nella [!DNL Log Processing Dataset Include] i file per eventuali profili ereditati vengono applicati in aggiunta a quelli specificati in Data Workbench [!DNL Transform.cfg] file.

Per informazioni sui file di inclusione dei set di dati, vedi [Dataset Include Files (File inclusi nel set di dati)](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Se i dati da esportare vengono elaborati da un cluster di server di Data Workbench, ciascuno dei server di elaborazione (DPU) del cluster elabora i dati, ma solo la prima DPU (server di elaborazione n. 0 nel [!DNL profile.cfg] file) scriverà i dati di output nel file system locale.

**Per modificare il file Transform.cfg di Data Workbench**

1. Quando lavori nel profilo per il quale desideri esportare i dati, apri la [!DNL Profile Manager] e fai clic su **[!UICONTROL Dataset]** per visualizzare il contenuto della directory.
1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a Data Workbench [!DNL Transform.cfg], quindi fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nel [!DNL User] colonna.
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Data Workbench [!DNL Transform.cfg] viene visualizzata la finestra .
1. Modifica i parametri nel file di configurazione utilizzando la tabella seguente come guida:

<table id="table_91D9C4C1BE2E43158D9D06C6284EE3C7"> 
  <thead> 
    <tr> 
    <th colname="col1" class="entry"> Parametro </th> 
    <th colname="col2" class="entry"> Descrizione </th> 
    </tr> 
  </thead>
  <tbody> 
    <tr> 
    <td colname="col1"> Ora di fine </td> 
    <td colname="col2"> <p>Facoltativo. Filtra i dati per includere voci di registro con marche temporali fino a questa volta, ma non incluse. L'Adobe consiglia di utilizzare per il tempo uno dei seguenti formati: 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 1 gennaio 2013:MM:EDT SS </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 1 gennaio 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Ad esempio, specificando 29 luglio 2013 00:00:00 EDT come <span class="wintitle"> Ora di fine </span> include i dati fino al 28 luglio 2013, alle ore 11:59:59 </p> <p> È necessario specificare un fuso orario. Il fuso orario non viene impostato su GMT se non viene specificato. Per un elenco delle abbreviazioni del fuso orario supportate dal server di Data Workbench, vedi <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codici del fuso orario </a>. </p> <p> Il parametro Use Start/End Times per le origini di file Sensor e log è correlato a questo parametro. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Esportatori </td> 
    <td colname="col2"> <p>I sottocampi di un esportatore specificano come vengono elaborati e/o formattati i dati di output. Puoi definire più esportatori per un set di origini di registro. Ogni tipo di esportatore crea la produzione in modo indipendente. </p> <p> Esistono tre tipi di esportatori: 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> Per ulteriori informazioni sui tipi di esportazione, vedi <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> Definizione degli esportatori </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Soglia hash </td> 
    <td colname="col2"> Facoltativo. Un fattore di campionamento per il sottocampionamento casuale delle righe. Se impostato su un numero n, per l’esportazione viene selezionato solo un ID di tracciamento su ogni n, riducendo il numero totale di righe esportate di un fattore n. Per esportare tutte le righe, imposta Hash Threshold su 1. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Condizione voce di registro (Log Entry Condition) </td> 
    <td colname="col2"> Facoltativo. Definisce le regole in base alle quali le voci di registro vengono considerate per l'esportazione. Per ulteriori informazioni sulla <span class="wintitle"> Condizione voce di registro </span>, vedi <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> File di configurazione dell’elaborazione del registro </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Origini del registro </td> 
    <td colname="col2"> <p>Le fonti di dati. <span class="wintitle"> Origini del registro </span> può <span class="filepath"> .vsl </span> file, file di registro o file XML o dati provenienti da database conformi a ODBC. Per informazioni su <span class="wintitle"> origini di log </span>, vedi <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> File di configurazione dell’elaborazione del registro </a>. </p> <p> <span class="wintitle"> Trasforma </span> si aspetta che tutti i dati di origine siano in ordine cronologico all’interno dei file di input ordinati in modo lessicografico. Se questo requisito non è soddisfatto, Come i calcoli sono errati e i dati di input aggiuntivi possono essere elaborati dopo la chiusura dei file di output. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Modalità offline </td> 
    <td colname="col2"> <p>Facoltativo. True o false. Se true, <span class="wintitle"> Trasforma </span> presuppone che tutti i file di input siano presenti quando inizia a elaborare i dati. Quando tutti i dati di input sono stati letti, <span class="wintitle"> Trasforma </span> chiude tutti i file di output senza attendere la ricezione di dati aggiuntivi. Il valore predefinito è false. </p> <p> <p>Nota: Se <span class="wintitle"> Modalità offline </span> è impostato su true, <span class="wintitle"> Trasforma </span> prevede che tutti i dati di origine siano presenti prima dell’avvio dell’elaborazione. Viene generato un messaggio di avviso nella variabile <span class="filepath"> VisualServer.log </span> se vengono ricevuti dati aggiuntivi dopo la chiusura dei file di output. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Rielaborazione </td> 
    <td colname="col2"> <p>Facoltativo. È possibile inserire qui qualsiasi carattere o combinazione di caratteri. Modifica di questo parametro e salvataggio del file nel <span class="wintitle"> Trasforma </span> viene avviata la rielaborazione dei dati. </p> <p> Per informazioni sulla rielaborazione dei dati, consulta <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Rielaborazione e ritrasformazione </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Fasi </td> 
    <td colname="col2"> <p>Facoltativo. Nomi delle fasi di elaborazione che possono essere utilizzate in <span class="wintitle"> Include set di dati di elaborazione del registro </span> file eseguiti in aggiunta a Data Workbench <span class="filepath"> Transform.cfg </span> file. Le fasi di elaborazione forniscono un modo per ordinare le trasformazioni definite in <span class="wintitle"> Include set di dati di elaborazione del registro </span> file. Questo parametro è molto utile se hai definito una o più trasformazioni all’interno di più <span class="wintitle"> Include set di dati di elaborazione del registro </span> file e desideri che trasformazioni specifiche vengano eseguite in punti specifici durante il processo di esportazione. </p> <p> L'ordine in cui si elencano gli stadi determina l'ordine in cui le trasformazioni nel <span class="wintitle"> Include set di dati di elaborazione del registro </span> i file vengono eseguiti durante l’esportazione dei dati. <span class="wintitle"> Pre-elaborazione </span> e <span class="wintitle"> Postelaborazione </span> sono fasi integrate; <span class="wintitle"> Pre-elaborazione </span> è sempre la prima fase, e <span class="wintitle"> Postelaborazione </span> è sempre l'ultimo stadio. Per impostazione predefinita, è disponibile una fase denominata <span class="wintitle"> Predefinito </span>. </p> <p> <b>Per aggiungere una nuova fase di elaborazione</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> All’interno di Data Workbench <span class="filepath"> Transform.cfg </span> finestra, clic con il pulsante destro del mouse <span class="uicontrol"> Fasi </span>, quindi fai clic su <span class="uicontrol"> Aggiungi nuovo </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Immettere un nome per il nuovo passaggio. </li> 
      </ul> <p> <b>Per eliminare una fase di elaborazione esistente</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Fai clic con il pulsante destro del mouse sul numero corrispondente all’area di visualizzazione da eliminare e fai clic su <span class="uicontrol"> Rimuovi </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> <p> <p>Nota: Quando si specifica uno stage in un <span class="wintitle"> Include set di dati di elaborazione del registro </span> il nome dell'area di visualizzazione deve corrispondere esattamente al nome immesso. Per ulteriori informazioni sui file di inclusione dei set di dati, vedi <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Dataset Include Files (File inclusi nel set di dati) </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Ora di inizio </td> 
    <td colname="col2"> <p>Facoltativo. Filtrare i dati per includere voci di registro con marche temporali in o dopo questo momento. L'Adobe consiglia di utilizzare per il tempo uno dei seguenti formati: </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1 gennaio 2013 HH:MM:EDT SS </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 1 gennaio 2013 HH:MM:SS GMT </li> 
      </ul> <p> Ad esempio, specificando 29 luglio 2013 00:00:00 EDT come ora di inizio include i dati a partire dal 29 luglio 2013 alle 12:00:00 EDT. </p> <p> È necessario specificare un fuso orario. Il fuso orario non viene impostato su GMT se non viene specificato. Per un elenco delle abbreviazioni del fuso orario supportate dal server di Data Workbench, vedi <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codici del fuso orario </a>. </p> <p> <p>Nota: Il parametro Use Start/End Times per le origini di file Sensor e log è correlato a questo parametro. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Trasformazioni </td> 
    <td colname="col2"> <p>Facoltativo. Definisce le trasformazioni da applicare ai dati. Per informazioni sui tipi di trasformazione disponibili, consulta <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Trasformazioni dei dati </a>. </p> <p> <p>Nota: I seguenti tipi di trasformazione non funzionano quando definiti all’interno di Data Workbench <span class="filepath"> Transform.cfg </span> file: </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Sessionize </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>Se vengono ricevuti dati aggiuntivi dopo la chiusura dei file di output (vedi [!DNL Log Sources] e [!DNL Offline Mode] nella tabella precedente), [!DNL Transform] crea nuovi file di output con i dati aggiuntivi. I nomi dei nuovi file di output vengono generati dal nome del file di output originale con l&#39;aggiunta di un numero di versione con parentesi prima dell&#39;estensione. Ad esempio, se il file di output originale è [!DNL 20070701-ABC.vsl], verranno denominate le versioni successive di questo file [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl]e così via. L’utilizzo dei file con versione come input per il server di Data Workbench può causare errori di elaborazione.
>
>
>Adobe consiglia di evitare la creazione di file di output con versione, verificando che tutti i dati di origine siano in ordine cronologico all’interno di file di input ordinati in modo lessicografico e, se [!DNL Offline Mode] è impostato su true e tutti i dati di origine sono presenti prima dell&#39;avvio dell&#39;elaborazione. Per ulteriori informazioni, consulta la sezione [!DNL Log Sources] e [!DNL Offline Mode] le voci della tabella precedente.

1. Aggiungi le trasformazioni facendo clic con il pulsante destro del mouse **[!UICONTROL Transformations]** e facendo clic su **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. Compila i campi di trasformazione.

   Vedi [Trasformazioni dei dati](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) per descrizioni ed esempi delle trasformazioni utilizzabili con la funzionalità di trasformazione.

1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra, quindi fai clic su **[!UICONTROL Save]**.
1. Per rendere effettive le modifiche apportate localmente, nella [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per Data Workbench [!DNL Transform.cfg] in [!DNL User] , quindi fai clic su **[!UICONTROL Save to]** >  **[!UICONTROL profile name]**, dove nome profilo è il nome del profilo per il quale stai esportando i dati. La rielaborazione dei dati inizia dopo la sincronizzazione del profilo.

   >[!NOTE]
   >
   >Per informazioni sulla rielaborazione dei dati per l’esportazione, consulta [Rielaborazione e ritrasformazione](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
