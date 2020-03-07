---
description: Le linee di tendenza consentono di sovrapporre i grafici per confrontare e interpretare i dati.
title: Linee di tendenza
uuid: b1d81973-2181-4507-a0a5-adf5eeb9f926
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Linee di tendenza{#trend-lines}

Le linee di tendenza consentono di sovrapporre i grafici per confrontare e interpretare i dati.

Come per la visualizzazione [Dispersione](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/c-scat-plots.html) , ora è possibile impostare linee di tendenza su una visualizzazione grafico per visualizzare il tasso di variazione in base a linee lineari, esponenziali, di potenza o polinomiali. La funzione Trend Line (Linea di tendenza) consente di sovrapporre linee di tendenza su un grafico, più comunemente su una dimensione Time (Tempo).

Ad esempio, in questo confronto grafico, vediamo che le visite tendono verso l&#39;alto, ma gli ordini tendono verso il basso.

![](assets/trend_line.png)

Per aggiungere una linea di tendenza

1. Aprite un grafico e fate clic con il pulsante destro del mouse sul nome della metrica nell’angolo in alto a sinistra.
1. Fare clic **[!UICONTROL Trend Lines]** e selezionare una delle opzioni disponibili.

   ![](assets/trend_line_graph.png)

   Potete selezionare la linea di tendenza da visualizzare sopra il grafico come Lineare **** semplice, **Esponenziale**, **Potenza** o **Polinomiale**. Polinomiale creerà una linea di tendenza di regressione polinomiale. Lineare semplice crea una linea di tendenza come tasso di variazione lungo la linea di regressione. L&#39;esponenziale calcola una linea di tendenza come y = b*exp( a*x ) e Power come y = b*x`<sup>a</sup>`.

   La tendenza verrà calcolata e rappresentata sul grafico, e verrà aperto un callout con informazioni dettagliate sull&#39;equazione di tendenza.

   ![](assets/trend_line_detail.png)

