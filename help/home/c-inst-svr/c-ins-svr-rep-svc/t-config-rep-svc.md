---
description: È necessario configurare i server di destinazione Insight per recuperare i dati dal Ripetitore in cui sono memorizzati i dati dell'evento originale.
solution: Analytics
title: Configurazione del servizio di replica
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 1%

---


# Configurazione del servizio di replica{#configuring-the-replication-service}

È necessario configurare i server di destinazione Insight per recuperare i dati dal Ripetitore in cui sono memorizzati i dati dell&#39;evento originale.

Per configurare il recupero dei dati da una [!DNL Repeater] destinazione [!DNL Insight Server], è necessario modificare il [!DNL Replicate.cfg] file fornito nella [!DNL Components] cartella sulla destinazione [!DNL Insight Server(s)] come descritto nella procedura seguente:

**Per configurare il[!DNL Replication Service]computer di destinazione**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.
1. Fate clic con il pulsante destro del mouse sull’icona della destinazione da [!DNL Insight Server] configurare e fate clic su **[!UICONTROL Server Files]**.
1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL Replicate.cfg] file si trova all&#39;interno di questa directory.
1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server per [!DNL Replicate.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Replicate.cfg].
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Si apre la [!DNL Replicate.cfg] finestra.
1. Nella [!DNL Replicate.cfg] finestra fare clic su **[!UICONTROL Replicate.cfg]**, quindi **[!UICONTROL component]** visualizzarne il contenuto.
1. Modificate i parametri utilizzando l&#39;esempio e la tabella seguenti come guide:

   ![Informazioni sul passaggio](assets/cfg_ReplicateFile.png)

   <table id="table_F32D4BFA2D834BBB81DF8F84417CA969"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Per questo parametro... </th> 
      <th colname="col2" class="entry"> Specifica... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Directory </td> 
      <td colname="col2"> <p>Le directory del <span class="wintitle"> Ripetitore</span> che devono essere copiate (replicate) nel server <span class="keyword"> di</span>Insight di destinazione. Il servizio <span class="wintitle"> di</span> replica consente la replica di più directory da un singolo <span class="wintitle"> Ripetitore</span>. </p> <p>Per aggiungere una nuova directory, fare clic con il pulsante destro del mouse su <span class="uicontrol"> Directory</span> e scegliere <span class="uicontrol"> Aggiungi nuovo</span> &gt; <span class="uicontrol"> Directory</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Appiattisci tracciati </td> 
      <td colname="col2"> <p>True o false. L'azione definita dall'impostazione di questo parametro dipende dall'impostazione del parametro ricorsivo in questo file: 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Se Recursive è false, i Percorsi appiattiti non hanno alcun effetto. Vengono replicati solo i file al livello superiore della directory specificata dal parametro URI remoto. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Se Recursive è true e Flatten Paths è false, la struttura di directory della directory remota (<span class="wintitle"> Ripater</span>) viene duplicata esattamente nel percorso locale sul server <span class="keyword"></span>Insight di destinazione. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Se i Percorsi ricorsivi e Appiattiti sono entrambi veri, nel percorso locale non viene creata alcuna sottodirectory. Tutti i file dalla struttura di directory remota vengono invece inseriti nel livello superiore della directory locale. </li>
      </ul></p> <p> <p>Nota: Se entrambe le proprietà Percorsi appiattiti e Ricorsivi sono vere e i file delle varie sottodirectory del computer remoto condividono gli stessi nomi, il servizio <span class="wintitle"> di</span> replica potrebbe arrestarsi o potrebbe verificarsi un altro comportamento non definito. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Percorso locale </td> 
      <td colname="col2">Percorso di memorizzazione per i file recuperati da <span class="wintitle"> Ripetitore</span>. Il percorso è relativo alla directory di installazione di <span class="keyword"> Insight Server</span> . </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ricorsivo </td> 
      <td colname="col2"> True o false. Se false, vengono replicati solo i file al livello superiore della directory specificata dal parametro URI remoto. Consultate Appiattisci percorsi in questa tabella. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> URI remoto </td> 
      <td colname="col2">L’URI, inclusa una maschera di file, per accedere all’archivio file del <span class="wintitle"> Ripetitore</span> . Il file <span class="filepath"> Communications.cfg</span> nel <span class="wintitle"> Ripetitore</span> deve essere configurato in modo che sia possibile accedere ai dati dell'evento utilizzando questo URI. See <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Monitoring Event Data Space</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Server </td> 
      <td colname="col2">Parametri per il <span class="wintitle"> Ripetitore</span> da cui il server <span class="keyword"> di</span> Insight di destinazione recupera i file di dati dell'evento. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nome </td> 
      <td colname="col2">Facoltativo. Nome per identificare il <span class="wintitle"> ripetitore</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nome comune server SSL </td> 
      <td colname="col2">Obbligatorio solo se Usa SSL è impostato su true. Nome comune del <span class="wintitle"> Ripetitore</span> in cui sono memorizzati i dati dell'evento. Questo nome deve corrispondere al nome comune elencato nel certificato di comunicazione per il computer. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Indirizzo </td> 
      <td colname="col2">Nome host o indirizzo IP numerico del <span class="wintitle"> Ripetitore</span> in cui sono memorizzati i dati dell'evento. Il nome comune del server non è una voce valida. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Porta </td> 
      <td colname="col2"> Porta utilizzata per la trasmissione dei dati. La porta predefinita è 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Certificato client SSL </td> 
      <td colname="col2">Obbligatorio solo se Usa SSL è impostato su true. Nome del certificato di licenza utilizzato per connettersi al <span class="wintitle"> ripetitore</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Usa SSL </td> 
      <td colname="col2"> <p>Determina se SSL viene utilizzato per la trasmissione dei dati. Le opzioni sono true o false e il valore predefinito è false. </p> <p> <p>Nota: L’utilizzo di SSL non è consigliato perché può influire negativamente sulle prestazioni. SSL non è richiesto a meno che la rete che collega il <span class="wintitle"> Ripetitore</span> ai computer di destinazione non sia sicura. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ora di fine, Ora di inizio </td> 
      <td colname="col2"> <p>(Facoltativo) Limita il set di file di dati dell'evento copiati nel server <span class="keyword"> di</span> Insight di destinazione a quelli che contengono dati nell'intervallo definito da Ora di inizio e Ora di fine. Se è impostata l'ora di inizio, i file dei dati dell'evento in cui tutte le voci di registro provengono da un'ora precedente a quella di inizio specificata non vengono copiati. Se è impostata l'ora di fine, i file dei dati dell'evento in cui non vengono copiate tutte le voci del registro dall'ora specificata o da quella successiva. Se solo una parte dei dati in un file si trova nell'intervallo specificato, l'intero file viene copiato nel computer di destinazione. </p> <p> Adobe consiglia di utilizzare per il momento uno dei seguenti formati: 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1 gennaio 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1 gen 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Nota: È necessario specificare un fuso orario. Se non viene specificato, il fuso orario predefinito non corrisponde all'ora del sistema. Se desiderate implementare un'ora legale o un criterio simile per lo spostamento dell'orologio, dovete salvare il file <span class="filepath"> .dst</span> contenente le regole appropriate nel computer Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span> . Per un elenco delle abbreviazioni supportate per i fusi orari e informazioni sull'implementazione dell'ora legale, consultate <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Codici</a>per i fusi orari. </p> </p> <p> <p>Nota:  Per utilizzare queste impostazioni, i nomi dei file di dati dell'evento devono iniziare con una data ISO (AAAAMMGG) e ogni file deve contenere dati per il periodo di 24 ore a partire dalle 12:00 GMT di quella data. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Salvate le modifiche al server effettuando le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.
   1. Fare [!DNL Server Files Manager]clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL Temp] colonna e selezionare **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

Questo esempio illustra come i file vengono copiati se i parametri Appiattisci tracciati e Ricorsivi sono impostati su true.

Supponiamo che URI remoto sia [!DNL /RemoteRoot/] e Percorso locale sia [!DNL E:\LocalRoot\]. Sul computer remoto ( [!DNL Repeater]), i file sono organizzati come segue:

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

Al termine della replica, la directory locale contiene i file seguenti:

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

Nella directory locale, non vengono create sottodirectory e tutti i file dalla struttura di directory remota vengono inseriti nel livello superiore della directory locale.

>[!NOTE]
>
>Se i file delle varie sottodirectory del computer remoto condividono gli stessi nomi, [!DNL Replication Service] potrebbe verificarsi un arresto o un altro comportamento non definito.
