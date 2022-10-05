---
description: È necessario configurare gli Insight Server di destinazione per recuperare i dati dal Repeater in cui sono memorizzati i dati dell’evento originale.
title: Configurazione del servizio di replica
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 1%

---

# Configurazione del servizio di replica{#configuring-the-replication-service}

{{eol}}

È necessario configurare gli Insight Server di destinazione per recuperare i dati dal Repeater in cui sono memorizzati i dati dell’evento originale.

Per configurare il recupero dei dati da un [!DNL Repeater] a un target [!DNL Insight Server], è necessario modificare il [!DNL Replicate.cfg] file fornito nella [!DNL Components] nella cartella di destinazione [!DNL Insight Server(s)] come descritto nella seguente procedura:

**Per configurare le [!DNL Replication Service] sul computer di destinazione**

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.
1. Fai clic con il pulsante destro del mouse sull’icona del target [!DNL Insight Server] si desidera configurare e fare clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. La [!DNL Replicate.cfg] il file si trova all&#39;interno di questa directory.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nel *nome server* colonna per [!DNL Replicate.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nel [!DNL Temp] colonna per [!DNL Replicate.cfg].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nel [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La [!DNL Replicate.cfg] si apre la finestra.
1. In [!DNL Replicate.cfg] finestra, fai clic su **[!UICONTROL Replicate.cfg]**, quindi **[!UICONTROL component]** per visualizzarne il contenuto.
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
      <td colname="col2"> <p>Le directory <span class="wintitle"> Ripetitore</span> che devono essere copiati (replicati) nella destinazione <span class="keyword"> Insight Server</span>. La <span class="wintitle"> Servizio di replica</span> consente la replica di più directory da un singolo <span class="wintitle"> Ripetitore</span>. </p> <p>Per aggiungere una nuova directory, fai clic con il pulsante destro del mouse su <span class="uicontrol"> Directory</span> e fai clic su <span class="uicontrol"> Aggiungi nuovo</span> &gt; <span class="uicontrol"> Directory</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Percorsi appiattiti </td> 
      <td colname="col2"> <p>True o false. L'azione definita dall'impostazione di questo parametro dipende dall'impostazione del parametro Ricorsivo in questo file: 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Se l’opzione Ricorsivo è false, i Percorsi appiattiti non hanno alcun effetto. Vengono replicati solo i file al livello superiore della directory specificata dal parametro URI remoto. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Se Recursive è true e Flatten Paths è false, la struttura della directory del telecomando (<span class="wintitle"> Ripetitore</span>) viene duplicata esattamente nel percorso locale sulla destinazione <span class="keyword"> Insight Server</span>. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Se sono true sia i Percorsi ricorsivi che i Percorsi appiattiti, nel percorso locale non vengono create sottodirectory. Tutti i file della struttura di directory remota vengono invece inseriti nel livello superiore della directory locale. </li>
      </ul></p> <p> <p>Nota: Se i Percorsi Flatten e i Percorsi Ricorsivi sono entrambi veri e i file nelle varie sottodirectory del computer remoto condividono gli stessi nomi, la <span class="wintitle"> Servizio di replica</span> può interrompere o può verificarsi un altro comportamento indefinito. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Percorso locale </td> 
      <td colname="col2">Percorso di archiviazione per i file recuperati da <span class="wintitle"> Ripetitore</span>. Il percorso è relativo al <span class="keyword"> Insight Server</span> directory di installazione. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ricorsivo </td> 
      <td colname="col2"> True o false. Se false, vengono replicati solo i file al livello superiore della directory specificata dal parametro URI remoto. Vedi Percorsi appiattiti in questa tabella. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> URI remoto </td> 
      <td colname="col2">L’URI, compresa una maschera di file, per accedere al <span class="wintitle"> Ripetitore</span> archivio file. La <span class="filepath"> Communications.cfg</span> sul <span class="wintitle"> Ripetitore</span> deve essere configurato in modo che sia possibile accedere ai dati dell’evento utilizzando questo URI. Vedi <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Monitoraggio dello spazio dei dati degli eventi</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Server </td> 
      <td colname="col2">Parametri per <span class="wintitle"> Ripetitore</span> da cui l'obiettivo <span class="keyword"> Insight Server</span> recupera i file di dati evento. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nome </td> 
      <td colname="col2">Facoltativo. Nome da identificare <span class="wintitle"> Ripetitore</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nome comune server SSL </td> 
      <td colname="col2">Obbligatorio solo se Usa SSL è impostato su true. Nome comune <span class="wintitle"> Ripetitore</span> in cui vengono memorizzati i dati dell’evento. Questo nome deve corrispondere al nome comune indicato nel certificato di comunicazione per il computer. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Indirizzo </td> 
      <td colname="col2">Nome host o indirizzo IP numerico della <span class="wintitle"> Ripetitore</span> in cui vengono memorizzati i dati dell’evento. Il nome comune del server non è una voce valida. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Porta </td> 
      <td colname="col2"> Porta utilizzata per la trasmissione dei dati. La porta predefinita è 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Certificato client SSL </td> 
      <td colname="col2">Obbligatorio solo se Usa SSL è impostato su true. Nome del certificato di licenza utilizzato per connettersi al <span class="wintitle"> Ripetitore</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Usa SSL </td> 
      <td colname="col2"> <p>Determina se SSL viene utilizzato per la trasmissione dei dati. Le opzioni sono true o false e il valore predefinito è false. </p> <p> <p>Nota: L’utilizzo di SSL non è consigliato perché può influire negativamente sulle prestazioni. Si noti che SSL non è richiesto a meno che la rete che collega la <span class="wintitle"> Ripetitore</span> ai computer di destinazione non è sicuro. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ora di fine, Ora di inizio </td> 
      <td colname="col2"> <p>(Facoltativo) Limita il set di file di dati evento copiati nella destinazione <span class="keyword"> Insight Server</span> a quelli che contengono dati nell’intervallo definito da Ora di inizio e Ora di fine. Se è impostata l'ora di inizio, i file di dati dell'evento in cui tutte le voci del registro sono precedenti all'ora di inizio specificata non vengono copiati. Se è impostata l'ora di fine, i file di dati dell'evento in cui tutte le voci del registro dall'ora specificata o successiva non vengono copiati. Se solo una parte dei dati in un file si trova nell'intervallo specificato, l'intero file viene copiato nel computer di destinazione. </p> <p>L'Adobe consiglia di utilizzare per il tempo uno dei seguenti formati: 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1 gennaio 2013 HH:MM:EDT SS </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1 gennaio 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Nota: È necessario specificare un fuso orario. Se non specificato, il fuso orario non viene impostato automaticamente sull'ora del sistema. Se desideri implementare un'ora legale o un criterio simile per lo spostamento dell'orologio, è necessario salvare il <span class="filepath"> .dst</span> file contenente le regole appropriate nella directory Base\Dataset\Timezone <span class="keyword"> Insight Server</span> macchina. Per un elenco delle abbreviazioni dei fusi orari supportati e informazioni sull'implementazione dell'ora legale, vedi <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Codici del fuso orario</a>. </p> </p> <p> <p>Nota: Per utilizzare queste impostazioni, i nomi dei file di dati dell'evento devono iniziare con una data ISO (AAAAMMGG) e ogni file deve contenere dati per il periodo di 24 ore a partire dalle ore 12 GMT di quella data. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

Questo esempio illustra come vengono copiati i file se i parametri Flatten Paths e Recursive sono impostati su true.

Supponiamo che l&#39;URI remoto sia [!DNL /RemoteRoot/] e Percorso locale è [!DNL E:\LocalRoot\]. Sul telecomando ( [!DNL Repeater]), i file sono organizzati come segue:

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
>Se i file nelle varie sottodirectory del computer remoto condividono gli stessi nomi, la [!DNL Replication Service] può interrompere o può verificarsi un altro comportamento indefinito.
