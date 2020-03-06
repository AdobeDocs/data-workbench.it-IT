---
description: Il grafico a barre in Workbench dati ora include un confronto di regressione per più metriche tra più grafici.
title: Grafico di analisi della regressione
uuid: 8512890e-f42b-4dce-826a-2b4bf2a215f4
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Regression Analysis Graph{#regression-analysis-graph}

Il grafico a barre in Workbench dati ora include un confronto di regressione per più metriche tra più grafici.

[I grafici](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/graphs/c-graphs.html) a barre in Workbench dati consentono di riportare le metriche in un grafico alle metriche in un altro grafico. Se disponete di più grafici, potete confrontare una metrica (come variabile indipendente) con un grafico che valuta altre metriche (come variabili dipendenti). Questo consente di determinare l&#39;intensità della relazione tra una variabile dipendente (la metrica stabilita per prima) e una serie di altre metriche in evoluzione (regressioni con la metrica dipendente stabilita).

L’analisi di regressione su una visualizzazione grafico consente agli analisti di eseguire scenari &quot;what-if&quot;. Ad esempio, se le visite aumentano a questo livello, quale impatto avrà questo aumento sulle entrate?

**Impostazione dell’analisi della regressione**

1. Seleziona il grafico come metrica dipendente per un confronto tra regressioni.

   Fate clic con il pulsante destro del mouse sul grafico e selezionate **Imposta come metrica di base per la regressione**.

   ![](assets/c_graph_regression_1.png)

1. Imposta altri grafici di metriche come variabili indipendenti.

   Fai clic con il pulsante destro del mouse sulla metrica e seleziona **[!UICONTROL Regress with `<base metric name>`]** per altre metriche.

   ![](assets/c_graph_regression.png)

1. Per visualizzare la regressione, fai clic con il pulsante destro del mouse sul grafico per spostare la barra verso l’alto o il basso.

   Se fai clic con il pulsante destro del mouse sul grafico per un valore specifico, puoi visualizzare i rapporti di regressione per ogni metrica in base ai valori verso l’alto o verso il basso.

   ![](assets/c_graph_regression_2.png)

   Ad esempio, se le mie Visualizzazioni pagina scendono a 86.041, le altre metriche avranno i seguenti valori: Visite a 12.183 e Visitatori per visita a 12.028.

   ![](assets/c_graph_regression_3.png)

   Se i valori Visitatori per visita aumentano a 26.141, le altre metriche saranno Visite a 26.560 e Visualizzazioni pagina a 189.091.

