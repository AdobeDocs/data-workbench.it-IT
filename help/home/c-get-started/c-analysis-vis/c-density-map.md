---
description: La visualizzazione mappa di densità visualizza gli elementi come rettangoli ombreggiati all’interno di una mappa quadrata.
title: Mappa di densità
uuid: c13cecee-f322-4757-aa90-12039173ff9f
exl-id: da37d954-cadb-42a6-a44b-9b38c0354a5d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 1%

---

# Mappa di densità{#density-map}

{{eol}}

La visualizzazione mappa di densità visualizza gli elementi come rettangoli ombreggiati all’interno di una mappa quadrata.

Le dimensioni dei rettangoli dipendono dai valori degli elementi, dove i valori più grandi sono rappresentati da rettangoli di area più grande. Simile a un grafico a torta, questa visualizzazione ti consente di vedere rapidamente quali elementi costituiscono la percentuale maggiore della dimensione selezionata.

![](assets/density_map_day_visits.png)

Per creare una mappa di densità:

1. Apri una nuova area di lavoro.

   Dopo aver aperto una nuova area di lavoro, potrebbe essere necessario fare clic su **Aggiungi** > **Sblocca temporaneamente**.
1. Fai clic su **[!UICONTROL Visualization]** > **[!UICONTROL Density Map]**.

1. Seleziona una **[!UICONTROL Dimension]** dal menu.

   Ad esempio, seleziona **[!UICONTROL Time]** > **[!UICONTROL Days]**.

   Al contrario, selezionando **[!UICONTROL Time]** > **[!UICONTROL Hours]** darebbe più elementi con valori più piccoli visualizzati come rettangoli più piccoli.

   >[!NOTE]
   >
   >Scegli una dimensione con più elementi in base alle tue esigenze. Il limite attuale è 200 degli elementi più grandi per ciascuna dimensione.

1. È possibile modificare le visualizzazioni delle dimensioni aprendo **[!UICONTROL Visualization]** > **[!UICONTROL Table]** e selezionando tra gli elementi dalla tabella da visualizzare nella mappa.

   ![](assets/density_map_day_selections.png)

   La mappa risponderà alle selezioni dalla tabella.

1. Passando il puntatore del mouse su elementi di piccole dimensioni, il nome e il valore verranno visualizzati nel testo visualizzato accanto al cursore del mouse.
1. Maschera gli elementi facendo clic con il pulsante destro del mouse e selezionando **[!UICONTROL Mask]**, quindi scegli un’opzione.

   ![](assets/density_map_day_mask.png)

   Per visualizzare tutti i nodi mascherati, seleziona **[!UICONTROL Unhide All]**.

1. Evidenziare gli elementi facendo clic con il pulsante destro del mouse e selezionando **[!UICONTROL Spotlight]**, quindi scegli un’opzione. L’evidenziazione consente di evidenziare e attenuare gli elementi in un intervallo.
1. Aggiungi una legenda colore all’area di lavoro. Puoi identificare i valori nella mappa utilizzando la legenda del colore.

   È possibile aggiungere una legenda colore all’area di lavoro e i nodi cambieranno colore in base alla dimensione aggiuntiva dei dati.
1. Per modificare la dimensione o la metrica, fai clic con il pulsante destro del mouse sul titolo della mappa e seleziona dal menu .

   ![](assets/density_map_change_dim.png)

1. Aggiungi callout facendo clic con il pulsante destro del mouse su una cella e selezionando **[!UICONTROL Add Callout]**. Puoi scegliere tra diversi tipi o visualizzazioni dal menu .

   ![](assets/density_map_callout.png)

1. Come in tutte le visualizzazioni, puoi fare clic con il pulsante destro del mouse sopra la barra del titolo per visualizzare i comandi di base Chiudi, Salva, Esporta in Microsoft Excel, Ordina, Copia, Riduci a icona e Senza bordi per visualizzare una visualizzazione senza bordo.

   ![](assets/density_map_export.png)

1. La mappa di densità consente di selezionare e deselezionare più elementi simili ad altre visualizzazioni:

* Fai clic con il pulsante sinistro del mouse per selezionare un elemento.
* Ctrl + clic per selezionare più elementi.
* Maiusc + clic per deselezionare un elemento.
* Fai clic con il pulsante destro del mouse all’interno degli elementi selezionati per aprire un menu. Quindi scegli **[!UICONTROL Deselect]** o **[!UICONTROL Deselect All]** per cancellare gli elementi selezionati.

## Opzioni aggiuntive {#section-d77defb012424de4a7ced8e5c93115bc}

Fai clic con il pulsante destro del mouse su Mappa densità per aprire un menu con le seguenti opzioni:

<table id="table_3ADA85031C834792BFD041E186962A41"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Add Callout </td> 
   <td colname="col2">Aggiungi un testo o un elemento grafico come callout nella visualizzazione per identificare o descrivere ulteriormente un elemento. <p>È inoltre possibile selezionare una legenda metrica vuota, una tabella, un grafico a linee o un grafico a dispersione in base all’elemento selezionato nella mappa di densità. Puoi quindi aggiungere metriche e dimensioni a queste visualizzazioni vuote a seconda delle esigenze. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maschera </td> 
   <td colname="col2">Le opzioni di mascheramento consentono di nascondere gli elementi selezionati. Fare clic con il pulsante destro del mouse per visualizzare le opzioni Maschera. <p><span class="uicontrol"> Nascondi questo elemento</span>- Scegli questa opzione per mascherare un singolo elemento selezionato. </p> <p><span class="uicontrol"> Nascondi selezionati</span>- Scegli questa opzione per mascherare più elementi selezionati. </p> <p><span class="uicontrol"> Mostra in alto</span>— scegli questa opzione per visualizzare solo i primi 100, 50, 25 o 10 elementi principali in base ai valori nella mappa di densità. </p> <p><span class="uicontrol"> Mostra in basso</span>- Scegli questa opzione per visualizzare solo i 100, 50, 25 o 10 elementi principali inferiori in base ai valori nella mappa di densità. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Luce </td> 
   <td colname="col2"> L’evidenziazione consente di evidenziare e attenuare gli elementi in un intervallo. Fare clic con il pulsante destro del mouse per aprire un menu di opzioni. <p><span class="uicontrol"> Mostra in alto</span>— scegli questa opzione per evidenziare solo i primi 100, 50, 25 o 10 elementi principali in base ai valori nella mappa di densità. </p> <p><span class="uicontrol"> Mostra in basso</span>- Scegli questa opzione per evidenziare solo i 100, 50, 25 o 10 elementi principali in base ai valori nella mappa di densità. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Deseleziona </p> <p>Deseleziona tutto </p> </td> 
   <td colname="col2"> <p> Selezionare questi comandi per deselezionare l’elemento corrente, se selezionato, oppure deselezionare tutti gli elementi selezionati. </p> </td> 
  </tr> 
 </tbody> 
</table>
