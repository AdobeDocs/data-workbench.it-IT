---
description: La visualizzazione della mappa di densità visualizza gli elementi come rettangoli ombreggiati all’interno di una mappa quadrata.
solution: Analytics
title: Mappa densità
topic: Data workbench
uuid: c13cecee-f322-4757-aa90-12039173ff9f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mappa densità{#density-map}

La visualizzazione della mappa di densità visualizza gli elementi come rettangoli ombreggiati all’interno di una mappa quadrata.

Le dimensioni dei rettangoli dipendono dai valori degli elementi, dove i valori maggiori sono rappresentati da rettangoli con un&#39;area più grande. Simile a un grafico a torta, questa visualizzazione consente di vedere rapidamente quali elementi costituiscono la percentuale maggiore della dimensione selezionata.

![](assets/density_map_day_visits.png)

Per creare una mappa di densità:

1. Aprite una nuova area di lavoro.

   Dopo aver aperto una nuova area di lavoro, potrebbe essere necessario fare clic su **Aggiungi** > Sblocca **temporaneamente**.
1. Fai clic su **[!UICONTROL Visualization]** > **[!UICONTROL Density Map]**.

1. Select a **[!UICONTROL Dimension]** from the menu.

   Ad esempio, selezionare **[!UICONTROL Time]** > **[!UICONTROL Days]**.

   Per contro, selezionando **[!UICONTROL Time]** > **[!UICONTROL Hours]** si otterrebbero più elementi con valori più piccoli che verranno visualizzati come rettangoli più piccoli.

   >[!NOTE]
   >
   >Sarà necessario scegliere una dimensione con più elementi in base alle proprie esigenze. Il limite corrente è 200 degli elementi più grandi per ciascuna dimensione.

1. Potete modificare le viste delle quote aprendo **[!UICONTROL Visualization]** > **[!UICONTROL Table]** e selezionando tra gli elementi dalla tabella per visualizzarle nella mappa.

   ![](assets/density_map_day_selections.png)

   La mappa risponderà alle selezioni dalla tabella.

1. Quando si passa il puntatore del mouse su elementi di piccole dimensioni, vengono visualizzati il nome e il valore nel testo accanto al cursore del mouse.
1. Mascherare gli elementi facendo clic con il pulsante destro del mouse e selezionando **[!UICONTROL Mask]**, quindi scegliere un’opzione.

   ![](assets/density_map_day_mask.png)

   Per visualizzare tutti i nodi mascherati, selezionare **[!UICONTROL Unhide All]**.

1. Evidenzia gli elementi facendo clic con il pulsante destro del mouse e selezionando **[!UICONTROL Spotlight]**, quindi scegliete un’opzione. L’evidenziazione consente di evidenziare e ridefinire gli elementi in un intervallo.
1. Aggiungete una legenda colore all’area di lavoro. Potete identificare i valori nella mappa utilizzando la legenda del colore.

   Potete aggiungere una legenda colore all’area di lavoro e i nodi cambiano colore in base alla dimensione aggiuntiva dei dati.
1. Per modificare la dimensione o la metrica, fai clic con il pulsante destro del mouse sul titolo della mappa e scegli dal menu.

   ![](assets/density_map_change_dim.png)

1. Aggiungete i callout facendo clic con il pulsante destro del mouse su una cella e selezionando **[!UICONTROL Add Callout]**. Puoi scegliere tra diversi tipi o visualizzazioni dal menu.

   ![](assets/density_map_callout.png)

1. Come in tutte le visualizzazioni, puoi fare clic con il pulsante destro del mouse sopra la barra del titolo per i comandi di base Chiudi, Salva, Esporta in Microsoft Excel, Ordina, Copia, Riduci a icona e Senza bordi per visualizzare una visualizzazione senza bordo.

   ![](assets/density_map_export.png)

1. La mappa densità consente di selezionare e deselezionare più elementi simili ad altre visualizzazioni:

* Fate clic con il pulsante sinistro del mouse per selezionare un elemento.
* Ctrl+clic per selezionare più elementi.
* Maiusc + clic per deselezionare un elemento.
* Fare clic con il pulsante destro del mouse all&#39;interno degli elementi selezionati per aprire un menu. Quindi scegliete **[!UICONTROL Deselect]** o **[!UICONTROL Deselect All]** cancellare gli elementi selezionati.

## Opzioni aggiuntive {#section-d77defb012424de4a7ced8e5c93115bc}

Fate clic con il pulsante destro del mouse sulla mappa densità per aprire un menu con le seguenti opzioni:

<table id="table_3ADA85031C834792BFD041E186962A41"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Aggiungi callout </td> 
   <td colname="col2">Aggiungete un testo o un elemento grafico come callout nella visualizzazione per identificare o descrivere ulteriormente un elemento. <p>Potete anche selezionare una legenda metrica vuota, una tabella, un grafico a linee o un grafico a dispersione in base all’elemento selezionato nella mappa densità. Puoi quindi aggiungere metriche e dimensioni a queste visualizzazioni vuote in base alle esigenze. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maschera </td> 
   <td colname="col2">Le opzioni di mascheramento consentono di nascondere gli elementi selezionati. Fate clic con il pulsante destro del mouse per visualizzare le opzioni Maschera. <p><span class="uicontrol"> Nascondi questo elemento</span>(Hide This Element) - Scegliete questa opzione per mascherare un singolo elemento selezionato. </p> <p><span class="uicontrol"> Nascondi selezionati</span>(Hide Selected) - Scegliete questa opzione per mascherare più elementi selezionati. </p> <p><span class="uicontrol"> Mostra in alto</span>— Scegliete questa opzione per visualizzare solo i primi 100, 50, 25 o 10 elementi principali in base ai valori nella mappa densità. </p> <p><span class="uicontrol"> Mostra in basso</span>(Show Bottom) - Scegliete questa opzione per visualizzare solo gli elementi inferiori a 100, 50, 25 o 10 in base ai valori nella mappa densità. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Luce </td> 
   <td colname="col2"> L’evidenziazione consente di evidenziare e ridefinire gli elementi in un intervallo. Fare clic con il pulsante destro del mouse per aprire un menu di opzioni. <p><span class="uicontrol"> Mostra in alto</span>— Scegliete questa opzione per evidenziare solo i primi 100, 50, 25 o 10 elementi principali in base ai valori nella mappa densità. </p> <p><span class="uicontrol"> Mostra in basso</span>(Show Bottom) - Scegliete questa opzione per evidenziare solo gli elementi inferiori a 100, 50, 25 o 10 in base ai valori nella mappa densità. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Deseleziona </p> <p>Deseleziona tutto </p> </td> 
   <td colname="col2"> <p> Selezionate questi comandi per deselezionare l’elemento corrente, se selezionato, oppure per deselezionare tutti gli elementi selezionati. </p> </td> 
  </tr> 
 </tbody> 
</table>

