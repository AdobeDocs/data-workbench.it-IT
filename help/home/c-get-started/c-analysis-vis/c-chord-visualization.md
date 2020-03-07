---
description: La visualizzazione Chord consente di mostrare sia la proporzione che la correlazione tra le metriche, mostrando accordi più grandi come indicazione di una correlazione più forte.
title: Visualizzazione accordi
uuid: 3f322f58-f8f5-4d91-bdf8-4b5f9d7fb072
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Visualizzazione accordi{#chord-visualization}

La visualizzazione Chord consente di mostrare sia la proporzione che la correlazione tra le metriche, mostrando accordi più grandi come indicazione di una correlazione più forte.

La visualizzazione Chord consente di identificare le correlazioni tra metriche, consentendo di aggiungere e valutare facilmente possibili correlazioni. Fornisce inoltre un&#39;altra visualizzazione di qualsiasi matrice [di](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html)correlazione creata in precedenza. Utilizzando la visualizzazione Chord, non è possibile identificare una correlazione positiva o negativa tra le metriche, ma solo che esiste una correlazione. In alcuni casi, la determinazione di una relazione diretta o inversa può essere identificata applicando metriche di contatore.

1. **Apri la **[!UICONTROL Chord]**visualizzazione**.

   Nell’area di lavoro, fate clic con il pulsante destro del mouse [!DNL Visualization > Predictive Analytics > Chord].

1. **Selezionate una dimensione dal menu**.

   Viene aperta una visualizzazione vuota che consente di selezionare una dimensione. Il nome della dimensione viene visualizzato nella parte superiore della visualizzazione a corda vuota.

   >[!NOTE]
   >
   >Se nell’area di lavoro è già aperta una matrice di correlazione, potete eseguirne il rendering come visualizzazione Chord.

1. **Scegliete le metriche da correlare**.

   Trascina le metriche dalla tabella **[!UICONTROL Finder]** facendo clic **[!UICONTROL Ctrl-Alt]** per trascinare le metriche dalla tabella al grafico. Dopo aver selezionato due o più metriche, il grafico si aggiorna automaticamente e inizia a visualizzare i dati di correlazione. Continua ad aggiungere metriche in base alle esigenze per correlare i punti dati.

   ![](assets/chord_drag_metric.png)

   La visualizzazione Chord mostra la proporzione dell’intero rappresentato dall’area di ciascun segmento. Continua ad aggiungere le metriche necessarie per identificare e analizzare relazioni significative.

   ![](assets/chord_selected.png)

1. **Visualizzare la visualizzazione** Chord.

   Passa il cursore sopra ogni metrica nella visualizzazione per vedere le relazioni. Nell&#39;esempio, puoi vedere una correlazione tra le unità e la maggior parte delle altre metriche (ad eccezione della metrica Durata **** visita).

   ![](assets/chord_visualization_1.png)

   Quando passi il cursore del mouse sulla metrica Durata **** visita nella visualizzazione Chord, puoi vedere che esiste una correlazione minima o minima tra tutte le altre metriche.

   ![](assets/chord_visualization_2.png)

1. **Modifica impostazioni.** Fai clic con il pulsante destro del mouse sulla visualizzazione Chord per aprire un menu per modificare la dimensione, visualizzare le dimensioni come numeri assoluti o come percentuali, rimuovere la metrica selezionata o tutte le metriche, modificare colori e dettagli ed esportare i valori in una matrice di correlazione.

   ![](assets/chord_menu.png)

