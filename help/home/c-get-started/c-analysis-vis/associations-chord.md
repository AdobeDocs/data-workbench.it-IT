---
description: La visualizzazione di Association Chord consente di mostrare sia la proporzione che l'associazione tra metriche, dimensioni ed elementi, mostrando accordi più grandi come indicazione di un'associazione più forte.
title: Visualizzazione di Association Chord
uuid: c656ffc8-e45a-44c0-a29b-cdc10dcbd1f2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualizzazione di Association Chord{#association-chord-visualization}

La visualizzazione di Association Chord consente di mostrare sia la proporzione che l&#39;associazione tra metriche, dimensioni ed elementi, mostrando accordi più grandi come indicazione di un&#39;associazione più forte.

La tabella Associations (Associazioni) confronta i valori con il calcolo V di Cramer invece di utilizzare il coefficiente di correlazione di Pearson come utilizzato nelle visualizzazioni [Matrice](/help/home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md) [](/help/home/c-get-started/c-analysis-vis/associations-visualization.md) di correlazione e Correlazione (queste possono solo confrontare le metriche, mentre la tabella di associazione e la corda possono confrontare metriche, dimensioni ed elementi). Il documento Associations Chord fornisce anche un&#39;altra visualizzazione in una tabella [di](../../../home/c-get-started/c-analysis-vis/associations-visualization.md#concept-9d937dda38174875b32095c6eaf22f2f)associazioni creata in precedenza.

**Per creare un accordo di associazione**

1. In un’area di lavoro, fate clic con il pulsante destro del mouse su **Visualization (Visualizzazione) > Predictive Analytics (Analisi predittiva) > Association Chord (Corda associazione)**.

   Viene aperto un menu che consente di selezionare una dimensione estesa dall’elenco.

   ![](assets/association_chord1.png)

   Una volta selezionata questa opzione, la tabella di associazione vuota si aprirà con la dimensione selezionata identificata nel titolo. ![](assets/association_chord2.png)

1. **Seleziona una metrica, una dimensione o un elemento** dimensione.

   Fai clic con il pulsante destro del mouse sulla visualizzazione degli accordi e seleziona **Aggiungi metrica** o **Aggiungi dimensione**. Selezionate le voci dal menu da aggiungere alla corda.

   Puoi anche trascinare metriche e dimensioni dal pannello **[!UICONTROL Finder]** facendo clic **[!UICONTROL Ctrl-Alt]** e trascinando metriche e dimensioni sull&#39;accordo. Oppure trascina gli elementi dimensionali direttamente da una tabella aperta alla visualizzazione degli accordi.

1. **Scegli metriche, dimensioni ed elementi aggiuntivi da associare**.

   Dopo aver selezionato due o più valori, il grafico si aggiorna automaticamente e inizia a visualizzare i dati delle associazioni. Continua ad aggiungere metriche in base alle esigenze per associare punti dati.

   ![](assets/association_chord.png)

   La visualizzazione Chord mostra la proporzione dell’intero rappresentato dall’area di ciascun segmento. Continua ad aggiungere metriche/dimensioni/elementi per identificare e approfondire le relazioni significative.

1. **Visualizzare la visualizzazione** Chord.

   Passa il cursore sopra ogni valore della visualizzazione per vedere le relazioni.

1. **Modifica impostazioni.** Fai clic con il pulsante destro del mouse sulla visualizzazione accordi per aprire un menu per modificare la metrica, la dimensione o gli elementi e visualizzare le dimensioni come numeri assoluti o come percentuali, rimuovere la metrica selezionata o tutte le metriche, modificare colori e dettagli ed esportare i valori in una tabella associazioni.

**Per creare un accordo di associazione da una tabella di associazione:**

1. Apri una visualizzazione **tabella** di associazione.
1. Fate clic con il pulsante destro del mouse e selezionate **Esporta visualizzazione** corda. Viene aperto un diagramma di accordo con i valori selezionati nella tabella di associazione. ![](assets/association_table_to_chord.png)

>[!IMPORTANT]
>
>Se si esporta una tabella di associazione da un diagramma di accordi che contiene almeno una metrica, vengono generati elementi duplicati nelle righe/colonne della tabella di associazione. Per evitare la duplicazione di elementi, create una nuova tabella di associazione e aggiungete gli elementi desiderati, anziché esportare gli elementi da un diagramma di accordo di associazione.

