---
description: Valutare un Albero decisionale utilizzando l’opzione Albero di regressione con nuove funzioni di campionamento e visualizzazione.
title: Opzione dell’albero di regressione per l’alberi delle decisioni
uuid: 1e3b5d5f-1fed-49c9-9a4d-d220c28075ac
exl-id: e5f8d525-1530-4169-b246-cdaf30e984c0
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 3%

---

# Opzione dell’albero di regressione per l’alberi delle decisioni{#regression-tree-option-for-decision-tree}

Valutare un Albero decisionale utilizzando l’opzione Albero di regressione con nuove funzioni di campionamento e visualizzazione.

Valutare un Albero decisionale utilizzando l&#39;opzione Albero di regressione facendo clic con il pulsante destro del mouse e selezionando Opzioni > **Albero di regressione** all&#39;interno di una visualizzazione Albero decisionale.

**Generatore** albero delle decisioni aggiornato: Il nuovo algoritmo è stato introdotto per la creazione di un  [Albero](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/decision-trees/c-decision-trees.html) decisionale. Gestisce dati più generali e fornisce una visualizzazione più informativa per migliorare la precisione della previsione.

**Modulo** di campionamento dei dati migliorato: Uno schema di campionamento adattivo aggiornato consente all’albero delle decisioni e al punteggio tendenza di ottenere risultati di precisione più elevati.

![](assets/CART-RegressionTreeOptions.jpg)

Verde e rosso indicano vero o falso. La saturazione del colore, ad esempio il rosso profondo e il rosso chiaro, viene utilizzata per indicare la probabilità. Ad esempio, un nodo con rosso profondo ha una probabilità molto alta di essere falso, mentre un nodo con rosso chiaro ha una probabilità più bassa di essere falso. Un nodo con un colore verde profondo ha una probabilità molto elevata di essere vero.

Tutti gli alberi decisionali hanno larghezze di ramo diverse per indicare il livello di traffico per quel ramo dell&#39;albero.

In una visualizzazione Struttura decisionale, fai clic con il pulsante destro del mouse e seleziona Opzioni > **Albero di regressione**. Quando questa opzione è selezionata, vengono fornite ulteriori impostazioni:

<table id="table_39E025A3E0B549B4BEDCE0D30A499211"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione di regressione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Utilizza Ogni Funzione Una Sola Volta</b> </p> </td> 
   <td colname="col2"> <p>Selezionando questa opzione non si utilizzerà una feature più di una volta (come l'albero decisionale originale), quindi se si dispone di cinque input, l'albero non sarà più di cinque livelli e la struttura ad albero apparirà simile a un Albero decisionale (ma un po' più complicato). Questa opzione rende la struttura ad albero veloce utilizzando ogni feature una sola volta (come un Albero decisionale originale). L’utilizzo di questa funzione è un’impostazione predefinita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Impostazione del livello dell'albero di regressione  </b> </p> </td> 
   <td colname="col2"> <p>Questa opzione controlla la complessità dell'albero di regressione. A seconda dei dati, potrebbe essere necessario creare un albero <i>Fine</i> (con una struttura complicata con più nodi) per ottenere una classificazione dell'albero più significativa. Se hai molti dati, allora un albero relativamente <i>grossolano</i> (meno complicato con meno nodi) potrebbe funzionare bene. </p> <p> <p>Nota: <i>Tipico</i> è l'impostazione predefinita. Ci sono alcuni casi estremi in cui l'impostazione <i>Tipica</i> non funziona bene e l'impostazione <i>Grosso</i> o <i>Fine</i> può fornire una visualizzazione migliore dei dati. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Fine</i>: L’albero più complesso con i livelli più granulari di reporting e la maggior parte dei rami. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Tipico</i>: Livello medio di granularità e rami. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>grossolano</i>: L'albero meno complesso con le categorie meno definite e meno rami. </p> </td> 
  </tr> 
 </tbody> 
</table>
