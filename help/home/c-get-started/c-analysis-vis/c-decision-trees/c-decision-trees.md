---
description: Le strutture decisionali sono una visualizzazione di analisi predittiva utilizzata per valutare le caratteristiche e le relazioni dei visitatori. Il Generatore albero decisionale genera una visualizzazione struttura decisionale basata su uno specifico caso positivo e su un insieme di input.
solution: Analytics
title: Generatore albero decisionale
topic: Data workbench
uuid: 1f7e91ea-e5d9-4d8e-9fcf-cae4de42dfdd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Generatore albero decisionale{#decision-tree-builder}

Le strutture decisionali sono una visualizzazione di analisi predittiva utilizzata per valutare le caratteristiche e le relazioni dei visitatori. Il Generatore albero decisionale genera una visualizzazione struttura decisionale basata su uno specifico caso positivo e su un insieme di input.

Un albero decisionale è un classificatore binario con un insieme di regole (o filtri) che identifica i visitatori che soddisfano regole specifiche basate su un caso positivo. Una struttura decisionale imposta le regole per classificare i visitatori che soddisfano (o non soddisfano) questo caso positivo. Queste regole generano una mappa ad albero per fornire un livello di confidenza per soddisfare questi risultati positivi.

Un albero decisionale è costruito esaminando gli input a ogni livello e scegliendo quello che fornisce un massimo guadagno di informazioni in un punto di divisione specificato. I punti di divisione per ciascun livello variabile generano due set:

* Valori inferiori o uguali al punto di divisione e
* Valori maggiori del punto di divisione.

Usa strutture decisionali per

* Eseguite analisi e interpretazione significative in minor tempo.
* Implementa la generazione automatizzata dei segmenti.
* È possibile ricavare rapidamente delle inferenze da un modello basato su una grande quantità di dati.

![](assets/decision_tree_parts.png)

<table id="table_FCC5D63EF8A843D79B2338BD951025EA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Barra degli strumenti e menu</b> </p> <p>La barra degli strumenti include pulsanti e comandi di menu per l'albero decisionale, comprese le funzioni per impostare il caso positivo e aggiungere elenchi di input. </p> <p>Come per altre visualizzazioni, la casella <span class="uicontrol"> Elemento</span> consente di trascinare dimensioni ed elementi, anche se è possibile trascinare direttamente dal riquadro Finder. </p> <p>Per ulteriori informazioni, vedere <a href="../../../../home/c-get-started/c-analysis-vis/c-decision-trees/c-decision-trees-menu.md#concept-bfc4e80651a243d3966cc770b205606c"> Opzioni</a>albero decisionale. </p> </td> 
   <td colname="col2"> <p><b>Elenco input</b> </p> <p>Quest'area visualizza gli input nel modello ad albero. Sono colorati per corrispondere ai nodi nell'area Visualizzazione struttura. </p> <p>Facendo clic con il pulsante destro del mouse su un input è possibile rimuovere l'input dal modello e reimpostarlo. </p> <p>Se si passa il puntatore del mouse su un nodo struttura, vengono visualizzate le condizioni di divisione lungo il ramo a tale nodo e la previsione a tale nodo con il relativo valore di confidenza. </p> </td> 
   <td colname="col3"> <p><b>Visualizzazione struttura</b> </p> <p>Quest'area visualizza il modello ad albero con nodi foglia codificati a colori in base alla previsione: verde per una previsione True del caso Positivo e rosso per una previsione False. </p> <p>I nodi separati hanno colori diversi rispetto agli input che corrispondono alla loro condizione di selezione. Quando si passa il puntatore del mouse su un nodo, vengono visualizzate informazioni sulla divisione e vengono espansi gli input elencati per visualizzare i punti di divisione lungo il ramo e la distribuzione del set di formazione. </p> <p>Per impostazione predefinita, i nodi al di sotto di una soglia non vengono visualizzati. Fate clic su un nodo espandibile (indicato da un simbolo +) per esplorare un ramo. Fare clic sul nodo principale per tornare alla visualizzazione ad albero completa. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_E800327344194A6DBF37F273D8462E2A"></a> -->

