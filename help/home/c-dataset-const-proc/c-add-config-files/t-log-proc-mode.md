---
description: Il file di configurazione Log Processing Mode.cfg consente di mettere in pausa l’elaborazione dei dati in un set di dati, specificare le origini offline o specificare la frequenza con cui il server di Data Workbench salva i propri file di stato.
title: Elaborazione registro Mode.cfg
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
exl-id: e252b815-e691-490d-9ac9-88bb1fd2c64d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 3%

---

# Elaborazione registro Mode.cfg{#log-processing-mode-cfg}

{{eol}}

Il file di configurazione Log Processing Mode.cfg consente di mettere in pausa l’elaborazione dei dati in un set di dati, specificare le origini offline o specificare la frequenza con cui il server di Data Workbench salva i propri file di stato.

Apportare modifiche al [!DNL Log Processing Mode.cfg] il file , inclusa l’aggiunta o la rimozione di origini, non causa la rielaborazione dei dati.

**Per modificare il file Log Processing Mode.cfg di un profilo di set di dati**

1. Quando lavori nel tuo profilo di set di dati, apri la [!DNL Profile Manager] e fai clic su **[!UICONTROL Dataset]** per visualizzarne il contenuto.

   >[!NOTE]
   >
   >Se la [!DNL Log Processing Mode.cfg] il file non si trova nella directory del profilo desiderato. È necessario copiare il file dalla directory Base sul computer server di Data Workbench nella directory del profilo.

   Per informazioni sull&#39;apertura e l&#39;utilizzo di [!DNL Profile Manager,] vedi *Guida utente di Data Workbench*.

