---
description: Il grafico a barre nella Data Workbench ora include un confronto di regressione per più metriche su più grafici.
title: Grafico analisi di regressione
uuid: 8512890e-f42b-4dce-826a-2b4bf2a215f4
exl-id: bfc76c4a-edd5-41fe-b875-c199ea3beab5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 2%

---

# Grafico analisi di regressione{#regression-analysis-graph}

{{eol}}

Il grafico a barre nella Data Workbench ora include un confronto di regressione per più metriche su più grafici.

[Grafici a barre](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/graphs/c-graphs.html) in Data Workbench consente di riportare le metriche in un grafico alle metriche in un altro grafico. Se disponi di più grafici, puoi confrontare una metrica (come variabile indipendente) con un grafico che valuta altre metriche (come variabili dipendenti). Ciò ti consente di determinare l’intensità della relazione tra una variabile dipendente (la metrica stabilita per prima) e una serie di altre metriche mutevoli (regressioni con la metrica dipendente stabilita).

L’analisi di regressione su una visualizzazione grafico consente agli analisti di eseguire scenari &quot;what-if&quot;. Ad esempio, se le visite aumentano a questo livello, quale impatto avrà questo aumento sui ricavi?

**Impostazione dell’analisi della regressione**

1. Seleziona il grafico come metrica dipendente per un confronto di regressione.

   Fai clic con il pulsante destro del mouse sul grafico e seleziona **Imposta come metrica di base per la regressione**.

   ![](assets/c_graph_regression_1.png)

1. Imposta altri grafici delle metriche come variabili indipendenti.

   Fai clic con il pulsante destro del mouse sulla metrica e seleziona **[!UICONTROL Regress with `<base metric name>`]** per altre metriche.

   ![](assets/c_graph_regression.png)

1. Per visualizzare la regressione, fai clic con il pulsante destro del mouse sul grafico per spostarla in alto o in basso.

   Se fai clic con il pulsante destro del mouse sul grafico per un valore specifico, puoi visualizzare i rapporti di regressione per ogni metrica in base ai valori verso l’alto o verso il basso.

   ![](assets/c_graph_regression_2.png)

   Ad esempio, se le mie visualizzazioni pagina scendono a 86.041, le altre metriche avranno questi valori: Visite a 12.183 e Visitatori per visita a 12.028.

   ![](assets/c_graph_regression_3.png)

   Se i valori di Visitatori per visita aumentano a 26.141, le altre metriche saranno Visite a 26.560 e Visualizzazioni pagina a 189.091.
