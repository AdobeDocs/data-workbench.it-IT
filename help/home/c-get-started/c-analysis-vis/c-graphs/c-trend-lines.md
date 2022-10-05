---
description: Le linee di tendenza consentono di sovrapporre grafici per confrontare e interpretare i dati.
title: Linee di tendenza
uuid: b1d81973-2181-4507-a0a5-adf5eeb9f926
exl-id: 3e7e9218-49b2-4877-a4bd-318b838089e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# Linee di tendenza{#trend-lines}

{{eol}}

Le linee di tendenza consentono di sovrapporre grafici per confrontare e interpretare i dati.

Come il [Dispersione](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-scat-plots.html) Con la visualizzazione, ora puoi impostare linee di tendenza su una visualizzazione grafico per visualizzare il tasso di variazione in base a linee lineari, esponenziali, di potenza o polinomiali. La funzione Trend Line (Linea di tendenza) consente di sovrapporre linee di tendenza su un grafico, più comunemente su una dimensione Time.

Ad esempio, in questo confronto grafico, possiamo vedere che le visite tendono verso l’alto, ma gli ordini tendono verso il basso.

![](assets/trend_line.png)

Per aggiungere una linea di tendenza

1. Apri un grafico e fai clic con il pulsante destro del mouse sul nome della metrica nell’angolo in alto a sinistra.
1. Fai clic su **[!UICONTROL Trend Lines]** e selezionare tra le opzioni.

   ![](assets/trend_line_graph.png)

   Puoi selezionare la linea di tendenza da visualizzare sul grafico come **Lineare semplice**, **Esponenziale**, **Potenza** oppure **Polinomiale**. Polinomiale creerà una linea di tendenza di regressione polinomiale. Lineare semplice crea una linea di tendenza come il tasso di variazione lungo la linea di regressione. L’esponenziale calcola una linea di tendenza come y = b&#42;exp( a&#42;x ) e Power as y = b&#42;x`<sup>a</sup>`.

   La tendenza verrà calcolata e resa sul grafico, e verrà aperto un callout con informazioni dettagliate sull’equazione di tendenza.

   ![](assets/trend_line_detail.png)
