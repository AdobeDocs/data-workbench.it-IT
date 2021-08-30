---
description: Utilizza i pannelli Finder nella Data Workbench per selezionare metriche, dimensioni e filtri. Questi pannelli forniscono supporto per la ricerca, opzioni di ordinamento e funzionalità di trascinamento e rilascio.
title: Finder
uuid: 7a4144f5-133f-48ed-9613-1e42b1313120
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 1%

---


# Finder{#finders}

Utilizza i pannelli Finder nella Data Workbench per selezionare metriche, dimensioni e filtri. Questi pannelli forniscono supporto per la ricerca, opzioni di ordinamento e funzionalità di trascinamento e rilascio.

Un pannello Finder può essere aperto nella barra laterale sinistra o all’interno di un’area di lavoro.

![](assets/query_entity_panel_main.png)

<table id="table_3E43DBA0646842898F14F31374F9E39C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Finder Dimension </th> 
   <th colname="col2" class="entry"> Finder metriche </th> 
   <th colname="col3" class="entry"> Finder filtri </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Un elenco di tutte le dimensioni nel modello di query. </p><img placement="break" id="image_D7D317D84C0843BE8D324E5B9F7AF20D" src="assets/query_entity_dim_panel.png" /> </td> 
   <td colname="col2"> <p>Un elenco di tutte le metriche nel modello di query. </p><img placement="break" id="image_04553B2F2C6A48FE897B4EFF002BED59" src="assets/query_entity_metric_panel.png" /> </td> 
   <td colname="col3"> <p>Elenco di tutti i filtri creati per la tua organizzazione. </p><img placement="break" id="image_920E72D795644634A82D1955CB64B355" src="assets/query_entity_filters_panel.png" /> </td> 
  </tr> 
 </tbody> 
</table>

**Per aprire un Finder:**

* Fai clic con il pulsante destro del mouse in un’area di lavoro e seleziona **[!UICONTROL Tools]** > **[!UICONTROL Finder]**.

   Il riquadro Finder con schede per Metriche, Dimension e Filtri si aprirà nell’area di lavoro.

