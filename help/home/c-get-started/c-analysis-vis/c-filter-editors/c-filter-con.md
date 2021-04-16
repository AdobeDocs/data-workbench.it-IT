---
description: Informazioni sull’utilizzo delle condizioni del filtro, tra cui la creazione di un nuovo filtro e l’aggiunta di una condizione a un nuovo filtro.
title: Utilizzo delle condizioni del filtro
uuid: a75fcb21-be5c-452a-8632-86cd78db15cb
exl-id: 15745b0c-2754-4f8b-acfd-a6bd5886ecf8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 1%

---

# Utilizzo delle condizioni del filtro{#working-with-filter-conditions}

Informazioni sull’utilizzo delle condizioni del filtro, tra cui la creazione di un nuovo filtro e l’aggiunta di una condizione a un nuovo filtro.

## Creazione di un filtro {#section-70ba51ae625e493fa3ca70b93ffba406}

* Apri un editor di filtri nell’area di lavoro facendo clic con il pulsante destro del mouse su **[!UICONTROL Add Visualization]** > **[!UICONTROL Filter Editor]**.

   -oppure-

* Se hai già aperto un editor di filtri e caricato un filtro, fai clic con il pulsante destro del mouse sul nome del filtro corrente e fai clic su **[!UICONTROL New Blank Filter]**.

## Aggiungi una condizione a un nuovo filtro {#section-50986db80f1148c489630a8a63fe9f28}

1. Crea un nuovo filtro. Assicurati che il Filtro progettazione sia evidenziato (anziché Applica filtro), indicando che si sta lavorando in modalità Filtro progettazione.
1. Fai clic con il pulsante destro del mouse nell’area contrassegnata come **[!UICONTROL Right-click to build filter]** e seleziona una delle seguenti opzioni:

   * Per creare un filtro di inclusione, fai clic su **[!UICONTROL Include group with]**.
   * Per creare un filtro di esclusione, fai clic su **[!UICONTROL Exclude group with]**.

1. Seleziona il tipo di condizione da aggiungere al filtro.

   Nella tabella seguente sono riportate le descrizioni dei tipi di condizioni del filtro disponibili:

<table id="table_3B35B57FF32349F09E91E8256FF1672A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di condizione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>selezione area di lavoro </p> </td> 
   <td colname="col2"> <p>Definisce una condizione di filtro in base alle selezioni nell’area di lavoro. Questa opzione è disponibile solo se nell’area di lavoro sono presenti una o più selezioni. </p> <p>Per visualizzare ulteriori informazioni sulla selezione, fare clic con il pulsante destro del mouse sulla condizione e fare clic su <span class="uicontrol"> Visualizza dettagli</span>. Viene visualizzato un callout per la condizione. </p> <p>Se effettui un’altra selezione nell’area di lavoro, puoi aggiungere la selezione come sottocondizione della prima selezione. Le selezioni sono raggruppate come AND logici. Pertanto, i dati inclusi o esclusi dalla condizione devono soddisfare tutte le selezioni dell’area di lavoro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>almeno uno </p> </td> 
   <td colname="col2">Definisce una condizione di filtro in base all’esistenza di almeno un elemento (qualsiasi) di una dimensione scelta. Per modificare la condizione, fai clic con il pulsante destro del mouse sulla condizione e fai clic su <span class="uicontrol"> Cambia condizione</span> in. Fai clic su una delle dimensioni disponibili. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>formula </p> </td> 
   <td colname="col2"> <p>Definisce una condizione di filtro in base alla formula immessa. È necessario utilizzare la sintassi appropriata per il funzionamento del filtro. </p> <p> <p>Nota: Per informazioni sulla sintassi per la definizione dei filtri, consulta <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Sintassi per le espressioni filtro</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>valore della metrica </p> </td> 
   <td colname="col2"> <p>Definisce una condizione di filtro basata sul valore di una metrica specificato. </p> <p>Per definire la condizione, effettua le seguenti operazioni: 
     <ul id="ul_B69D31258A36460E94535709239CD165"> 
      <li id="li_51317A681E654DD7A9D997DF9F2F22BA">Fai clic con il pulsante destro del mouse su <span class="uicontrol"> [scegli livello]</span> &gt; <span class="uicontrol"> Cambia livello</span> per selezionare il livello e la metrica da un elenco di dimensioni nel set di dati. </li> 
      <li id="li_975E56C335824FDCB988344952DE2E9F">Fai clic con il pulsante destro del mouse su <span class="uicontrol"> [scegli metrica]</span> &gt; <span class="uicontrol"> Cambia metrica</span> per selezionare la metrica da un elenco di metriche nel set di dati. </li> 
      <li id="li_D00B3AF3D8DE472C9D0E9EABBBCAAF61">Fai clic con il pulsante destro del mouse su minore di e fai clic su <span class="uicontrol"> Cambia confronto</span> per selezionare una delle condizioni di confronto disponibili (minore di, più di, esattamente, almeno o al massimo). </li> 
      <li id="li_3334CE0A0950448590E5442AB243F46B">Digita il valore desiderato per la metrica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>first/last </p> </td> 
   <td colname="col2"> <p>Definisce un filtro che consente di includere o escludere un livello con una dimensione specificata. Ad esempio, puoi specificare un primo/ultimo filtro da includere (o escludere): </p> <p>Sessioni la cui ultima visualizzazione di pagina ha una pagina di <span class="filepath"> /hme/rts/Our Rates</span>. </p> <p>Per definire una condizione Primo/Ultimo: 
     <ul id="ul_5AD916DA093844B8AC70127B1EB9BFC8"> 
      <li id="li_AB9FF22ADC8843A79856FED60B9478FA">Scegli <span class="uicontrol"> Include group with</span> o <span class="uicontrol"> Exclude group with</span> &gt; <span class="uicontrol"> first/last</span> come nuova condizione nell’Editor filtri. </li> 
      <li id="li_92F536FCC2A74DDE97F66C6C45ACC3DC">Fai clic con il pulsante destro del mouse su <span class="uicontrol"> [scegli contenitore]</span> &gt; <span class="uicontrol"> Cambia contenitore</span> per selezionare il contenitore. </li> 
      <li id="li_1E5DBE04ABC74D84B7C0EF6886CDB5DC">Fai clic con il pulsante destro del mouse su <span class="uicontrol"> primo</span> o <span class="uicontrol"> ultimo</span> per specificare il livello. </li> 
      <li id="li_8B73EBF5D06E4513B5F0376EB2805D1C">Fai clic con il pulsante destro del mouse per specificare una dimensione, quindi digita un valore nel campo disponibile. </li> 
      <li id="li_A9E02EF6C6004DDF9B00EB853B6E54EE">Fai clic su <span class="uicontrol">Applica</span>. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Il filtro in questo esempio definisce un primo/ultimo filtro per gli utenti la cui ultima visualizzazione di pagina è stata [!DNL /hme/rts/Our Rates]:

