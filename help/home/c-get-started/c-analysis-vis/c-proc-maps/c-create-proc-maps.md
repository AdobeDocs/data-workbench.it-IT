---
description: È possibile creare mappe del processo 2D e 3D trascinando gli elementi da grafici a barre, tabelle e viste gerarchiche su una mappa vuota.
title: Creare una mappa del processo
uuid: dbcde637-0411-4296-99ca-5510e0285e4b
exl-id: 2e417a8e-5b1c-4dce-9e4e-ac7ed044564c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 1%

---

# Creare una mappa del processo{#create-a-process-map}

È possibile creare mappe del processo 2D e 3D trascinando gli elementi da grafici a barre, tabelle e viste gerarchiche su una mappa vuota.

Gli elementi che è possibile aggiungere devono essere elementi della dimensione di base della mappa di processo. Puoi anche trascinare i nodi da una mappa del processo a un&#39;altra, purché le mappe utilizzino la stessa dimensione di base. Inoltre, è possibile ingrandire o spostare l’intera mappa per concentrarla su un particolare nodo, oppure modificarla in altri tipi di visualizzazione. Consulta [Zoom in Visualizations](../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

**Per aggiungere elementi a una mappa del processo utilizzando una tabella o un grafico a barre**

* Da qualsiasi tabella o grafico a barre con la stessa dimensione di base della mappa del processo, premi Ctrl+Alt mentre fai clic su e trascina singoli elementi nella mappa del processo. Il cursore del mouse visualizza la parola &quot;No&quot; finché il mouse non raggiunge la mappa del processo.

   >[!NOTE]
   >
   >Gli elementi che è possibile aggiungere devono essere elementi della dimensione di base della mappa di processo.

   ![](assets/vis_2DProcessMap_addPages.png)

**Per aggiungere elementi a una mappa del processo utilizzando una vista gerarchica**

>[!NOTE]
>
>Adobe consiglia di aggiungere nodi dal livello più alto della gerarchia che si sta analizzando.

1. Da qualsiasi tabella o grafico a barre con la stessa dimensione di base della mappa del processo, fai clic con il pulsante destro del mouse su un elemento o sull’etichetta della dimensione di base e fai clic su **[!UICONTROL Hierarchy View]**.
1. Premi Ctrl+Alt mentre fai clic su e trascina gli elementi sulla mappa del processo. Il cursore del mouse visualizza la parola &quot;No&quot; finché il mouse non raggiunge la mappa.

   >[!NOTE]
   >
   >Gli elementi che è possibile aggiungere devono essere elementi della dimensione di base della mappa di processo.

   Se si trascina un singolo elemento su una mappa del processo, viene creato un nodo mappa solo per tale elemento, ma se si selezionano più elementi (un gruppo) o una cartella contenente più elementi, trascinando dalla gerarchia viene creato un singolo nodo per tale gruppo o cartella. Ad esempio, se lavori con i dati del sito web, trascinando una cartella denominata [!DNL site.com/cgi-bin] su una mappa viene creato un nodo denominato [!DNL site.com/cgi-bin/*], che rappresenta tutte le pagine e le directory figlie di tale cartella.

Per ulteriori informazioni sulle visualizzazioni gerarchiche delle pagine, vedere [Applicazione delle visualizzazioni gerarchiche](../../../../home/c-get-started/c-analysis-vis/c-tables/c-hier-vews.md#concept-b461183424a841eb94f8143a0eaf9bff).

**Per aggiungere nodi a una mappa del processo da un&#39;altra mappa del processo**

>[!NOTE]
>
>Le mappe del processo devono avere la stessa dimensione di base.

* Copia un nodo dalla prima alla seconda mappa del processo utilizzando i seguenti metodi:

   * Per copiare singoli nodi, fai clic su e trascina ciascun nodo nella seconda mappa del processo.
   * Per copiare più nodi, tieni premuto Ctrl e trascina per creare una casella intorno ai nodi da copiare, quindi fai clic e trascina i nodi evidenziati nella seconda mappa del processo. Tutti i nodi evidenziati vengono copiati nella seconda mappa del processo.