* Fai clic con il pulsante destro del mouse nella barra laterale sinistra e seleziona **[!UICONTROL Add]** > **[!UICONTROL Finder]**.

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
   <td colname="col1"><b>Trascinamento della selezione</b> </td> 
   <td colname="col2"> <p> Puoi trascinare dimensioni o metriche dal pannello a una visualizzazione nell’area di lavoro per modificarle o aggiungerne di nuove. </p> 
    <ol id="ol_612DC76EC04C4FCE938B20B388C43CE8"> 
     <li id="li_7F73B781141E4B8CAE9800F580F62E44">Tieni premuto i tasti <span class="uicontrol"> &lt;Ctrl&gt;</span> e <span class="uicontrol"> &lt;Alt&gt;</span> e seleziona la dimensione o la metrica dal pannello del Finder. </li> 
     <li id="li_631D57976F71415AA61F33EBBFDD128A">Trascina una nuova dimensione dal riquadro e rilasciala nella visualizzazione per modificare o aggiungere dimensioni. </li> 
     <li id="li_5329FB82225F46EBBE3A996A641058DE">Per aggiungere metriche, trascina una nuova metrica dal riquadro e rilasciala sull’intestazione della metrica della visualizzazione selezionata. </li> 
    </ol> <p>Questo funziona per tutte le visualizzazioni rilevanti, compresi tabelle, cluster di visitatori, matrice di correlazione, grafici a dispersione e grafico a barre 2D (a seconda dell’asse). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Ricerca</b> </td> 
   <td colname="col2">Una casella <span class="uicontrol"> Search</span> nei pannelli del Finder consente di filtrare i nomi per Dimension, metriche e filtri. 
    <ul id="ul_0F6F377E9906472E99008EBE7483F689"> 
     <li id="li_75857895EDB045C8B2960393854B257D"> <p>Corrispondenza pattern (ricerca glob semplice). Inizia a digitare il nome di un’entità dimensione, metrica o filtro obbligatoria nel campo Ricerca e solo le stringhe corrispondenti contenute in un punto qualsiasi del nome verranno filtrate e visualizzate nel riquadro Finder. </p> <p>Ad esempio, immetti: </p> <code><b>Search:</b>click</code> <p>È possibile ottenere i seguenti risultati nel Finder dei Dimension: </p> <p><img placement="break" id="image_7CBAAABA92BB47658B7F9F5C0263CF20" src="assets/finders_glob_search.png" /> </p> <p>La corrispondenza dei pattern standard consente di utilizzare i caratteri jolly, ad esempio . (punto), "?" e "*" (stella). </p> </li> 
     <li id="li_044F9EC1399B44CD81E1852F85137704"> <p>Espressioni regolari. Sono supportate anche espressioni regolari più complesse per l’aggiunta di funzionalità di ricerca. Aggiungi il prefisso "re:" prima del termine di ricerca (senza spazi) da interpretare come espressione regolare. </p> <p>Ad esempio, immetti: </p> <code><b>Search:</b>re.*ip</code> <p>È possibile ottenere i seguenti risultati nel Finder dei Dimension: </p> <p><img placement="break" id="image_F47DB90B36504997AA1C509855B89A47" src="assets/finders_regex_search.png" /> </p> </li> 
    </ul> <p>Per informazioni sulla ricerca approfondita, consulta <a href="https://experienceleague.adobe.com/docs/data-workbench/using/dataset/c-reg-exp.html" format="http" scope="external"> espressioni regolari</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Tipo di Dimension</b> </td> 
   <td colname="col2">Nella scheda Dimension, puoi fare clic con il pulsante destro del mouse sull’intestazione della scheda per ordinare in base al tipo di dimensione. <p><img id="image_FB44D0F4D36B4AD7A6165E0432211AB6" placement="break" src="assets/query_entity_search_types.png" /> 
     <ul id="ul_D36B8474730F4859BC7AA015CC1B8EF0"> 
      <li id="li_4AE1D5699D0E45AF880A134F886B8B19">Attributi: Dimension basati sulle caratteristiche del visitatore, dei prodotti, dell’area geografica, del tempo, del video e di altri attributi. </li> 
      <li id="li_0B2A08F8CBE94356AC506F95DC268C47">Cluster: Dimension generati nel generatore di cluster. </li> 
      <li id="li_4BC3396A680B49A4B6BDAAD066826864">Punteggi: Dimension generati nel punteggio di propensione. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Etichetta</b> </td> 
   <td colname="col2">In ogni scheda, puoi fare clic con il pulsante destro del mouse e selezionare <span class="uicontrol"> Etichetta</span> per rinominare il riquadro Finder. <p><img placement="break" id="image_F61C57F6548646069242DFB2490C67B9" src="assets/label_change.png" /> </p> <p>Le etichette Dimension, metriche e filtri predefinite possono essere modificate in un nome di scheda che soddisfi le convenzioni della tua organizzazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Aggiungi elemento</b> </td> 
   <td colname="col2">In ciascuna scheda, puoi fare clic con il pulsante destro del mouse e selezionare <span class="uicontrol"> Aggiungi elemento</span> per aprire una tabella e aggiungere manualmente Dimension, metriche e filtri. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Barra dei Finder</b> </td> 
   <td colname="col2">Fai clic con il pulsante destro del mouse sulla barra <span class="uicontrol"> Finder</span> nella barra laterale sinistra per aprire un menu per ulteriori funzioni. <p><img placement="break" id="image_4DA4930294B84308A1E627C828C35663" src="assets/finders_menu.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Close</b> </td> 
   <td colname="col2">Fare clic con il pulsante destro del mouse sulla barra <span class="uicontrol"> Finder</span> e selezionare <span class="uicontrol"> Chiudi</span> per chiudere un riquadro Finder. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Salva</b> </td> 
   <td colname="col2">Salva l'elenco localmente facendo clic con il pulsante destro del mouse sulla barra dell'intestazione e selezionando l'opzione <span class="uicontrol"> Save</span> (Salva). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Esporta</b> </td> 
   <td colname="col2">Per esportare un elenco di dimensioni, metriche o filtri selezionati dal pannello del Finder, fai clic con il pulsante destro del mouse nella barra dei Finder e seleziona <span class="uicontrol"> Esporta</span> dal menu. <p> Aggiungi un nome ed esporta in Microsoft Excel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Copia</b> </td> 
   <td colname="col2"> Copia un elenco di Dimension, metriche o filtri. È possibile copiare come file o come immagine in Sfondo scuro, Sfondo chiaro o Monocromatico. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Riduci a icona</b> </td> 
   <td colname="col2"> Riduci a icona il riquadro Finder. Viene visualizzata solo la barra dei Finder. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Senza confini</b> </td> 
   <td colname="col2"> Visualizza un riquadro senza linee dei bordi per i Finder nell’area di lavoro (ma non nella barra laterale sinistra). </td> 
  </tr> 
 </tbody> 
</table>

