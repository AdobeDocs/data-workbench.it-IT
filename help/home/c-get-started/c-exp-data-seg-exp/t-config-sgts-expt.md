---
description: Puoi creare un segmento degli elementi di qualsiasi dimensione numerabile, quindi generare i dati per quel segmento in batch o in tempo reale continuo in un file delimitato da tabulazioni.
title: Configurare i segmenti per l’esportazione
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
exl-id: 4f53e02c-3f00-44b3-9f6d-a2f23903b3fa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 1%

---

# Configurare i segmenti per l’esportazione{#configure-segments-for-export}

Puoi creare un segmento degli elementi di qualsiasi dimensione numerabile, quindi generare i dati per quel segmento in batch o in tempo reale continuo in un file delimitato da tabulazioni.

Ogni volta che si esporta un segmento, si producono dati di metrica o dimensione per tutti gli elementi dimensionali inclusi in quel segmento. È possibile controllare la formattazione dei dati di output in modo che altri sistemi possano caricare facilmente i dati.

>[!NOTE]
>
>Non è possibile esportare le dimensioni dei rapporti perché utilizzano un file [!DNL report time.metric] come riferimento. Come soluzione alternativa, se inserisci un [!DNL report time.metric] hardcoded nel profilo, l’esportazione del segmento può utilizzarlo come punto di riferimento per le dimensioni di reporting. Tuttavia, il file [!DNL report time.metric] non viene aggiornato automaticamente in base al valore di Data e ora del profilo; pertanto, quando desideri modificare il riferimento alla dimensione di reporting, devi modificare il file [!DNL report time.metric] codificato.

Per configurare un segmento per l’esportazione, è necessario aprire e modificare un file [!DNL .export].

1. In [!DNL Profile Manager], fai clic sulla directory **[!UICONTROL Export]** nella colonna [!DNL File] per visualizzarne il contenuto.

       Se la directory Export non esiste, creala come segue:
   
   1. Passa alla directory di installazione Data Workbench.
   1. Apri la directory del profilo in cui stai lavorando.
   1. Nella directory Profilo, crea una nuova directory denominata &quot;Export&quot;.

1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sulla cella vuota nella colonna [!DNL User] della directory Export , quindi fai clic su **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   Un file denominato [!DNL New Segment Export.export] viene visualizzato nella colonna [!DNL File] per l&#39;esportazione.

1. Rinomina il nuovo file facendo clic con il pulsante destro del mouse nella colonna [!DNL User] relativa al file e digitando il nuovo nome nel parametro File .
1. Apri il nuovo file facendo clic con il pulsante destro del mouse nella colonna [!DNL User] relativa al file e facendo clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   Viene visualizzata la finestra di configurazione del file [!DNL .export].

1. Fai clic su **[!UICONTROL Query]**, quindi modifica i campi del file [!DNL .export] come descritto nella tabella seguente:

