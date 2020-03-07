---
description: Utilizzare i pannelli Finder di Workbench dati per selezionare metriche, dimensioni e filtri. Questi pannelli forniscono supporto per la ricerca, opzioni di ordinamento e funzionalità di trascinamento della selezione.
solution: Analytics
title: Finder
topic: Data workbench
uuid: 7a4144f5-133f-48ed-9613-1e42b1313120
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Finder{#finders}

Utilizzare i pannelli Finder di Workbench dati per selezionare metriche, dimensioni e filtri. Questi pannelli forniscono supporto per la ricerca, opzioni di ordinamento e funzionalità di trascinamento della selezione.

Un pannello del Finder può essere aperto nella barra laterale sinistra o all’interno di un’area di lavoro.

![](assets/query_entity_panel_main.png)

<table id="table_3E43DBA0646842898F14F31374F9E39C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension Finder </th> 
   <th colname="col2" class="entry"> Finder delle metriche </th> 
   <th colname="col3" class="entry"> Finder filtri </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Un elenco di tutte le dimensioni nel modello di query. </p><img placement="break" id="image_D7D317D84C0843BE8D324E5B9F7AF20D" src="assets/query_entity_dim_panel.png" /> </td> 
   <td colname="col2"> <p>Un elenco di tutte le metriche nel modello di query. </p><img placement="break" id="image_04553B2F2C6A48FE897B4EFF002BED59" src="assets/query_entity_metric_panel.png" /> </td> 
   <td colname="col3"> <p>Elenco di tutti i filtri creati per la vostra organizzazione. </p><img placement="break" id="image_920E72D795644634A82D1955CB64B355" src="assets/query_entity_filters_panel.png" /> </td> 
  </tr> 
 </tbody> 
</table>

**Per aprire un Finder:**

* Fate clic con il pulsante destro del mouse in un’area di lavoro e selezionate **[!UICONTROL Tools]** > **[!UICONTROL Finder]**.

   Il riquadro Finder con schede per Metriche, Dimensioni e Filtri si aprirà nell’area di lavoro.

* Fate clic con il pulsante destro del mouse nella barra laterale sinistra e selezionate **[!UICONTROL Add]** > **[!UICONTROL Finder]**.

   Il riquadro Finder si apre nel pannello a sinistra.

Il **Finder** include le seguenti funzionalità:

<table id="table_072047E919204577AE85789BAE0F4EE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funzioni del Finder </th> 
   <th colname="col2" class="entry"> Dettagli </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Inserimento tramite trascinamento</b> </td> 
   <td colname="col2"> <p> Puoi trascinare dimensioni o metriche dal pannello a una visualizzazione nell’area di lavoro per modificare la dimensione o aggiungere nuove metriche. </p> 
    <ol id="ol_612DC76EC04C4FCE938B20B388C43CE8"> 
     <li id="li_7F73B781141E4B8CAE9800F580F62E44">Tenere premuto i tasti <span class="uicontrol"> &lt;Ctrl&gt;</span> e <span class="uicontrol"> &lt;Alt&gt;</span> e selezionare la dimensione o la metrica dal pannello Finder. </li> 
     <li id="li_631D57976F71415AA61F33EBBFDD128A">Trascina una nuova dimensione dal riquadro e rilasciala sulla visualizzazione per modificarla o aggiungerla. </li> 
     <li id="li_5329FB82225F46EBBE3A996A641058DE">Per aggiungere metriche, trascina una nuova metrica dal riquadro e rilasciala nell’intestazione della metrica della visualizzazione selezionata. </li> 
    </ol> <p>Questo funzionerà per tutte le visualizzazioni pertinenti, incluse tabelle, cluster di visitatori, matrice di correlazione, grafici a dispersione e il grafico a barre 2D (a seconda dell’asse). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Ricerca</b> </td> 
   <td colname="col2">Una casella di <span class="uicontrol"> ricerca</span> nei pannelli del Finder consente di filtrare i nomi per Dimensioni, Metriche e Filtri. 
    <ul id="ul_0F6F377E9906472E99008EBE7483F689"> 
     <li id="li_75857895EDB045C8B2960393854B257D"> <p>Corrispondenza pattern (ricerca semplice di tipo sferico). Iniziate a digitare il nome di un'entità dimensione, metrica o filtro richiesta nel campo di ricerca e solo le stringhe corrispondenti contenute in un punto qualsiasi del nome verranno filtrate e visualizzate nel riquadro Finder. </p> <p>Ad esempio, immettete: </p> <code><b>Search:</b>click</code> <p>È possibile ottenere i seguenti risultati nel Finder dimensioni: </p> <p><img placement="break" id="image_7CBAAABA92BB47658B7F9F5C0263CF20" src="assets/finders_glob_search.png" /> </p> <p>La corrispondenza dei pattern standard consente di utilizzare i caratteri jolly, ad esempio . (punto), "?" e "*" (stella). </p> </li> 
     <li id="li_044F9EC1399B44CD81E1852F85137704"> <p>Espressioni regolari. Sono inoltre supportate espressioni regolari più complesse per l'aggiunta di funzionalità di ricerca. Aggiungete il prefisso "re:" prima del termine di ricerca (senza spazi) da interpretare come espressione regolare. </p> <p>Ad esempio, immettete: </p> <code><b>Search:</b>re.*ip</code> <p>È possibile ottenere i seguenti risultati nel Finder dimensioni: </p> <p><img placement="break" id="image_F47DB90B36504997AA1C509855B89A47" src="assets/finders_regex_search.png" /> </p> </li> 
    </ul> <p>Per informazioni dettagliate sulla ricerca, consultate <a href="https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-reg-exp.html" format="http" scope="external"> espressioni</a>regolari. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Tipo dimensione</b> </td> 
   <td colname="col2">Nella scheda Dimensione, puoi fare clic con il pulsante destro del mouse sull’intestazione della scheda per ordinare in base al tipo di dimensione. <p><img id="image_FB44D0F4D36B4AD7A6165E0432211AB6" placement="break" src="assets/query_entity_search_types.png" /> 
     <ul id="ul_D36B8474730F4859BC7AA015CC1B8EF0"> 
      <li id="li_4AE1D5699D0E45AF880A134F886B8B19">Attributi (Attributes) - Dimensioni costruite in base alle caratteristiche del visitatore, prodotti, geografia, ora, video e altri attributi. </li> 
      <li id="li_0B2A08F8CBE94356AC506F95DC268C47">Cluster (Clusters) - Dimensioni integrate nel generatore di cluster. </li> 
      <li id="li_4BC3396A680B49A4B6BDAAD066826864">Scorte (Scores) - Dimensioni costruite all'interno del punteggio di propensione. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Etichetta</b> </td> 
   <td colname="col2">In ciascuna scheda, è possibile fare clic con il pulsante destro del mouse e selezionare <span class="uicontrol"> Etichetta</span> per rinominare il riquadro del Finder. <p><img placement="break" id="image_F61C57F6548646069242DFB2490C67B9" src="assets/label_change.png" /> </p> <p>Le etichette Dimensioni, Metriche e Filtri predefinite possono essere modificate in un nome scheda conforme alle convenzioni aziendali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Aggiungi elemento</b> </td> 
   <td colname="col2">In ciascuna scheda, è possibile fare clic con il pulsante destro del mouse e selezionare <span class="uicontrol"> Aggiungi elemento</span> per aprire una tabella e aggiungere manualmente Dimensioni, Metriche e Filtri. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Barra di ricerca</b> </td> 
   <td colname="col2">Fate clic con il pulsante destro del mouse nella barra <span class="uicontrol"> Finder</span> nella barra laterale sinistra per aprire un menu con le funzioni aggiuntive. <p><img placement="break" id="image_4DA4930294B84308A1E627C828C35663" src="assets/finders_menu.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Close</b> </td> 
   <td colname="col2">Fare clic con il pulsante destro del mouse nella barra <span class="uicontrol"> Finder</span> e selezionare <span class="uicontrol"> Chiudi</span> per chiudere il riquadro Finder. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Salva</b> </td> 
   <td colname="col2">Salvate l’elenco localmente facendo clic con il pulsante destro del mouse nella barra dell’intestazione e selezionando l’opzione <span class="uicontrol"> Salva</span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Esporta</b> </td> 
   <td colname="col2">Per esportare un elenco di dimensioni, metriche o filtri selezionati dal pannello Finder, fai clic con il pulsante destro del mouse nella barra Finder e seleziona <span class="uicontrol"> Esporta</span> dal menu. <p> Aggiungete un nome ed esportate in Microsoft Excel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Copia</b> </td> 
   <td colname="col2"> Copiare un elenco di dimensioni, metriche o filtri. Potete copiare come file o come elemento grafico in Sfondo scuro, Sfondo chiaro o Monocromatico. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Riduci a icona</b> </td> 
   <td colname="col2"> Riducete a icona il riquadro del Finder. Viene visualizzata solo la barra Finder. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Senza confini</b> </td> 
   <td colname="col2"> Visualizza un riquadro senza linee dei bordi per Finder nell'area di lavoro (ma non nella barra laterale sinistra). </td> 
  </tr> 
 </tbody> 
</table>

