---
description: Il file workbenchTransform.cfg di dati contiene i parametri che definiscono le origini di registro, le trasformazioni dei dati e gli esportatori.
solution: Analytics
title: Il file Transform.cfg
topic: Data workbench
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Il file Transform.cfg{#the-transform-cfg-file}

Il file workbenchTransform.cfg di dati contiene i parametri che definiscono le origini di registro, le trasformazioni dei dati e gli esportatori.

Le trasformazioni definite dall&#39;utente manipolano i dati non elaborati raccolti dai sensori ( [!DNL .vsl] file) o contenuti in file di testo, file XML o database conformi a ODBC e li inviano ai campi esistenti, sovrascrivendo i dati correnti o in campi di nuova definizione.

Per configurare la funzionalità di trasformazione, è possibile modificare il file del workbench dati all&#39;interno della [!DNL Transform.cfg] cartella Dataset per il profilo per il quale si desidera esportare i dati dell&#39;evento. In genere, questo profilo è dedicato alla funzionalità di trasformazione (ovvero, l&#39;elaborazione dati non viene eseguita altro che quanto definito nel [!DNL Transform.cfg] file workbench dati). È importante notare che tutte le istruzioni di elaborazione specificate nei [!DNL Log Processing Dataset Include] file per eventuali profili ereditati vengono applicate in aggiunta a quelle specificate nel file workbench dati [!DNL Transform.cfg] .

Per informazioni sui set di dati che includono file, vedere [Set di dati Includi file](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Se i dati che si desidera esportare vengono elaborati da un cluster di server workbench dati, ogni server di elaborazione (DPU) del cluster elabora i dati, ma solo il primo DPU (server di elaborazione n. 0 nel [!DNL profile.cfg] file) scriverà i dati di output nel proprio file system locale.

**Per modificare il file Transform.cfg del workbench dati**

1. Durante l&#39;utilizzo del profilo per il quale si desidera esportare i dati, aprire il profilo [!DNL Profile Manager] e fare clic **[!UICONTROL Dataset]** per visualizzare il contenuto della directory.
1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al workbench dati [!DNL Transform.cfg], quindi fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene visualizzata la finestra del workbench dati [!DNL Transform.cfg] .
1. Modificate i parametri nel file di configurazione utilizzando la tabella seguente come guida:

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
    <td colname="col2"> <p>Facoltativo. Filtrare i dati per includere voci di registro con marche temporali fino a, ma non incluse, questa volta. Adobe consiglia di utilizzare per il momento uno dei seguenti formati: 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 1 gennaio 2013HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 1 gen 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Ad esempio, se specificate il 29 luglio 2013 00:00:00 EDT come Ora di <span class="wintitle"> fine </span> includete i dati fino al 28 luglio 2013, alle 11:59:59 PM EDT. </p> <p> È necessario specificare un fuso orario. Il fuso orario predefinito non è GMT se non specificato. Per un elenco delle abbreviazioni del fuso orario supportate dal server workbench dati, vedere <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codici del fuso orario </a>. </p> <p> Il parametro Use Start/End Times per Sensor e le origini file di registro è correlato a questo parametro. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Esportatori </td> 
    <td colname="col2"> <p>I sottocampi di un esportatore specificano la modalità di elaborazione e/o formattazione dei dati di output. Potete definire più esportatori per un set di origini di registro. Ogni tipo di esportatore crea output in modo indipendente. </p> <p> Esistono tre tipi di esportatori: 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> Per ulteriori informazioni sui tipi di esportatori, consultate <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> Definizione degli esportatori </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Soglia hash </td> 
    <td colname="col2"> Facoltativo. Fattore di campionamento per il sottocampionamento casuale delle righe. Se è impostato su un numero n, per l’esportazione viene selezionato solo un ID di tracciamento n, riducendo il numero totale di righe esportate di un fattore n. Per esportare tutte le righe, impostate Soglia hash su 1. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Condizione voce di registro </td> 
    <td colname="col2"> Facoltativo. Definisce le regole in base alle quali le voci di registro vengono considerate per l’esportazione. Per ulteriori informazioni sulla condizione di <span class="wintitle"> voce di registro </span>, vedere <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> File di configurazione di elaborazione del registro </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Origini log </td> 
    <td colname="col2"> <p>Le origini dei dati. <span class="wintitle"> Le origini di registro </span> possono essere <span class="filepath"> .vsl </span> file, file di registro o file XML o dati provenienti da database conformi a ODBC. Per informazioni sulle origini <span class="wintitle"> di registro </span>, vedere <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> File di configurazione dell'elaborazione del registro </a>. </p> <p> <span class="wintitle"> Transform </span> prevede che tutti i dati di origine siano in ordine cronologico all'interno di file di input ordinati lessicograficamente. Se questo requisito non è soddisfatto, Poiché i calcoli sono errati, e i dati di input aggiuntivi possono essere elaborati dopo la chiusura dei file di output. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Modalità offline </td> 
    <td colname="col2"> <p>Facoltativo. True o false. Se true, <span class="wintitle"> Transform </span> presuppone che tutti i file di input siano presenti quando inizia l'elaborazione dei dati. Quando tutti i dati di input sono stati letti, <span class="wintitle"> Transform </span> chiude tutti i file di output senza attendere la ricezione di dati aggiuntivi. Il valore predefinito è false. </p> <p> <p>Nota:  Se la modalità <span class="wintitle"> offline </span> è impostata su true, <span class="wintitle"> Transform </span> prevede la presenza di tutti i dati di origine prima dell'avvio dell'elaborazione. Un messaggio di avviso viene generato nel file <span class="filepath"> VisualServer.log </span> se vengono ricevuti dati aggiuntivi dopo la chiusura dei file di output. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Rielabora </td> 
    <td colname="col2"> <p>Facoltativo. È possibile inserire qui qualsiasi carattere o combinazione di caratteri. La modifica di questo parametro e il salvataggio del file nel computer <span class="wintitle"> Transform </span> avvia la rielaborazione dei dati. </p> <p> Per informazioni sulla rielaborazione dei dati, vedere <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Rielaborazione e </a>Trasformazione. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Stadi </td> 
    <td colname="col2"> <p>Facoltativo. I nomi delle fasi di elaborazione che possono essere utilizzate nel <span class="wintitle"> set di dati Elaborazione log includono </span> i file che vengono eseguiti oltre al file workbench di dati <span class="filepath"> Transform.cfg </span> . Le fasi di elaborazione consentono di ordinare le trasformazioni definite in <span class="wintitle"> Log Processing Dataset Include </span> i file. Questo parametro è molto utile se avete definito una o più trasformazioni all'interno di più file <span class="wintitle"> Log Processing Dataset Include e desiderate che </span> le trasformazioni specifiche vengano eseguite in punti specifici durante il processo di esportazione. </p> <p> L'ordine in cui si elencano le fasi qui determina l'ordine in cui le trasformazioni nei file <span class="wintitle"> Log Processing Dataset Include vengono eseguite durante </span> l'esportazione dei dati. <span class="wintitle"> La preelaborazione </span> e il <span class="wintitle"> posttrattamento </span> sono fasi integrate; <span class="wintitle"> La preelaborazione </span> è sempre la prima fase, mentre la <span class="wintitle"> postelaborazione </span> è sempre l'ultima fase. Per impostazione predefinita, è presente uno stage denominato <span class="wintitle"> Default </span>. </p> <p> <b>Per aggiungere una nuova fase di elaborazione</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> Nella finestra workbench dati <span class="filepath"> Transform.cfg </span> , fare clic con il pulsante destro del mouse su <span class="uicontrol"> Stages </span>, quindi scegliere <span class="uicontrol"> Aggiungi nuovo </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Immettete un nome per il nuovo passaggio. </li> 
      </ul> <p> <b>Per eliminare una fase di elaborazione esistente</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Fare clic con il pulsante destro del mouse sul numero corrispondente all'area di visualizzazione da eliminare e scegliere <span class="uicontrol"> Rimuovi </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> <p> <p>Nota:  Quando si specifica uno stage in un file <span class="wintitle"> Log Processing Dataset Include, il nome </span> dell'area di visualizzazione deve corrispondere esattamente al nome immesso qui. Per ulteriori informazioni sui dataset includono i file, vedere <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Dataset Include i file </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Ora di inizio </td> 
    <td colname="col2"> <p>Facoltativo. Filtrare i dati per includere voci di registro con marche temporali all’ora o dopo. Adobe consiglia di utilizzare per il momento uno dei seguenti formati: </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1 gennaio 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 1 gen 2013 HH:MM:SS GMT </li> 
      </ul> <p> Ad esempio, se specificate il 29 luglio 2013 00:00:00 EDT come Ora di inizio, i dati iniziano il 29 luglio 2013, alle 01:00:00 EDT delle ore 12. </p> <p> È necessario specificare un fuso orario. Il fuso orario predefinito non è GMT se non specificato. Per un elenco delle abbreviazioni del fuso orario supportate dal server workbench dati, vedere <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codici del fuso orario </a>. </p> <p> <p>Nota:  Il parametro Use Start/End Times per Sensor e le origini file di registro è correlato a questo parametro. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Trasformazioni </td> 
    <td colname="col2"> <p>Facoltativo. Definisce le trasformazioni da applicare ai dati. Per informazioni sui tipi di trasformazione disponibili, vedere <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Trasformazioni dati </a>. </p> <p> <p>Nota:  I seguenti tipi di trasformazione non funzionano se definiti nel file workbench dati <span class="filepath"> Transform.cfg </span> : </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Sessionizza </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>Se vengono ricevuti dati aggiuntivi dopo la chiusura dei file di output (vedere [!DNL Log Sources] e [!DNL Offline Mode] nella tabella precedente), [!DNL Transform] crea nuovi file di output con i dati aggiuntivi. I nomi dei nuovi file di output vengono generati dal nome del file di output originale con l&#39;aggiunta di un numero di versione pari a zero subito prima dell&#39;estensione. Ad esempio, se il file di output originale è [!DNL 20070701-ABC.vsl], le versioni successive di questo file verranno denominate [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl]e così via. Tenere presente che l&#39;utilizzo dei file con le versioni come input per il server workbench dati potrebbe causare errori di elaborazione.
>
>
>Adobe consiglia di evitare la creazione di file di output con controllo delle versioni verificando che tutti i dati di origine siano in ordine cronologico all&#39;interno di file di input ordinati in modo lessicografico e, se [!DNL Offline Mode] è impostato su true, che tutti i dati di origine siano presenti prima dell&#39;avvio dell&#39;elaborazione. Per ulteriori informazioni, vedere [!DNL Log Sources] e [!DNL Offline Mode] le voci della tabella precedente.

1. Aggiungete le trasformazioni facendo clic con il pulsante destro del mouse **[!UICONTROL Transformations]** e scegliendo **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. Completare i campi di trasformazione.

   Per le descrizioni e gli esempi delle trasformazioni utilizzabili con la funzionalità di trasformazione, consultate Trasformazioni [dati](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) .

1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra, quindi scegliere **[!UICONTROL Save]**.
1. Per rendere attive le modifiche apportate localmente, nella [!DNL Profile Manager]colonna fare clic con il pulsante destro del mouse sul segno di spunta per il workbench dati [!DNL Transform.cfg] nella [!DNL User] colonna, quindi scegliere **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, dove il nome del profilo è il nome del profilo per il quale si esportano i dati. La rielaborazione dei dati inizia dopo la sincronizzazione del profilo.

   >[!NOTE]
   >
   >Per informazioni sulla rielaborazione dei dati per l&#39;esportazione, vedere [Rielaborazione e trasformazione](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
