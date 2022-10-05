---
description: La visualizzazione Chord (Accordi) consente di mostrare sia la proporzione che la correlazione tra le metriche, mostrando accordi più grandi come indicazione di una correlazione più forte.
title: Visualizzazione accordi
uuid: 3f322f58-f8f5-4d91-bdf8-4b5f9d7fb072
exl-id: d712f7b3-de2f-4ca4-a1bf-a2e4d42a084e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# Visualizzazione accordi{#chord-visualization}

{{eol}}

La visualizzazione Chord (Accordi) consente di mostrare sia la proporzione che la correlazione tra le metriche, mostrando accordi più grandi come indicazione di una correlazione più forte.

La visualizzazione Chord (Accordi) consente di visualizzare l’identificazione delle correlazioni tra metriche, consentendoti di aggiungere e valutare facilmente le possibili correlazioni. Offre inoltre un’altra visualizzazione di qualsiasi [Matrice di correlazione](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html). Con la visualizzazione Chord (Corda) non è possibile identificare una correlazione positiva o negativa tra le metriche, ma solo che esiste una correlazione. In alcuni casi, la determinazione di una relazione diretta o inversa può essere identificata applicando metriche di contatore.

1. **Apri **[!UICONTROL Chord]**visualizzazione**.

   Nell’area di lavoro, fai clic con il pulsante destro del mouse su [!DNL Visualization > Predictive Analytics > Chord].

1. **Selezionare un Dimension dal menu**.

   Viene visualizzata una visualizzazione vuota per la selezione di una dimensione. Il nome della dimensione viene visualizzato nella parte superiore della visualizzazione a corda vuota.

   >[!NOTE]
   >
   >Se nell’area di lavoro è già aperta una Matrice di correlazione, puoi anche eseguirne il rendering come visualizzazione Chord.

1. **Scegliere le metriche da correlare**.

   Trascina le metriche dal **[!UICONTROL Finder]** facendo clic su **[!UICONTROL Ctrl-Alt]** per trascinare metriche dalla tabella al grafico. Dopo aver selezionato due o più metriche, il grafico si aggiorna automaticamente e inizia a visualizzare i dati di correlazione. Continua ad aggiungere metriche in base alle esigenze per correlare i punti dati.

   ![](assets/chord_drag_metric.png)

   La visualizzazione Chord (Corda) mostra la proporzione dell’intero rappresentato dall’area di ciascun segmento. Continua ad aggiungere metriche necessarie per identificare e analizzare relazioni significative.

   ![](assets/chord_selected.png)

1. **Visualizzare la visualizzazione Chord**.

   Passa il puntatore del mouse su ciascuna metrica della visualizzazione per vedere le relazioni. Nell’esempio, è possibile visualizzare una correlazione tra Unità e la maggior parte delle altre metriche (ad eccezione della variabile **Durata visita** metrica).

   ![](assets/chord_visualization_1.png)

   Quando passi il puntatore del mouse sopra la **Durata visita** nella visualizzazione Chord (Corda), puoi vedere che esiste una correlazione molto ridotta o al massimo debole tra tutte le altre metriche.

   ![](assets/chord_visualization_2.png)

1. **Modificare le impostazioni.** Fai clic con il pulsante destro del mouse sulla visualizzazione Accordi per aprire un menu per modificare la dimensione, visualizzare le dimensioni come numeri assoluti o come percentuali, rimuovere la metrica selezionata o tutte le metriche, modificare i colori e i dettagli ed esportare i valori in una matrice di correlazione.

   ![](assets/chord_menu.png)
