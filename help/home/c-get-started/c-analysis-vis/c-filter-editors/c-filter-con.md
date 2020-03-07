---
description: Informazioni sull’utilizzo delle condizioni del filtro, ad esempio la creazione di un nuovo filtro e l’aggiunta di una condizione a un nuovo filtro.
solution: Analytics
title: Utilizzo delle condizioni del filtro
topic: Data workbench
uuid: a75fcb21-be5c-452a-8632-86cd78db15cb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Utilizzo delle condizioni del filtro{#working-with-filter-conditions}

Informazioni sull’utilizzo delle condizioni del filtro, ad esempio la creazione di un nuovo filtro e l’aggiunta di una condizione a un nuovo filtro.

## Create a filter {#section-70ba51ae625e493fa3ca70b93ffba406}

* Aprite un editor di filtri nell’area di lavoro facendo clic con il pulsante destro del mouse **[!UICONTROL Add Visualization]** > **[!UICONTROL Filter Editor]**.

   -or-

* Se avete già aperto un editor di filtri e caricato un filtro, fate clic con il pulsante destro del mouse sul nome del filtro corrente e fate clic **[!UICONTROL New Blank Filter]**.

## Aggiunta di una condizione a un nuovo filtro {#section-50986db80f1148c489630a8a63fe9f28}

1. Creare un nuovo filtro. Accertatevi che Filtro progettazione sia evidenziato (invece di Filtro applicazione), a indicare che state lavorando in modalità Filtro progettazione.
1. Fare clic con il pulsante destro del mouse nell&#39;area contrassegnata **[!UICONTROL Right-click to build filter]** e selezionare una delle opzioni seguenti:

   * Per creare un filtro di inclusione, fate clic su **[!UICONTROL Include group with]**.
   * Per creare un filtro di esclusione, fate clic su **[!UICONTROL Exclude group with]**.

1. Selezionare il tipo di condizione da aggiungere al filtro.

   Nella tabella seguente sono illustrate le descrizioni dei tipi di condizioni del filtro disponibili:

<table id="table_3B35B57FF32349F09E91E8256FF1672A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo condizione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>selezione area di lavoro </p> </td> 
   <td colname="col2"> <p>Definisce una condizione di filtro in base alle selezioni effettuate nell’area di lavoro. Questa opzione è disponibile solo se all’interno dell’area di lavoro sono presenti una o più selezioni. </p> <p>Per visualizzare ulteriori informazioni sulla selezione, fare clic con il pulsante destro del mouse sulla condizione e scegliere <span class="uicontrol"> Visualizza dettagli</span>. Viene visualizzato un callout per la condizione. </p> <p>Se effettuate un’altra selezione nell’area di lavoro, potete aggiungere la selezione come condizione secondaria della prima selezione. Le selezioni sono raggruppate come AND logici. Pertanto, i dati inclusi o esclusi dalla condizione devono soddisfare tutte le selezioni dell’area di lavoro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>almeno uno </p> </td> 
   <td colname="col2">Definisce una condizione di filtro in base all’esistenza di almeno un elemento (qualsiasi) di una dimensione scelta. Per modificare la condizione, fare clic con il pulsante destro del mouse sulla condizione e fare clic su <span class="uicontrol"> Cambia</span> condizione in. Fate clic su una delle dimensioni disponibili. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>formula </p> </td> 
   <td colname="col2"> <p>Definisce una condizione di filtro in base alla formula immessa. Per il funzionamento del filtro è necessario utilizzare la sintassi appropriata. </p> <p> <p>Nota: Per informazioni sulla sintassi per la definizione dei filtri, consultate <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Sintassi per le espressioni</a>filtro. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>valore della metrica </p> </td> 
   <td colname="col2"> <p>Definisce una condizione di filtro in base al valore di una metrica specificato. </p> <p>Per definire la condizione, procedere come segue: 
     <ul id="ul_B69D31258A36460E94535709239CD165"> 
      <li id="li_51317A681E654DD7A9D997DF9F2F22BA">Fai clic con il pulsante destro del mouse su <span class="uicontrol"> [scegli livello]</span> &gt; <span class="uicontrol"> Modifica livello</span> per selezionare il livello e la metrica da un elenco di dimensioni nel set di dati. </li> 
      <li id="li_975E56C335824FDCB988344952DE2E9F">Fai clic con il pulsante destro del mouse su <span class="uicontrol"> [scegli metrica]</span> &gt; <span class="uicontrol"> Modifica metrica</span> per selezionare la metrica da un elenco di metriche nel set di dati. </li> 
      <li id="li_D00B3AF3D8DE472C9D0E9EABBBCAAF61">Fare clic con il pulsante destro del mouse su un numero inferiore e scegliere <span class="uicontrol"> Modifica confronto</span> per selezionare una delle condizioni di confronto disponibili (minore di, più di, esattamente, almeno, o al massimo). </li> 
      <li id="li_3334CE0A0950448590E5442AB243F46B">Digita il valore desiderato per la metrica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>first/last </p> </td> 
   <td colname="col2"> <p>Definisce un filtro che consente di includere o escludere un livello con una dimensione specificata. Ad esempio, potete specificare un primo/ultimo filtro da includere (o escludere): </p> <p>Sessioni la cui ultima visualizzazione pagina contiene una pagina con <span class="filepath"> /hme/rts/Nostre tariffe</span>. </p> <p>Per definire una condizione Primo/Ultimo: 
     <ul id="ul_5AD916DA093844B8AC70127B1EB9BFC8"> 
      <li id="li_AB9FF22ADC8843A79856FED60B9478FA">Scegliete <span class="uicontrol"> Includi gruppo con</span> o <span class="uicontrol"> Escludi gruppo con</span> &gt; <span class="uicontrol"> primo/ultimo</span> come nuova condizione nell’Editor filtro. </li> 
      <li id="li_92F536FCC2A74DDE97F66C6C45ACC3DC">Fate clic con il pulsante destro del mouse <span class="uicontrol"> [scegliete un contenitore]</span> &gt; <span class="uicontrol"> Cambia contenitore</span> per selezionare il contenitore. </li> 
      <li id="li_1E5DBE04ABC74D84B7C0EF6886CDB5DC">Fare clic con il pulsante destro del mouse <span class="uicontrol"> prima</span> o <span class="uicontrol"> ultima</span> volta per specificare il livello. </li> 
      <li id="li_8B73EBF5D06E4513B5F0376EB2805D1C">Fare clic con il pulsante destro del mouse per specificare una dimensione, quindi digitare un valore nel campo disponibile. </li> 
      <li id="li_A9E02EF6C6004DDF9B00EB853B6E54EE">Fai clic su <span class="uicontrol">Applica</span>. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Il filtro in questo esempio definisce un primo/ultimo filtro per gli utenti la cui ultima visualizzazione di pagina era [!DNL /hme/rts/Our Rates]:

![](assets/client-fil2.png)

1. (Facoltativo) Per aggiungere ulteriori condizioni al filtro, fate clic con il pulsante destro del mouse nell’area della finestra in cui state creando il filtro e selezionate il tipo di filtro (vedere il Passaggio 2) e la regola della condizione (vedere il Passaggio 3).

   >[!NOTE]
   >
   >Le condizioni di inclusione multiple sono raggruppate come OR logici. Pertanto, i dati inclusi nel filtro devono soddisfare almeno una delle condizioni di inclusione definite. Anche le condizioni di esclusione multiple sono raggruppate come OR logici. Per essere esclusi, i dati devono soddisfare almeno una delle condizioni di esclusione.

Il filtro in questo esempio definisce un sottoinsieme di dati costituiti da visualizzatori per filmati (utenti) che hanno valutato molti filmati ma non hanno assegnato ad alcun filmato un punteggio alto (4 o 5). Questo filtro (denominato in modo appropriato &quot;Molto difficile da soddisfare&quot;) è costituito da due condizioni:

* **Una condizione relativa al valore della metrica:** Questa condizione include gli utenti che hanno valutato almeno 500 filmati.
* **Una condizione di selezione dell’area di lavoro:** Questa condizione esclude gli utenti che hanno assegnato a un singolo filmato un punteggio di 4 o 5. Il callout indica che 4 e 5 erano gli elementi selezionati dalla dimensione Valutazione.

![](assets/vis_FilterEditor_ExampleMovies.png)

## Eliminare una condizione filtro {#section-3092e0d7ac624885b8fe24616279de13}

>[!NOTE]
>
>Potete eliminare le condizioni solo quando lavorate in modalità Filtro struttura. Se avete applicato un filtro all’area di lavoro, dovete fare clic su Filtro struttura per tornare alla modalità Filtro struttura prima di poter eliminare una o più condizioni del filtro.

* Fate clic sulla **x** a sinistra della condizione per eliminarla.

## Modificare una descrizione di una condizione {#section-5015fd2c88ed4b6a95be7f0d53be2db0}

È possibile aggiungere descrizioni a ciascuna delle condizioni aggiunte a un filtro. Potete modificare o rimuovere le descrizioni come desiderate.

>[!NOTE]
>
>Le descrizioni delle condizioni vengono visualizzate solo quando si lavora in modalità Filtro struttura.

* Fare clic con il pulsante destro del mouse sulla condizione e scegliere **[!UICONTROL Edit description]**.

   * Per aggiungere o modificare una descrizione, digitare la descrizione nel [!DNL Edit condition description] campo. La descrizione viene visualizzata tra virgolette sopra la condizione nella finestra dell’editor di filtri.

      ![](assets/vis_FilterEditor_ConditionDescription.png)

* Per rimuovere una descrizione, fate clic su **[!UICONTROL Remove description]**. La condizione rimane nella finestra dell’editor filtri.

