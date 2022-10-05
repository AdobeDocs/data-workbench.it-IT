---
description: Gli alberi decisionali sono una visualizzazione di analisi predittiva utilizzata per valutare le caratteristiche e le relazioni dei visitatori. Il Generatore albero delle decisioni genera una visualizzazione dell’albero delle decisioni basata su un caso positivo specificato e su un insieme di input.
title: Decision Tree Builder (Generatore dell’albero delle decisioni)
uuid: 1f7e91ea-e5d9-4d8e-9fcf-cae4de42dfdd
exl-id: d93e6a34-be59-4af5-84c3-c13deb98b57b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 1%

---

# Decision Tree Builder (Generatore dell’albero delle decisioni) {#decision-tree-builder}

{{eol}}

Gli alberi decisionali sono una visualizzazione di analisi predittiva utilizzata per valutare le caratteristiche e le relazioni dei visitatori. Il Generatore albero delle decisioni genera una visualizzazione dell’albero delle decisioni basata su un caso positivo specificato e su un insieme di input.

Un Albero decisionale è un classificatore binario con un set di regole (o filtri) che identifica i visitatori che soddisfano regole specifiche basate su un caso positivo. Una struttura decisionale imposta le regole per classificare i visitatori che soddisfano (o non soddisfano) questo caso positivo. Queste regole generano una mappa ad albero per fornire un livello di affidabilità in modo da soddisfare questi risultati positivi dei casi.

Un Albero decisionale è costruito esaminando gli input a ogni livello e scegliendo quello che fornisce un massimo guadagno di informazioni in un determinato punto di divisione. I punti di divisione per ogni livello variabile generano due set:

* Valori inferiori o uguali al punto di divisione e
* Valori maggiori del punto di divisione.

Utilizzare gli alberi decisionali per

* Effettuare analisi e interpretazioni significative in minor tempo.
* Utilizza la generazione automatica dei segmenti.
* Crea rapidamente deduzioni da un modello basato su una grande quantità di dati.

![](assets/decision_tree_parts.png)

<table id="table_FCC5D63EF8A843D79B2338BD951025EA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Barra degli strumenti e menu</b> </p> <p>La barra degli strumenti include pulsanti e comandi di menu per l'albero delle decisioni, incluse le funzioni per impostare il caso positivo e aggiungere gli elenchi di input. </p> <p>Come altre visualizzazioni, la <span class="uicontrol"> Elemento</span> consente di trascinare Dimension ed elementi, anche se è possibile trascinarli direttamente dal riquadro Finder. </p> <p>Per ulteriori informazioni, consulta <a href="../../../../home/c-get-started/c-analysis-vis/c-decision-trees/c-decision-trees-menu.md#concept-bfc4e80651a243d3966cc770b205606c"> Opzioni dell’albero delle decisioni</a>. </p> </td> 
   <td colname="col2"> <p><b>Inserimento</b> </p> <p>Quest'area visualizza gli input nel modello ad albero. Sono codificati a colori per far corrispondere i nodi nell'area Visualizzazione ad albero. </p> <p>Facendo clic con il pulsante destro del mouse su un input è possibile rimuovere l'input dal modello e ripristinarlo. </p> <p>Se passi il puntatore del mouse su un nodo ad albero, verranno visualizzate le condizioni di divisione lungo il ramo a quel nodo e la previsione in quel nodo con il relativo valore di affidabilità. </p> </td> 
   <td colname="col3"> <p><b>Visualizzazione struttura</b> </p> <p>Quest'area visualizza il modello ad albero con nodi foglia codificati a colori in base alla sua previsione: verde per una previsione True del caso positivo e rosso per una previsione False. </p> <p>I nodi divisi sono codificati a colori in base agli input che corrispondono alla loro condizione di selezione. Passando il puntatore del mouse su un nodo vengono visualizzate informazioni sulla suddivisione ed è possibile espandere l'elenco degli input per visualizzare i punti di divisione lungo il ramo e la distribuzione del set di addestramento. </p> <p>I nodi al di sotto di una soglia non vengono visualizzati per impostazione predefinita. Fai clic su un nodo espandibile (indicato da un simbolo +) per esplorare un ramo. Fai clic sul nodo principale per tornare alla visualizzazione ad albero completa. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_E800327344194A6DBF37F273D8462E2A"></a> -->