![](assets/client-fil2.png)

1. (Facoltativo) Per aggiungere ulteriori condizioni al filtro, fai clic con il pulsante destro del mouse nell’area della finestra in cui stai creando il filtro e seleziona il tipo di filtro (vedi il Passaggio 2) e la regola di condizione (vedi il Passaggio 3).

   >[!NOTE]
   >
   >Condizioni di inclusione multiple sono raggruppate come OR logici. Pertanto, i dati inclusi nel filtro devono soddisfare almeno una delle condizioni di inclusione definite. Anche le condizioni di esclusione multiple sono raggruppate come OR logici. Per essere esclusi, i dati devono soddisfare almeno una delle condizioni di esclusione.

Il filtro in questo esempio definisce un sottoinsieme di dati costituiti da visualizzatori di film (utenti) che hanno valutato molti film ma non hanno dato a nessun film un punteggio alto (4 o 5). Questo filtro (denominato in modo appropriato &quot;Molto difficile da soddisfare&quot;) è costituito da due condizioni:

* **Una condizione di valore della metrica:** la condizione include gli utenti che hanno valutato almeno 500 film.
* **Una condizione di selezione dell’area di lavoro:** la condizione esclude gli utenti che hanno dato a un filmato un punteggio di 4 o 5. Il callout indica che 4 e 5 erano gli elementi selezionati dalla dimensione Punteggio.

![](assets/vis_FilterEditor_ExampleMovies.png)

## Eliminare una condizione di filtro {#section-3092e0d7ac624885b8fe24616279de13}

>[!NOTE]
>
>È possibile eliminare le condizioni solo quando si lavora in modalità Filtro struttura. Se hai applicato un filtro all’area di lavoro, fai clic su Filtro progettazione per tornare alla modalità Filtro progettazione prima di poter eliminare una o più condizioni del filtro.

* Fai clic su **x** a sinistra della condizione per eliminarla.

## Modificare una descrizione della condizione {#section-5015fd2c88ed4b6a95be7f0d53be2db0}

Puoi aggiungere descrizioni a ciascuna delle condizioni aggiunte a un filtro. Potete modificare o rimuovere le descrizioni desiderate.

>[!NOTE]
>
>Le descrizioni delle condizioni vengono visualizzate solo quando si lavora in modalità Filtro struttura.

* Fai clic con il pulsante destro del mouse sulla condizione e fai clic su **[!UICONTROL Edit description]**.

   * Per aggiungere o modificare una descrizione, digita la descrizione nel campo [!DNL Edit condition description] . La descrizione viene visualizzata tra virgolette sopra la condizione nella finestra dell’editor filtri.

      ![](assets/vis_FilterEditor_ConditionDescription.png)

* Per rimuovere una descrizione, fai clic su **[!UICONTROL Remove description]**. La condizione rimane nella finestra dell’editor filtri.
