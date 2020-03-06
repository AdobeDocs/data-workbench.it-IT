---
description: Le tabelle dei dettagli consentono di visualizzare informazioni aggiuntive su un sottoinsieme di dati, definito dalle selezioni effettuate in altre visualizzazioni.
solution: Analytics
title: Tabella dei dettagli
topic: Data workbench
uuid: 2becff5e-c78d-4ac7-8cda-814ad0193efd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tabella dei dettagli{#detail-table}

Le tabelle dei dettagli consentono di visualizzare informazioni aggiuntive su un sottoinsieme di dati, definito dalle selezioni effettuate in altre visualizzazioni.

Le informazioni aggiuntive visualizzate sono un esempio di tutti i dati disponibili.

![](assets/vis_details.png)

Nella tabella seguente sono descritti gli elementi di una tabella di dettaglio.

<table id="table_C88C7F7F5AEA4820B908923E45CC0A62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col02" class="entry"> Colore </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Livello </p> </td> 
   <td colname="col02"> <p>Rosa </p> </td> 
   <td colname="col2"> <p>Qualsiasi dimensione numerabile per la quale si desidera visualizzare informazioni dettagliate su attributi e metriche. Il livello è preceduto dal numero di elementi visualizzati rispetto al numero di elementi disponibili, ad esempio 6/444 indica che 6 elementi sono visualizzati su un possibile 444. Nell'esempio precedente, il livello Visitatori indica che tutti i dettagli forniti sono basati sul visitatore. Il livello Visualizzazioni pagina indica che tutti i dettagli forniti sono basati sulla visualizzazione della pagina. La visualizzazione simultanea di più livelli è utile per analizzare i dati con diversi elementi principali comparabili. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attributo </p> </td> 
   <td colname="col02"> <p>Verde </p> </td> 
   <td colname="col2"> <p>Qualsiasi dimensione uno-a-molti o uno-a-uno con il livello, come Città ai Visitatori. Ogni riga visualizza l'elemento correlato a ciascun elemento del livello selezionato. Nell’esempio precedente, gli attributi Domain (Dominio) e City (Città) elencano il dominio e la città per ciascuno dei visitatori di esempio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrica </p> </td> 
   <td colname="col02"> <p>Blu </p> </td> 
   <td colname="col2"> <p>Dettagli della metrica sul livello selezionato. Nell’esempio precedente, con il livello impostato su Visitatori, la metrica Visualizzazioni pagina mostra il numero di visualizzazioni di pagina per un singolo visitatore, mentre il livello Visualizzazioni pagina fornisce i dettagli su ciascuna di queste visualizzazioni di pagina. </p> </td> 
  </tr> 
 </tbody> 
</table>

Supponiamo che tu stia lavorando con i dati del sito web e desideri scoprire quali pagine sono state visitate dai visitatori in città particolari e da domini specifici durante un particolare intervallo di tempo.

Prima devi creare una visualizzazione che mostri l’intervallo di tempo al quale sei interessato, quindi devi selezionare tale intervallo di tempo. Ora è possibile aggiungere una tabella di dettaglio per visualizzare i dettagli desiderati per un numero di visitatori di esempio nel set di dati.

Per visualizzare i dettagli sopra descritti, è necessario completare i seguenti passaggi:

1. Fare clic con il pulsante destro del mouse all&#39;interno della tabella dei dettagli e scegliere **[!UICONTROL Add Level]** > **[!UICONTROL Visitor]**.
1. Fare clic con il pulsante destro del mouse all&#39;interno della tabella dei dettagli e scegliere **[!UICONTROL Add Level]** > **[!UICONTROL Page View]**.
1. Fare clic con il pulsante destro del mouse sull&#39;intestazione del **[!UICONTROL Visitors]** livello e scegliere **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL Domain]**.
1. Fai clic con il pulsante destro del mouse nell’intestazione del livello Visitatori e fai clic su **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL City]**.
1. Fai clic con il pulsante destro del mouse nell’intestazione del livello Visitatori e fai clic su **[!UICONTROL Add Metric]** > **[!UICONTROL Page Views]**.
1. Fare clic con il pulsante destro del mouse all&#39;interno dell&#39;intestazione del livello Visualizzazioni di pagina e scegliere **[!UICONTROL Add Attribute]** > **[!UICONTROL Page]** > **[!UICONTROL Page]**.

L’area di lavoro di esempio seguente illustra i dettagli relativi a un campionamento casuale di sei visitatori del sito durante l’intervallo di tempo specificato.

![](assets/client-tab1.png)

## Aggiungere un livello {#section-f948d3361fd84906ac4d9ebce520bfd0}

* Fare clic con il pulsante destro del mouse all&#39;interno della tabella dei dettagli e scegliere **[!UICONTROL Add Level]** > *&lt;**[!UICONTROL dimension name]**>*.

![](assets/mnu_DetailsTable_AddLevel.png)

## Rimozione di un livello {#section-a8c820e0b656451e98e5ea75373edefc}

* Fare clic con il pulsante destro del mouse sull&#39;intestazione del livello esistente e scegliere **[!UICONTROL Remove Level]** > *&lt;**[!UICONTROL dimension name]**>*.

![](assets/mnu_DetailsTable_Level.png)

## Add attributes and metrics {#section-cdda2df3c9a448d5b9770686c8b8efb3}

* Fare clic con il pulsante destro del mouse sull&#39;intestazione di un attributo o di una metrica e scegliere **[!UICONTROL Add Attribute]** > *&lt;**[!UICONTROL attribute name]**>* o **[!UICONTROL Add Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_DetailsTable.png)

## Rimozione di attributi e metriche {#section-4002ac957a2846678f9940270987d651}

* Fare clic con il pulsante destro del mouse sulla colonna da rimuovere e scegliere **[!UICONTROL Remove Attribute]** > *&lt;**[!UICONTROL attribute name]**>* o **[!UICONTROL Remove Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_DetailsTable.png)

## Esporta in Microsoft Excel {#section-a9eaba63c88a4598836a34669ba8cac1}

Per informazioni sull&#39;esportazione delle finestre, vedere [Esportazione dei dati](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)delle finestre.
