---
description: La visualizzazione Tabella associazione consente di associare metriche, dimensioni ed elementi dimensione utilizzando l'algoritmo V di Cramer.
title: Visualizzazione tabella di associazione
uuid: 4563c336-3377-4929-8694-8c0d00866825
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Visualizzazione tabella di associazione{#association-table-visualization}

La visualizzazione Tabella associazione consente di associare metriche, dimensioni ed elementi dimensione utilizzando l&#39;algoritmo V di Cramer.

La tabella di associazione confronta i valori con il calcolo V di Cramer anziché utilizzare il coefficiente di correlazione di Pearson come utilizzato nelle visualizzazioni Matrice [di](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html) correlazione e Correlazione [(queste possono solo confrontare le metriche, mentre la tabella di associazione e il cordo](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html) di [](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445) associazione possono confrontare metriche, dimensioni ed elementi).

## Creazione di una tabella di associazione {#section-87ed12ccc1af4196a1b6534e621c4cbb}

La tabella di associazione confronta le metriche su una dimensione numerabile o non calcolabile. La tabella può essere modificata per evidenziare le associazioni all’interno della visualizzazione mediante la selezione del colore o per renderla una mappa di testo, una mappa di calore o entrambe.

1. Aprite una tabella di associazione.

   Right-click [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table].

   ![](assets/association_table.png)

1. Seleziona una dimensione estesa: ClickThrough, Hit, Product, Visit o Visitor. Viene aperta una tabella di associazione con la dimensione estesa identificata nell&#39;angolo e la metrica associata inserita sia nella riga che nella colonna.

   ![](assets/association_table1.png)

   La tabella Associations (Associazioni) utilizza il V di Cramer come correlazione simmetrica, generando metriche, dimensioni ed elementi selezionati che si riflettono sia nelle colonne che nelle righe di una tabella Association. Ad esempio, se selezionate la dimensione estesa del **prodotto** , la metrica viene usata come metrica **[!UICONTROL Visits]** associata sia nella riga che nella colonna della tabella, generando un confronto perfetto ma inutile (1,00) perché i valori confrontati sono identici.

1. Aggiungete altri valori alla tabella di associazione.

   Fare clic con il pulsante destro del mouse in una colonna o riga e selezionare **Aggiungi metrica** o **Aggiungi dimensione**. Puoi anche trascinare metriche e dimensioni da un pannello **Finder** . È inoltre possibile trascinare gli elementi dimensione da una tabella aperta alla visualizzazione tabella.

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >Nella tabella di associazione è consentito un limite di dieci righe e colonne.