<table id="table_C2EC8FCD3FA04DE78D2CADFA3F7FD8E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questo parametro.. </th> 
   <th colname="col2" class="entry"> Fornisci queste informazioni.. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Comando </td> 
   <td colname="col2"> <p>Facoltativo. Programma da eseguire dopo la creazione del file di output. Questo campo deve fare riferimento a un file eseguibile (un file <span class="filepath"> .exe </span>), non a un comando shell. </p> <p>Nota:  L’esportazione del segmento avrà esito negativo se nel parametro di comando è presente uno spazio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro </td> 
   <td colname="col2"> <p>Facoltativo. Un filtro o un'espressione di filtro. È possibile creare un filtro denominato utilizzando un editor di filtri, quindi digitare il nome del filtro in questo punto oppure digitare un'espressione di filtro. </p> <p>Per ulteriori informazioni sugli editor di filtri, consulta <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> Editor filtri </a>. Per ulteriori informazioni sulla sintassi delle espressioni filtro, consulta <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Sintassi delle espressioni filtro </a>. </p> <p>Vengono esportati gli elementi di Livello che corrispondono al filtro, mentre non tutti gli altri elementi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Livello </td> 
   <td colname="col2"> <p>La dimensione numerabile di cui devono essere esportati gli elementi. </p> <p>Esempio: Un livello di Visitatore esporta una riga di dati per ogni visitatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> File di output </td> 
   <td colname="col2"> <p>Percorso e nome file dei dati esportati. Se il profilo è in esecuzione su un cluster di server Data Workbench, ogni server Data Workbench scrive un file di output contenente una parte dei dati. </p> <p>La directory di installazione del server Data Workbench contiene una directory Exports in cui è possibile salvare il file di output. Ad esempio, puoi immettere <span class="filepath"> Esportazioni\Segmento visitatore.txt </span>, dove <span class="filepath"> Segmento visitatore.txt </span> è il nome del file contenente i dati esportati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Formato di uscita </td> 
   <td colname="col2"> I dati della metrica o della dimensione da esportare per ciascun elemento di livello. Se l’output è un file delimitato da tabulazioni, i campi devono essere separati da caratteri di tabulazione e il formato deve terminare con i caratteri di nuova riga appropriati. Per ulteriori informazioni, vedere <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> Informazioni sul formato di output </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ora di fine pianificazione </td> 
   <td colname="col2"> <p>Facoltativo. Data e ora di fine della pianificazione, incluso il fuso orario. </p> <p>Formato: AAAA-MM-GG hh:mm fuso orario </p> <p>Esempio: 2013-08-01 12:01 EDT </p> <p>Al momento le esportazioni programmate si fermano; tuttavia, il file di output viene rigenerato ogni volta che la sua definizione viene modificata. Questo campo è privo di significato senza definire Pianificazione ogni. Per ulteriori informazioni sulle impostazioni del fuso orario, consulta la <i>Guida alla configurazione del set di dati</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pianifica ogni </td> 
   <td colname="col2"> Facoltativo. Frequenza con cui generare il file di output. I valori supportati sono ora, giorno, settimana e mese. Il file di output viene rigenerato ogni volta che la sua definizione viene modificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ora di inizio pianificazione </td> 
   <td colname="col2"> <p>Facoltativo. Data e ora di inizio della pianificazione, incluso il fuso orario. </p> <p>Formato: AAAA-MM-GG hh:mm fuso orario </p> <p>Esempio: 2013-08-01 12:01 EDT </p> <p>Le esportazioni programmate iniziano in questo momento e la pianificazione è relativa a questo momento. Questo campo è privo di significato senza definire <span class="wintitle"> Pianifica ogni </span>. Per ulteriori informazioni sulle impostazioni del fuso orario, consulta la <i>Guida alla configurazione del set di dati</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite di tempo (sec) </td> 
   <td colname="col2"> Facoltativo. Il tempo massimo consentito durante la generazione di un’esportazione di segmenti. Se viene superato l'intervallo specificato, l'esportazione inizia di nuovo. Impostando questo valore su 0 (zero), il limite viene rimosso. Il valore predefinito è 600 secondi. </td> 
  </tr> 
 </tbody> 
</table>

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (New)]** nella parte superiore della finestra, quindi fai clic su **[!UICONTROL Save]**.
1. Per rendere questo file disponibile a tutti gli utenti del profilo di lavoro, fai clic con il pulsante destro del mouse sul segno di spunta per il file [!DNL .export] creato nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Il salvataggio del file [!DNL .export] nel server Data Workbench comporta l&#39;esecuzione immediata dell&#39;esportazione, anche se l&#39;ora di inizio pianificazione è impostata su una data e un&#39;ora future.

   Di seguito è riportato un file di esempio [!DNL .export] .

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >Il file [!DNL Visitor Segment.export] mostrato nell’esempio fa riferimento al filtro Segmento visitatore. Modificando la definizione di questo filtro si modifica la definizione dell’esportazione.
