---
description: Un grafico a dispersione 3D rappresenta gli elementi di una dimensione dati (come Giorni o Sito di riferimento) su una griglia tridimensionale in cui gli assi x, y e z rappresentano diverse metriche.
solution: Analytics
title: 3D Dispersione
topic: Data workbench
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# 3D Dispersione{#d-scatter-plots}

Un grafico a dispersione 3D rappresenta gli elementi di una dimensione dati (come Giorni o Sito di riferimento) su una griglia tridimensionale in cui gli assi x, y e z rappresentano diverse metriche.

Come la [Traccia dispersione 2D](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Scatter_Plots), questa visualizzazione è utile per comprendere la relazione tra un gran numero di elementi disparati che utilizzano metriche diverse.

**Per utilizzare la visualizzazione Dispersione 3D:**

1. Aprite una nuova area di lavoro.

   Dopo aver aperto una nuova area di lavoro, potrebbe essere necessario fare clic su **Aggiungi** > Sblocca **temporaneamente**.
1. Fai clic con il pulsante destro del mouse e seleziona **Visualizzazione** > Dispersione **3D**.

   Viene **[!UICONTROL Dimensions]** visualizzata una lista di menu.

1. Selezionare una dimensione per la query.

   Il grafico a dispersione 3D aprirà le metriche predefinite per tale dimensione.

   ![](assets/3D_main.png)

   Selezionando il **[!UICONTROL Days]** menu viene visualizzato il seguente grafico a dispersione 3D con queste metriche predefinite sugli assi seguenti: **[!UICONTROL x=Visits]**, **[!UICONTROL y=Retention]**, e **[!UICONTROL z=Visits]**.

1. Modificare le metriche. Fare clic con il pulsante destro del mouse sull&#39;etichetta della metrica nell&#39;asse x, y o z e selezionare **[!UICONTROL Change Metric]**. Selezionate quindi una metrica diversa per l’asse selezionato.

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * Trascina una metrica su una delle etichette dei tre assi e rilasciala per modificare l&#39;asse selezionato nella metrica rilasciata.
   >    * Trascina una metrica altrove sulla visualizzazione e rilasciala per modificare la metrica del raggio per quell’asse.
   >    * Trascina una dimensione in un punto qualsiasi della visualizzazione e rilasciala per modificarne la dimensione.


1. Modificate la metrica Raggio. Fare clic con il pulsante destro del mouse sul titolo nella parte superiore della pagina (con titolo dopo la dimensione selezionata) e selezionare **[!UICONTROL Change Radius Metric]**.

   La metrica radius definisce la dimensione del punto tracciato in base alla selezione della metrica. La posizione relativa dei punti non cambia nel grafico a dispersione, ma le dimensioni dei punti tracciati nella visualizzazione aumentano in base al valore della metrica.

   ![](assets/3D_change_radius.png)

1. Utilizzare il **[!UICONTROL Orthographic Camera]**. Questa opzione consente di identificare i punti tracciati in relazione alla loro prospettiva reale in base alla metrica del raggio, per evitare distorsioni tridimensionali.

   Quando viene visualizzata per la prima volta la Trama dispersione 3D, questa viene visualizzata in una proiezione rotante tridimensionale, che causa una distorsione per punti tracciati più vicino alla prospettiva, o &quot;fotocamera&quot; virtuale. (Le trame più vicine alla telecamera appaiono molto più grandi dei punti che ruotano ulteriormente dalla telecamera.)

   Per evitare questa distorsione prospettica, potete selezionare l’ **[!UICONTROL Orthographic Camera]** opzione facendo clic con il pulsante destro del mouse sul titolo e selezionando dal menu. Questo consente di rappresentare gli oggetti tridimensionali in due dimensioni. In questo modo i punti tracciati vengono visualizzati come piani e i punti vengono visualizzati come relativi alla metrica del raggio, riducendo gli offset tridimensionali.

1. Selezionare i punti dal grafico a dispersione.

   * **Per rimuovere un punto o un gruppo di punti**: Fare clic sul punto.
   * **Per aggiungere un altro punto o gruppo di punti alla selezione**: **Ctrl** + **clic** su un punto o **Ctrl** + **trascinamento** su più punti.

   * **Per rimuovere un punto o un gruppo di punti dalla selezione**: **Maiusc** + **clic** su un punto o **Maiusc** + **trascinamento** **** su più punti.

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->

