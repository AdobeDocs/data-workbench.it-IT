---
description: È possibile creare mappe di processo 2D e 3D trascinando gli elementi da grafici a barre, tabelle e viste gerarchiche su una mappa vuota.
solution: Analytics
title: Creare una mappa di processo
topic: Data workbench
uuid: dbcde637-0411-4296-99ca-5510e0285e4b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creare una mappa di processo{#create-a-process-map}

È possibile creare mappe di processo 2D e 3D trascinando gli elementi da grafici a barre, tabelle e viste gerarchiche su una mappa vuota.

Gli elementi che è possibile aggiungere devono essere elementi della dimensione di base della mappa di processo. È inoltre possibile trascinare i nodi da una mappa di processo a un&#39;altra purché le mappe utilizzino la stessa dimensione di base. Inoltre, l&#39;intera mappa può essere ingrandita o spostata per essere messa a fuoco su un particolare nodo, oppure può essere modificata in altri tipi di visualizzazione. Consulta [Zoom in Visualizations (Visualizzazione in visualizzazioni)](../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

**Per aggiungere elementi a una mappa di processo utilizzando una tabella o un grafico a barre**

* Da qualsiasi grafico a tabelle o a barre con la stessa dimensione di base della mappa di processo, premere Ctrl+Alt mentre si fa clic e si trascina i singoli elementi sulla mappa di processo. Il cursore del mouse visualizza la parola &quot;No&quot; finché il mouse non raggiunge la mappa del processo.

   >[!NOTE]
   >
   >Gli elementi che è possibile aggiungere devono essere elementi della dimensione di base della mappa di processo.

   ![](assets/vis_2DProcessMap_addPages.png)

**Aggiunta di elementi a una mappa di processo tramite una visualizzazione gerarchica**

>[!NOTE]
>
>Adobe consiglia di aggiungere nodi dal livello più alto della gerarchia che si sta analizzando.

1. Da qualsiasi grafico a tabelle o a barre con la stessa dimensione di base della mappa di processo, fate clic con il pulsante destro del mouse su un elemento o sull’etichetta della dimensione di base e fate clic **[!UICONTROL Hierarchy View]**.
1. Premere Ctrl+Alt mentre si fa clic e si trascinano gli elementi sulla mappa di processo. Il cursore del mouse visualizza la parola &quot;No&quot; finché il mouse non raggiunge la mappa.

   >[!NOTE]
   >
   >Gli elementi che è possibile aggiungere devono essere elementi della dimensione di base della mappa di processo.

   Se trascinate un singolo elemento su una mappa di processo, viene creato un nodo di mappa solo per tale elemento, ma se selezionate più elementi (un gruppo) o una cartella contenente più elementi, trascinando dalla gerarchia viene creato un singolo nodo per tale gruppo o cartella. Ad esempio, se state lavorando con i dati del sito Web, trascinando una cartella denominata [!DNL site.com/cgi-bin] su una mappa viene creato un nodo denominato [!DNL site.com/cgi-bin/*], che rappresenta tutte le pagine e le directory figlie di tale cartella.

Per ulteriori informazioni sulle viste gerarchiche delle pagine, vedere [Applicazione delle viste](../../../../home/c-get-started/c-analysis-vis/c-tables/c-hier-vews.md#concept-b461183424a841eb94f8143a0eaf9bff)gerarchiche.

**Aggiunta di nodi a una mappa di processo da un&#39;altra mappa di processo**

>[!NOTE]
>
>Le mappe processo devono avere la stessa dimensione di base.

* Copiare un nodo dal primo al secondo mapping di processo utilizzando i seguenti metodi:

   * Per copiare i singoli nodi, fate clic e trascinate ciascun nodo nella seconda mappa del processo.
   * Per copiare più nodi, Ctrl+clic e trascinate per creare una casella intorno ai nodi da copiare, quindi fate clic e trascinate i nodi evidenziati nella seconda mappa di processo. Tutti i nodi evidenziati vengono copiati nella seconda mappa di processo.

