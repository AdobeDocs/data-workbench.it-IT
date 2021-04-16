---
description: È necessario configurare gli Insight Server di destinazione per recuperare i dati dal Repeater in cui sono memorizzati i dati dell’evento originale.
title: Configurazione del servizio di replica
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 1%

---

# Configurazione del servizio di replica{#configuring-the-replication-service}

È necessario configurare gli Insight Server di destinazione per recuperare i dati dal Repeater in cui sono memorizzati i dati dell’evento originale.

Per configurare il recupero dei dati da un [!DNL Repeater] a un target [!DNL Insight Server], è necessario modificare il file [!DNL Replicate.cfg] fornito nella cartella [!DNL Components] del target [!DNL Insight Server(s)] come descritto nella procedura seguente:

**Per configurare il  [!DNL Replication Service] nel computer di destinazione**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.
1. Fai clic con il pulsante destro del mouse sull&#39;icona della destinazione [!DNL Insight Server] da configurare e fai clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. Il file [!DNL Replicate.cfg] si trova all&#39;interno di questa directory.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* per [!DNL Replicate.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella colonna [!DNL Temp] per [!DNL Replicate.cfg].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Viene visualizzata la finestra [!DNL Replicate.cfg].
1. Nella finestra [!DNL Replicate.cfg] fare clic su **[!UICONTROL Replicate.cfg]**, quindi **[!UICONTROL component]** per visualizzarne il contenuto.
1. Modifica i parametri utilizzando l’esempio e la tabella seguenti come guide:

   ![Informazioni sul passaggio](assets/cfg_ReplicateFile.png)

   <table id="table_F32D4BFA2D834BBB81DF8F84417CA969"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Per questo parametro.. </th> 
      <th colname="col2" class="entry"> Specifica... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Directory </td> 
      <td colname="col2"> <p>Le directory del <span class="wintitle"> Repeater</span> che devono essere copiate (replicate) nella destinazione <span class="keyword"> Insight Server</span>. Il <span class="wintitle"> servizio di replica</span> consente la replica di più directory da un singolo <span class="wintitle"> Repeater</span>. </p> <p>Per aggiungere una nuova directory, fai clic con il pulsante destro del mouse su <span class="uicontrol"> Directory</span> e fai clic su <span class="uicontrol"> Aggiungi nuovo</span> &gt; <span class="uicontrol"> Directory</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Percorsi appiattiti </td> 
      <td colname="col2"> <p>True o false. L'azione definita dall'impostazione di questo parametro dipende dall'impostazione del parametro Ricorsivo in questo file: 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Se l’opzione Ricorsivo è false, i Percorsi appiattiti non hanno alcun effetto. Vengono replicati solo i file al livello superiore della directory specificata dal parametro URI remoto. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Se Recursive è true e Flatten Paths è false, la struttura di directory della directory remota (<span class="wintitle"> Repeater</span>) viene duplicata esattamente nel percorso locale sulla destinazione <span class="keyword"> Insight Server</span>. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Se sono true sia i Percorsi ricorsivi che i Percorsi appiattiti, nel percorso locale non vengono create sottodirectory. Tutti i file della struttura di directory remota vengono invece inseriti nel livello superiore della directory locale. </li>
      </ul></p> <p> <p>Nota: Se sono true sia i percorsi appiattiti che i percorsi ricorsivi e i file nelle varie sottodirectory del computer remoto condividono gli stessi nomi, il <span class="wintitle"> Servizio di replica</span> potrebbe arrestarsi o potrebbe verificarsi un altro comportamento non definito. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Percorso locale </td> 
      <td colname="col2">Percorso di archiviazione per i file recuperati da <span class="wintitle"> Repeater</span>. Il percorso è relativo alla directory di installazione di <span class="keyword"> Insight Server</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ricorsivo </td> 
      <td colname="col2"> True o false. Se false, vengono replicati solo i file al livello superiore della directory specificata dal parametro URI remoto. Vedi Percorsi appiattiti in questa tabella. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> URI remoto </td> 
      <td colname="col2">L’URI, compresa una maschera di file, per accedere all’archivio file <span class="wintitle"> del Repeater</span>. Il file <span class="filepath"> Communications.cfg</span> sul <span class="wintitle"> Repeater</span> deve essere configurato in modo da consentire l'accesso ai dati dell'evento utilizzando questo URI. Vedere <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Monitoraggio dello spazio dei dati evento</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Server </td> 
      <td colname="col2">Parametri per il <span class="wintitle"> Repeater</span> da cui la destinazione <span class="keyword"> Insight Server</span> recupera i file di dati dell'evento. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nome </td> 
      <td colname="col2">Facoltativo. Nome da identificare il <span class="wintitle"> Repeater</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nome comune server SSL </td> 
      <td colname="col2">Obbligatorio solo se Usa SSL è impostato su true. Nome comune del <span class="wintitle"> Repeater</span> sul quale vengono memorizzati i dati dell'evento. Questo nome deve corrispondere al nome comune indicato nel certificato di comunicazione per il computer. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Indirizzo </td> 
      <td colname="col2">Nome host o indirizzo IP numerico del <span class="wintitle"> Repeater</span> su cui vengono archiviati i dati dell'evento. Il nome comune del server non è una voce valida. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Porta </td> 
      <td colname="col2"> Porta utilizzata per la trasmissione dei dati. La porta predefinita è 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Certificato client SSL </td> 
      <td colname="col2">Obbligatorio solo se Usa SSL è impostato su true. Nome del certificato di licenza utilizzato per connettersi al <span class="wintitle"> Repeater</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Usa SSL </td> 
      <td colname="col2"> <p>Determina se SSL viene utilizzato per la trasmissione dei dati. Le opzioni sono true o false e il valore predefinito è false. </p> <p> <p>Nota: L’utilizzo di SSL non è consigliato perché può influire negativamente sulle prestazioni. Si noti che SSL non è richiesto a meno che la rete che collega il <span class="wintitle"> Repeater</span> ai computer di destinazione non sia sicura. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ora di fine, Ora di inizio </td> 
      <td colname="col2"> <p>(Facoltativo) Limita il set di file di dati evento copiati nella destinazione <span class="keyword"> Insight Server</span> a quelli che contengono dati nell'intervallo definito in Ora di inizio e Ora di fine. Se è impostata l'ora di inizio, i file di dati dell'evento in cui tutte le voci del registro sono precedenti all'ora di inizio specificata non vengono copiati. Se è impostata l'ora di fine, i file di dati dell'evento in cui tutte le voci del registro dall'ora specificata o successiva non vengono copiati. Se solo una parte dei dati in un file si trova nell'intervallo specificato, l'intero file viene copiato nel computer di destinazione. </p> <p>L'Adobe consiglia di utilizzare per il tempo uno dei seguenti formati: 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1 gennaio 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1 gennaio 2013 OH:MM:SS GMT </li>
      </ul></p> <p> <p>Nota: È necessario specificare un fuso orario. Se non specificato, il fuso orario non viene impostato automaticamente sull'ora del sistema. Se si desidera implementare un criterio di ora legale o un criterio di spostamento dell'orologio simile, è necessario salvare il file <span class="filepath"> .dst</span> contenente le regole appropriate nel computer Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span>. Per un elenco delle abbreviazioni di fuso orario supportate e delle informazioni sull'implementazione dell'ora legale, vedere <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Codici del fuso orario</a>. </p> </p> <p> <p>Nota:  Per utilizzare queste impostazioni, i nomi dei file di dati dell'evento devono iniziare con una data ISO (AAAAMMGG) e ogni file deve contenere dati per il periodo di 24 ore a partire dalle ore 12 GMT di quella data. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

Questo esempio illustra come vengono copiati i file se i parametri Flatten Paths e Recursive sono impostati su true.

Supponiamo che l&#39;URI remoto sia [!DNL /RemoteRoot/] e che il percorso locale sia [!DNL E:\LocalRoot\]. Sul computer remoto ( [!DNL Repeater]), i file sono organizzati come segue:

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

Al termine della replica, la directory locale contiene i file seguenti:

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

Nella directory locale non viene creata alcuna sottodirectory e tutti i file della struttura della directory remota vengono inseriti nel livello superiore della directory locale.

>[!NOTE]
>
>Se i file nelle varie sottodirectory del computer remoto condividono gli stessi nomi, il [!DNL Replication Service] potrebbe arrestarsi o potrebbe verificarsi un altro comportamento non definito.
