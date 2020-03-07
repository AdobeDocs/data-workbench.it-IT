---
description: Aprite Attribuzione adattamento ottimale dal menu Premium e seguite la procedura seguente per creare un modello di attribuzione adattamento ottimale.
title: Creare un modello di attribuzione di adattamento ottimale
uuid: d1fd0340-1917-41bc-9a08-e78a79d084e7
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Creare un modello di attribuzione di adattamento ottimale{#build-a-best-fit-attribution-model}

Aprite Attribuzione adattamento ottimale dal menu Premium e seguite la procedura seguente per creare un modello di attribuzione adattamento ottimale.

Consultate una panoramica di [Attribuzione](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-algorithmic.md#concept-237feb6e9c4d49efaf75399297dcb9d1)adattamento ottimale.

1. Aprite **Attribuzione** adattamento ottimale.

   Aprite un’area di lavoro e fate clic su **[!UICONTROL Premium]** > **[!UICONTROL Best Fit Attribution]**.

   ![](assets/attrib_windows_launch.png)

   >[!NOTE]
   >
   >Attribuzione adattamento ottimale è una funzione Adobe Analytics Premium che richiede l&#39;attivazione di Premium nel profilo. Richiede l&#39;aggiornamento del certificato e l&#39;aggiunta del profilo Premium al file profile.cfg. Consultate Aggiornamento del server [DWB: Da 6.2 a 6.3](https://docs.adobe.com/content/help/en/data-workbench/using/install/upgrade-dwb/c-6-2-to-6-3-upgrade.html) per DWB 6.3.

1. Impostate la **[!UICONTROL Success]** metrica.

   >[!NOTE]
   >
   >Puoi trascinare una metrica da una **[!UICONTROL Finder]** tabella al riquadro sinistro della visualizzazione Attribuzione, oppure selezionarla dal menu **Input** .

   Fai clic su **[!UICONTROL Inputs]** > **[!UICONTROL Set Success]**. Viene aperto il menu delle metriche. ![](assets/attrib_set_success_metric.png)

   Seleziona una metrica che identifica una conversione riuscita.

1. (facoltativo) Impostate la metrica **Entrate** .

   Imposta una metrica per valutare i ricavi nel processo di conversione.

1. Impostare la metrica **Touch** .

   >[!NOTE]
   >
   >L’impostazione di una metrica touch è necessaria solo se si tenta di generare automaticamente metriche di successo trascinando gli elementi dimensionali sulla visualizzazione.

   Fate clic sul **[!UICONTROL Inputs]** menu e selezionate **Imposta contatto** oppure trascinate una metrica dal Finder. ![](assets/attrib_set_touch.png)

   Questo viene utilizzato per derivare le metriche dei canali quando gli elementi dimensionali vengono utilizzati come input.

1. Impostare una finestra **Success** .

   Fai clic su [!DNL Inputs > Success Window] (Fine). Selezionare un intervallo di date da una tabella, quindi assegnare un nome alla finestra Successo. Fai clic su **[!UICONTROL Workspace Selection]** e le date selezionate verranno assegnate come intervallo di tempo per la metrica Successo.

   ![](assets/attrib_set_success_window.png)

   >[!NOTE]
   >
   >Poiché la finestra Successo è una selezione di workstation, puoi includere qualsiasi dimensione nella finestra Successo.

1. Impostate un **[!UICONTROL Touch Window]**.

   Fai clic su [!DNL Inputs > Touch Window] (Fine). Selezionare un intervallo di date da una tabella, quindi assegnare un nome alla finestra Tocco. Fai clic su **[!UICONTROL Workspace Selection]** e le date selezionate verranno assegnate come intervallo di tempo per la metrica Successo.

   ![](assets/attrib_set_touch_window.png)

   Per impostazione predefinita, la finestra **Touch** è impostata sullo stesso periodo di tempo della **[!UICONTROL Success]** finestra.

1. (Facoltativo) Impostate un filtro formazione.

   Potete anche specificare un filtro **** formazione nell’area di lavoro per filtrare i dati dei visitatori.

   >[!NOTE]
   >
   >Impostando entrambe le finestre Successo e Tocco, potete applicare il filtro Formazione alle selezioni dell’area di lavoro correnti per limitare ulteriormente i dati.

   ![](assets/attrib_filter.png)

   >[!NOTE]
   >
   >Il set di formazione è sempre attinto dai visitatori che soddisfano la finestra Successo. Filtrando utilizzando l&#39;Editor filtro, potete creare un sottoinsieme di visitatori segnalati nella finestra Successo.

1. Specifica le metriche del canale che rappresentano i tocchi.

   Trascina le metriche sulla visualizzazione o sceglietele dal menu [!DNL Inputs] > [!DNL Add Channel] . Se non hai già delle metriche definite per campagne o canali, ma hai dimensioni che rappresentano i canali, la visualizzazione può crearle automaticamente con la specifica di una metrica Touch.

   Ad esempio, con la metrica Touch impostata su [!DNL Hits], e con una [!DNL dimension] chiamata [!DNL Media Type] con elementi come [!DNL Email], [!DNL Press Release], [!DNL Print Ad]e [!DNL Social Media], la visualizzazione genererà metriche Canale del modulo [!DNL Hits where Media Type = Email] quando si trascinano e si rilasciano gli elementi sulla visualizzazione.

1. Premere **Go**.

   Viene eseguito il processo di analisi dei livelli migliori e viene visualizzato un grafico con le attribuzioni per canale in base agli input selezionati.

   >[!NOTE]
   >
   >Fai clic con il pulsante destro del mouse su **Modello completo** per visualizzare le statistiche per il modello di attribuzione.

   ![](assets/attrib_visualization.png)

Al termine, un grafico mostra un modello di attribuzione calcolato per canale e una distribuzione della metrica *Entrate* (se impostata). Il modello può essere salvato internamente o esportato in altri sistemi.

>[!NOTE]
>
>**[!UICONTROL Streaming]**, **[!UICONTROL Online]** e **[!UICONTROL Offline]** le modalità producono effetti diversi durante la creazione di un modello di attribuzione in base alla latenza dei dati valutati. In modalità Streaming viene visualizzato il **[!UICONTROL Model Complete]** messaggio di dettaglio. Nelle modalità Online e Offline **[!UICONTROL Local Model Complete]** verranno visualizzati i dettagli.

## Menu Opzioni {#section-22288867f6c8483a8a38410f4b948346}

Il menu **Opzioni** offre funzioni avanzate per l&#39;impostazione e la visualizzazione dell&#39;analisi Attribuzione adattamento ottimale.

<table id="table_8F6F517B7DBF4259814BEC6D07A72EAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menu Opzioni </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Imposta filtro formazione </span> </td> 
   <td colname="col2"> Il Filtro formazione viene utilizzato con la finestra Successo per filtrare la popolazione durante la creazione del modello di attribuzione. Questo fornisce un sottoinsieme di dati che include solo i visitatori che si desidera analizzare. <p>Nota: Gli utenti esperti possono inoltre sfruttare la flessibilità dei filtri per concentrarsi oltre la linea temporale delle finestre di successo e touch. Ad esempio, oltre a selezionare un intervallo di tempo, puoi selezionare un set di Domini <i>di</i> riferimento per esaminare solo l’attribuzione per gli utenti di tali domini. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Mostra descrizione filtro complessa </span> </td> 
   <td colname="col2"> Visualizza il codice del filtro per il filtro Formazione, la finestra Successo e la finestra Touch. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Salva modello </span> </td> 
   <td colname="col2"> Salva il modello di attribuzione corrente per un utilizzo futuro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Modello di caricamento </span> </td> 
   <td colname="col2"> Apre un modello di attribuzione salvato in precedenza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Visualizzazione presentazione </span> </td> 
   <td colname="col2"> Nasconde la barra dei menu superiore per la presentazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Opzioni &gt; Avanzate</b> include funzioni per impostare la dimensione del set di formazione e specificare l’approccio da adottare in caso di squilibrio di classe. </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Avanzate &gt; Dimensioni set di formazione </span> </td> 
   <td colname="col2"> <p>Imposta la dimensione del set di formazione. </p> <p>Nota:  La dimensione predefinita della formazione è Grande per 250.000 visitatori. </p> 
    <ul id="ul_5F17C60227C34A85A2C476A32F2B5DCD"> 
     <li id="li_A076FC2AD0214ADDBFCFD82AEA5F0880">Tiny = 50.000 </li> 
     <li id="li_17E77E01D5374068BEBC80B3AD4CCD41">Piccolo = 75.000 </li> 
     <li id="li_7F6B4834742A4BFCBC3DB214425B88C3">Normale = 100.000 </li> 
     <li id="li_0BB7F791603745028CFC661EBC94D8B4">Grande = 250,00 </li> 
     <li id="li_34B60233C84F48F1BCB8040C5195411A">Enorme = 500.000 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Avanzate &gt; Bilanciamento classe </b> </td> 
   <td colname="col2"> <p>Identifica e definisce il numero di record di input da generare per un problema di squilibrio di classe in base alle dimensioni del dataset. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Opzioni Reimposta e Rimuovi | Descrizione |
|---|---|
| **[!UICONTROL Reset Model]** | Dal **[!UICONTROL Reset]** menu, selezionate **[!UICONTROL Reset Model]** per cancellare la visualizzazione ma mantenere le metriche di input. |
| **[!UICONTROL Reset All]** | Dal **[!UICONTROL Reset]** menu, selezionate **[!UICONTROL Reset All]** per cancellare la visualizzazione e le metriche di input. |
| **[!UICONTROL Remove]** | Fai clic con il pulsante destro del mouse su un input e seleziona **[!UICONTROL Remove]** per cancellare la metrica dall&#39;input selezionato. |
| **[!UICONTROL Remove All]** | Fai clic con il pulsante destro del mouse su *Canali* e seleziona **[!UICONTROL Remove All]** per cancellare tutte le metriche di input. |

