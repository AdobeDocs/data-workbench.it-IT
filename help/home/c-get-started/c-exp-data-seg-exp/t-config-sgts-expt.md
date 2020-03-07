---
description: Puoi creare un segmento degli elementi di qualsiasi dimensione numerabile, quindi inviare i dati per quel segmento in batch o in tempo reale in un file delimitato da tabulazioni.
solution: Analytics
title: Configurare i segmenti per l’esportazione
topic: Data workbench
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurare i segmenti per l’esportazione{#configure-segments-for-export}

Puoi creare un segmento degli elementi di qualsiasi dimensione numerabile, quindi inviare i dati per quel segmento in batch o in tempo reale in un file delimitato da tabulazioni.

Ogni volta che si esporta un segmento, si ottengono dati di metrica o dimensione per tutti gli elementi di dimensione inclusi in tale segmento. È possibile controllare la formattazione dei dati di output in modo che altri sistemi possano caricare facilmente i dati.

>[!NOTE]
>
>Non potete esportare le dimensioni dei rapporti, perché utilizzano un [!DNL report time.metric] file come riferimento. Come soluzione alternativa, se inserite un codice fisso [!DNL report time.metric] nel profilo, l’esportazione del segmento può utilizzarlo come punto di riferimento per il reporting delle dimensioni. Tuttavia, [!DNL report time.metric] non viene aggiornato automaticamente in base al tempo di disponibilità del profilo; pertanto, se desiderate modificare il riferimento alla dimensione del rapporto, dovete modificare il [!DNL report time.metric] file codificato.

Per configurare un segmento per l’esportazione, è necessario aprire e modificare un [!DNL .export] file.

1. Nella [!DNL Profile Manager], fate clic sulla **[!UICONTROL Export]** directory nella [!DNL File] colonna per visualizzarne il contenuto.

       Se la directory Export non esiste, createla come segue:
   
   1. Accedere alla directory di installazione di Workbench dati.
   1. Aprite la directory del profilo in uso.
   1. All’interno della directory Profile, create una nuova directory denominata &quot;Export&quot;.

1. Nella [!DNL Profile Manager]colonna fare clic con il pulsante destro del mouse sulla cella vuota della [!DNL User] directory Export, quindi scegliere **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   Un file denominato [!DNL New Segment Export.export] viene visualizzato nella [!DNL File] colonna Esporta.

1. Rinominare il nuovo file facendo clic con il pulsante destro del mouse nella [!DNL User] colonna del file e digitando il nuovo nome nel parametro File.
1. Aprite il nuovo file facendo clic con il pulsante destro del mouse nella [!DNL User] colonna del file e scegliendo **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   Viene visualizzata la finestra di configurazione del [!DNL .export] file.

1. Fate clic **[!UICONTROL Query]**, quindi modificate i campi del [!DNL .export] file come descritto nella tabella seguente:

<table id="table_C2EC8FCD3FA04DE78D2CADFA3F7FD8E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questo parametro... </th> 
   <th colname="col2" class="entry"> Fornire queste informazioni... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Comando </td> 
   <td colname="col2"> <p>Facoltativo. Un programma da eseguire dopo la creazione del file di output. Questo campo deve fare riferimento a un file eseguibile (un file <span class="filepath"> .exe </span> ), non a un comando shell. </p> <p>Nota:  L'esportazione del segmento non riuscirà se nel parametro del comando è presente uno spazio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro </td> 
   <td colname="col2"> <p>Facoltativo. Un filtro o un'espressione di filtro con nome. Potete creare un filtro denominato utilizzando un editor di filtri, quindi digitare il nome del filtro oppure digitare l'espressione di filtro. </p> <p>Per ulteriori informazioni sugli editor di filtri, consultate <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> Filtra editor </a>. Per ulteriori informazioni sulla sintassi delle espressioni di filtro, vedere <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Sintassi delle espressioni di filtro </a>. </p> <p>Gli elementi di livello che corrispondono al filtro vengono esportati, mentre tutti gli altri non lo sono. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Livello </td> 
   <td colname="col2"> <p>Dimensione numerabile di cui esportare gli elementi. </p> <p>Esempio: Un livello di Visitatore esporta una riga di dati per ogni visitatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> File di output </td> 
   <td colname="col2"> <p>Percorso e nome file dei dati esportati. Se il profilo è in esecuzione su un cluster di server Workbench dati, ogni server di Workbench dati scrive un file di output contenente una parte dei dati. </p> <p>La directory di installazione del server Workbench dati contiene una directory Exports in cui è possibile salvare il file di output. Ad esempio, puoi immettere <span class="filepath"> Exports\Visitor Segment.txt </span>, dove <span class="filepath"> Visitor Segment.txt </span> è il nome del file contenente i dati esportati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Formato di output </td> 
   <td colname="col2"> I dati della metrica o della dimensione da esportare per ciascun elemento di livello. Se l'output è un file delimitato da tabulazioni, i campi devono essere separati da caratteri di tabulazione e il formato deve terminare con i caratteri di nuova riga appropriati. Per ulteriori informazioni, vedere <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> Informazioni sul formato di output </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Orario fine pianificazione </td> 
   <td colname="col2"> <p>Facoltativo. Data e ora di fine della pianificazione, incluso il fuso orario. </p> <p>Formato: AAAA-MM-GG hh:mm fuso orario </p> <p>Esempio: 2013-08-01 12:01 EDT </p> <p>Al momento le esportazioni programmate si fermano; tuttavia, il file di output viene ancora rigenerato ogni volta che la sua definizione viene modificata. Questo campo è privo di significato senza definire Schedule Every (Pianificazione ogni). Per ulteriori informazioni sulle impostazioni del fuso orario, vedere la Guida alla configurazione del <i>set di dati</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pianifica ogni </td> 
   <td colname="col2"> Facoltativo. Frequenza con cui rigenerare il file di output. I valori supportati sono ora, giorno, settimana e mese. Il file di output viene ancora rigenerato ogni volta che la sua definizione viene modificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Orario inizio pianificazione </td> 
   <td colname="col2"> <p>Facoltativo. Data e ora di inizio della pianificazione, incluso il fuso orario. </p> <p>Formato: AAAA-MM-GG hh:mm fuso orario </p> <p>Esempio: 2013-08-01 12:01 EDT </p> <p>Le esportazioni programmate iniziano in questa fase e la pianificazione è relativa a tale ora. Questo campo è privo di significato senza definire <span class="wintitle"> Schedule Every (Pianificazione ogni) </span>. Per ulteriori informazioni sulle impostazioni del fuso orario, vedere la Guida alla configurazione del <i>set di dati</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite di tempo (sec) </td> 
   <td colname="col2"> Facoltativo. Il tempo massimo consentito per trascorrere durante la generazione dell’esportazione di un segmento. Se viene superato l'intervallo specificato, l'esportazione ripartirà. Impostando questo valore su 0 (zero) il limite viene rimosso. Il valore predefinito è 600 secondi. </td> 
  </tr> 
 </tbody> 
</table>

1. Fare clic con il pulsante destro del mouse **[!UICONTROL (New)]** nella parte superiore della finestra, quindi scegliere **[!UICONTROL Save]**.
1. Per rendere questo file disponibile a tutti gli utenti del profilo di lavoro, fare clic con il pulsante destro del mouse sul [!DNL .export] file creato nella [!DNL User] colonna, quindi fare clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Il salvataggio del [!DNL .export] file nel server Workbench dati determina l&#39;esecuzione immediata dell&#39;esportazione, anche se l&#39;ora di inizio pianificazione è impostata su una data e un&#39;ora future.

   Segue un [!DNL .export] file di esempio.

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >Il [!DNL Visitor Segment.export] file mostrato nell’esempio fa riferimento al filtro Segmento visitatore. Modificando la definizione di questo filtro si modifica la definizione dell’esportazione.

