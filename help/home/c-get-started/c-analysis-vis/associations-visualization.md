---
description: La visualizzazione Tabella associazioni consente di associare metriche, dimensioni ed elementi dimensionali utilizzando l’algoritmo V di Cramer.
title: Visualizzazione di Associations Table (Tabella associazioni)
uuid: 4563c336-3377-4929-8694-8c0d00866825
exl-id: 3fc2c025-d369-45ed-8c9e-eb4a0ac412b7
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# Visualizzazione di Associations Table (Tabella associazioni){#association-table-visualization}

La visualizzazione Tabella associazioni consente di associare metriche, dimensioni ed elementi dimensionali utilizzando l’algoritmo V di Cramer.

La tabella delle associazioni confronta i valori con il calcolo del V di Cramer anziché utilizzare il coefficiente di correlazione di Pearson come utilizzato nelle visualizzazioni [Matrice di correlazione](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html) e [Correlazione corda](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html) (queste possono solo confrontare le metriche, mentre la tabella delle associazioni e [Accordi di associazione](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445) possono confrontare metriche, dimensioni ed elementi).

## Creare una tabella di associazione {#section-87ed12ccc1af4196a1b6534e621c4cbb}

La tabella delle associazioni confronta le metriche su una dimensione conteggiata o non numerabile. È possibile modificare la tabella per evidenziare le associazioni all’interno della visualizzazione mediante la selezione del colore o per renderla come mappa di testo, mappa di calore o entrambe.

1. Aprire una tabella di associazione.

   Fai clic con il pulsante destro del mouse su [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table].

   ![](assets/association_table.png)

1. Seleziona una dimensione estesa: Clickthrough, Hit, Prodotto, Visita o Visitatore. Viene aperta una tabella di associazione con la dimensione estesa identificata nell’angolo e la metrica associata posizionata sia nella riga che nella colonna.

   ![](assets/association_table1.png)

   La tabella delle associazioni utilizza il V di Cramer come correlazione simmetrica, con conseguente visualizzazione di metriche, dimensioni ed elementi selezionati che si riflettono sia nelle colonne che nelle righe di una tabella delle associazioni. Ad esempio, selezionando la dimensione estesa **Prodotto** , la metrica **[!UICONTROL Visits]** viene utilizzata come metrica associata sia nella riga che nella colonna della tabella, con conseguente confronto perfetto ma inutile (1.00), in quanto i valori confrontati sono identici.

1. Aggiungi altri valori alla tabella di associazione.

   Fai clic con il pulsante destro del mouse su una colonna o una riga e seleziona **Aggiungi metrica** o **Aggiungi Dimension**. Puoi anche trascinare metriche e dimensioni da un pannello **Finder**. È inoltre possibile trascinare gli elementi di Dimension da una tabella aperta alla visualizzazione tabella.

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >Nella tabella delle associazioni è consentito un limite di dieci righe e colonne.
