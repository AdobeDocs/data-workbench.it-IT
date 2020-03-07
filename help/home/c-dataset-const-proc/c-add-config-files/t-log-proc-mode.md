---
description: Il file di configurazione Log Processing Mode.cfg consente di mettere in pausa l'elaborazione dei dati in un dataset, specificare le origini offline o specificare la frequenza con cui il server workbench dati salva i propri file di stato.
solution: Analytics
title: Modalità di elaborazione log.cfg
topic: Data workbench
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modalità di elaborazione log.cfg{#log-processing-mode-cfg}

Il file di configurazione Log Processing Mode.cfg consente di mettere in pausa l&#39;elaborazione dei dati in un dataset, specificare le origini offline o specificare la frequenza con cui il server workbench dati salva i propri file di stato.

Le modifiche apportate al [!DNL Log Processing Mode.cfg] file, inclusa l&#39;aggiunta o la rimozione di origini, non causano la rielaborazione dei dati.

**Per modificare il file Log Processing Mode.cfg per un profilo dataset**

1. Quando lavori nel profilo del set di dati, apri il set di dati [!DNL Profile Manager] e fai clic **[!UICONTROL Dataset]** per visualizzarne il contenuto.

   >[!NOTE]
   >
   >Se il [!DNL Log Processing Mode.cfg] file non si trova nella directory per il profilo desiderato, è necessario copiare il file dalla directory Base sul computer server workbench dati nella directory del profilo.

   Per informazioni sull&#39;apertura e l&#39;utilizzo di [!DNL Profile Manager,] Workbench *dati, vedere la Guida* utente.

1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file di configurazione e quindi scegliere **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene visualizzata la finestra di configurazione.
1. Modificate i parametri nel file di configurazione utilizzando la seguente tabella come guida.

   >[!NOTE]
   >
   >Alcuni parametri del [!DNL Log Processing Mode.cfg] file hanno nomi che includono [!DNL Fast Input] o [!DNL Fast Merge]. [!DNL Fast Input]si riferisce alla fase di elaborazione del log della costruzione dell&#39;insieme di dati ed è responsabile di circa la metà del tempo totale di elaborazione dell&#39;insieme di dati. [!DNL Fast Merge] si riferisce alla fase di trasformazione della costruzione dell&#39;insieme di dati solo se preceduta dall&#39;elaborazione del registro. [!DNL Fast Merge] non si verifica durante la riconversione che risulta dalla modifica di un [!DNL Transformation Dataset Configuration] file. Analogamente [!DNL Fast Input], [!DNL Fast Merge] è responsabile di circa la metà del tempo di elaborazione del dataset.

   <table id="table_1BF356E21C0E4119A277F40CEC5D7A21"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parametro </th> 
      <th colname="col2" class="entry"> Descrizione </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Byte cloud </td> 
      <td colname="col2"> <p>Un parametro di ottimizzazione che influisce sull'efficienza della trasformazione dei dati. Il valore predefinito è 128000000. </p> <p> <p>Nota:  Non devi modificare questo valore senza consultare Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rapporto di ingresso rapido </td> 
      <td colname="col2"> <p>Un parametro di ottimizzazione che specifica il rapporto tra byte di log totali e non letti in cui il sistema passa alla modalità <span class="wintitle"> Fast Input</span> (e successivamente <span class="wintitle"> Fast Merge</span>) anziché elaborare i dati in tempo reale. </p> <p> Il valore predefinito è 200, ovvero il sistema passa alla modalità <span class="wintitle"> Fast Input</span> dalla modalità in tempo reale quando i dati di registro non letti sono a 1/200 del totale dei dati. Un rapporto di decisione più elevato rende il sistema entrare <span class="wintitle"> in modalità Fast Input</span> più facilmente, mentre un rapporto inferiore rende meno probabile entrare in modalità <span class="wintitle"> Fast Input</span> . </p> <p> <p>Nota: Impostando il parametro su 0 si evita che il sistema entri in modalità <span class="wintitle"> Fast Input</span> , anche per l'elaborazione iniziale. Impostando il parametro su 1.1, il sistema può immettere <span class="wintitle"> Fast Input</span> durante l'elaborazione iniziale, ma non per l'elaborazione successiva. Adobe non consiglia di utilizzare valori compresi tra 0 e 1.1. Per ulteriori informazioni sull'impostazione di questo parametro, contattate Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Byte FIFO di input rapido </td> 
      <td colname="col2"> <p>Parametro di ottimizzazione che bilancia l'utilizzo della memoria e le prestazioni del sistema durante l'elaborazione dei dati. Il valore predefinito è 120000000. </p> <p> <p>Nota:  Non devi modificare questo valore senza consultare Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Byte buffer unione veloce </td> 
      <td colname="col2"> <p>Parametro di ottimizzazione che bilancia l'utilizzo della memoria e le prestazioni del sistema durante l'elaborazione dei dati. Il valore predefinito è 128000000. </p> <p> <p>Nota:  Non devi modificare questo valore senza consultare Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Origini offline </td> 
      <td colname="col2"> <p>Maschera dell'origine del registro offline. </p> <p> <b> Per specificare un'origine offline</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> Fai clic con il pulsante destro del mouse su <span class="uicontrol"> Origini</span>offline, quindi fai clic su <span class="uicontrol"> Aggiungi nuovo</span> &gt; <span class="uicontrol"> Origine</span>. </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> Nel parametro per la nuova origine, immettete la maschera della sequenza di registro. Per le sorgenti di registro Sensor con nomi di file nel formato YYYYMMDD-<i>SENSORID</i>.vsl, la maschera è <i>SENSORID.SENSORID</i> con distinzione tra maiuscole e minuscole. Per le origini di registro dei file di registro, la maschera è la stringa estratta dal pattern <span class="wintitle"> di</span>maschera. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Log Files</a>. </li> 
      </ul> </p> <p> L'aggiunta o la rimozione di origini da origini offline non causa la rielaborazione del set di dati. </p> <p> Come misura del tempo vengono mantenute per l'elaborazione delle fonti online del profilo. Quando l'origine offline è nuovamente online, l'elaborazione dei file di registro in entrata per tale origine riprende. </p> <p> Ogni volta che una fonte torna online, devi rimuoverla da Origini offline. In caso contrario, il server workbench dati tratta l'origine come un'origine online e aggiorna il periodo di tempo impostato per l'invio dei dati. Se l'origine torna offline, le misure Come ora si fermano. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> In pausa </td> 
      <td colname="col2"> True o false. Se true, i nuovi dati non vengono elaborati nel dataset. Il valore predefinito è false. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ritardo in tempo reale </td> 
      <td colname="col2"> Il tempo in secondi che il server workbench dati attende tra gli intervalli di elaborazione dei dati nel dataset. Quando questo valore è impostato su zero, il sistema tenta di tenere il passo con i dati in entrata in tempo reale. Il valore predefinito è zero (0), ma potete aumentare questo valore per ridurre il carico della CPU. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Byte FIFO in tempo reale </td> 
      <td colname="col2"> <p>La quantità di memoria in byte utilizzata per memorizzare i dati in attesa di essere elaborati nel dataset. Potrebbe essere necessario modificare questo valore in base al numero di secondi specificato per Ritardo in tempo reale. Il valore predefinito è 16000000. </p> <p> <p>Nota:  Non devi modificare questo valore senza consultare Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Intervallo di salvataggio (sec) </td> 
      <td colname="col2"> <p>Frequenza con cui il server workbench dati salva i propri file di stato. Il valore predefinito è 3600. </p> <p> <p>Nota:  Non devi modificare questo valore senza consultare Adobe. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   Quando si modifica il [!DNL Log Processing Mode.cfg] file all&#39;interno di una finestra del workbench dati, è possibile utilizzare i tasti di scelta rapida per le funzioni di modifica di base, quali Taglia (Ctrl+x ), Copia (Ctrl+c), Incolla (Ctrl+v), Annulla (Ctrl+z ), Ripristina (Ctrl+Maiusc+Z ), Seleziona la sezione (Clic+trascinamento) e seleziona tutto (Ctrl+a ). Inoltre, potete utilizzare i collegamenti per copiare e incollare il testo da un file di configurazione ( [!DNL .cfg]) a un altro.

1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.
1. Fare [!DNL Profile Manager]clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL User] colonna, quindi scegliere **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**.

   >[!NOTE]
   >
   >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe, in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti per tali profili.