1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file di configurazione e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nel [!DNL User] colonna.
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene visualizzata la finestra di configurazione.
1. Modifica i parametri nel file di configurazione utilizzando la seguente tabella come guida.

   >[!NOTE]
   >
   >Alcuni dei parametri nel [!DNL Log Processing Mode.cfg] file con nomi che includono [!DNL Fast Input] o [!DNL Fast Merge]. [!DNL Fast Input]si riferisce alla fase di elaborazione del registro della costruzione del set di dati ed è responsabile di circa la metà del tempo totale di elaborazione del set di dati. [!DNL Fast Merge] si riferisce alla fase di trasformazione della costruzione del set di dati solo se preceduta dall’elaborazione del registro. [!DNL Fast Merge] non si verifica durante la trasformazione risultante dalla modifica di un [!DNL Transformation Dataset Configuration] file. Simile [!DNL Fast Input], [!DNL Fast Merge] è inoltre responsabile di circa la metà del tempo di elaborazione del set di dati.

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
      <td colname="col2"> <p>Parametro di ottimizzazione che influisce sull'efficienza della trasformazione dei dati. Il valore predefinito è 128000000. </p> <p> <p>Nota: Non modificare questo valore senza consultare un Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rapporto di decisione di ingresso rapido </td> 
      <td colname="col2"> <p>Parametro di ottimizzazione che specifica il rapporto tra byte di log totali e non letti in cui il sistema immette <span class="wintitle"> Ingresso rapido</span> (e successivamente <span class="wintitle"> Unione veloce</span>) invece di elaborare i dati in tempo reale. </p> <p> Il valore predefinito è 200, ovvero il sistema immette <span class="wintitle"> Ingresso rapido</span> dalla modalità in tempo reale quando i dati di registro non letti sono a 1/200 del totale dei dati. Un rapporto decisionale più elevato fa sì che il sistema entri <span class="wintitle"> Ingresso rapido</span> più facilmente, mentre un rapporto più basso rende meno probabile entrare <span class="wintitle"> Ingresso rapido</span> modalità. </p> <p> <p>Nota: L'impostazione del parametro su 0 impedisce l'immissione del sistema <span class="wintitle"> Ingresso rapido</span> del tutto, anche per l'elaborazione iniziale. L'impostazione del parametro su 1.1 consente al sistema di immettere <span class="wintitle"> Ingresso rapido</span> durante l'elaborazione iniziale ma non per l'elaborazione successiva. Adobe sconsiglia di utilizzare valori compresi tra 0 e 1.1. Per ulteriori informazioni sull'impostazione di questo parametro, contattare Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Byte FIFO di input rapido </td> 
      <td colname="col2"> <p>Parametro di ottimizzazione che bilancia l'utilizzo della memoria e le prestazioni del sistema durante l'elaborazione dei dati. Il valore predefinito è 120000000. </p> <p> <p>Nota: Non modificare questo valore senza consultare un Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Byte buffer di unione rapida </td> 
      <td colname="col2"> <p>Parametro di ottimizzazione che bilancia l'utilizzo della memoria e le prestazioni del sistema durante l'elaborazione dei dati. Il valore predefinito è 128000000. </p> <p> <p>Nota: Non modificare questo valore senza consultare un Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Origini offline </td> 
      <td colname="col2"> <p>Maschera dell'origine del registro offline. </p> <p> <b> Per specificare un'origine offline</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> Fai clic con il pulsante destro del mouse <span class="uicontrol"> Origini offline</span>, quindi fai clic su <span class="uicontrol"> Aggiungi nuovo</span> &gt; <span class="uicontrol"> Origine</span>. </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> Nel parametro per la nuova sorgente, immetti la maschera della sequenza di log. Per le fonti di log Sensor con nomi di file del formato YYYYMMDD-<i>SENSORIA</i>.vsl, la maschera è <i>SENSORID.SENSORID</i> fa distinzione tra maiuscole e minuscole. Per le origini dei file di log, la maschera è la stringa estratta dal <span class="wintitle"> Pattern di maschera</span>. Vedi <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> File di registro</a>. </li> 
      </ul> </p> <p> L'aggiunta o la rimozione di origini offline non causa la rielaborazione del set di dati. </p> <p> Come delle misurazioni del tempo sono mantenuti per l'elaborazione delle fonti online del profilo. Quando l'origine offline è nuovamente online, riprende l'elaborazione dei file di registro in ingresso per quella sorgente. </p> <p> Ogni volta che un'origine torna online, devi rimuoverla da Sorgenti offline. In caso contrario, il server di Data Workbench tratta l’origine come un’origine online e la aggiorna a partire dal momento in cui l’origine invia i dati. Se l'origine torna offline di nuovo, le misurazioni dell'ora A si arrestano. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> In pausa </td> 
      <td colname="col2"> True o false. Se true, i nuovi dati non vengono elaborati nel set di dati. Il valore predefinito è false. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ritardo in tempo reale </td> 
      <td colname="col2"> Il tempo in secondi che il server di Data Workbench attende tra gli intervalli di elaborazione dei dati nel set di dati. Quando questo valore è impostato su zero, il sistema tenta di tenere il passo con i dati in arrivo in tempo reale. Il valore predefinito è zero (0), ma puoi aumentare questo valore per ridurre il carico della CPU. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Byte FIFO in tempo reale </td> 
      <td colname="col2"> <p>La quantità di memoria in byte utilizzata per memorizzare i dati in attesa di essere elaborati nel set di dati. Potrebbe essere necessario modificare questo valore in base al numero di secondi specificati per Ritardo in tempo reale. Il valore predefinito è 16000000. </p> <p> <p>Nota: Non modificare questo valore senza consultare un Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Intervallo di salvataggio (sec) </td> 
      <td colname="col2"> <p>Frequenza con cui il server di Data Workbench salva i propri file di stato. Il valore predefinito è 3600. </p> <p> <p>Nota: Non modificare questo valore senza consultare un Adobe. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   Durante la modifica del [!DNL Log Processing Mode.cfg] all’interno di una finestra di Data Workbench, puoi utilizzare i tasti di scelta rapida per le funzioni di modifica di base, tra cui Taglia (Ctrl+x ), Copia (Ctrl+c) , Incolla (Ctrl+v ), Annulla (Ctrl+z ), Ripristina (Ctrl+Maiusc+Z ), seleziona una sezione (clic+trascina) e seleziona tutto (Ctrl+a ). Inoltre, è possibile utilizzare le scelte rapide per copiare e incollare il testo da un file di configurazione ( [!DNL .cfg]) a un altro.

1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL User] , quindi fai clic su **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**.

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.
