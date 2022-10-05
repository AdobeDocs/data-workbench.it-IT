---
description: Un grafico a dispersione 3D rappresenta gli elementi di una dimensione dati (ad esempio Giorni o Sito di riferimento) in una griglia tridimensionale in cui gli assi x, y e z rappresentano diverse metriche.
title: Dispersioni 3D
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
exl-id: 18f18cab-a31b-4ffe-89c5-412a5645af2e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 1%

---

# Dispersioni 3D{#d-scatter-plots}

{{eol}}

Un grafico a dispersione 3D rappresenta gli elementi di una dimensione dati (ad esempio Giorni o Sito di riferimento) in una griglia tridimensionale in cui gli assi x, y e z rappresentano diverse metriche.

Come il [Dispersione 2D](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Scatter_Plots), questa visualizzazione è utile quando si cerca di comprendere il rapporto tra un numero elevato di elementi diversi utilizzando metriche diverse.

**Per utilizzare la visualizzazione Dispersione 3D:**

1. Apri una nuova area di lavoro.

   Dopo aver aperto una nuova area di lavoro, potrebbe essere necessario fare clic su **Aggiungi** > **Sblocca temporaneamente**.
1. Fai clic con il pulsante destro del mouse e seleziona **Visualizzazione** > **Dispersione 3D**.

   Elenco di menu **[!UICONTROL Dimensions]** si aprirà.

1. Seleziona una dimensione per la query.

   Il grafico a dispersione 3D aprirà le metriche predefinite per quella dimensione.

   ![](assets/3D_main.png)

   Selezione della **[!UICONTROL Days]** visualizza il seguente grafico a dispersione 3D con queste metriche predefinite sui seguenti assi: **[!UICONTROL x=Visits]**, **[!UICONTROL y=Retention]** e **[!UICONTROL z=Visits]**.

1. Modificare le metriche. Fai clic con il pulsante destro del mouse sull’etichetta della metrica nell’asse x, y o z e seleziona **[!UICONTROL Change Metric]**. Quindi selezionate una metrica diversa per l’asse selezionato.

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * Trascina una metrica su una delle etichette dei tre assi e rilasciala per modificare l’asse selezionato nella metrica rilasciata.
   >    * Trascina una metrica in un altro punto della visualizzazione e rilasciala per modificare la metrica del raggio per quell’asse.
   >    * Trascina una dimensione in un punto qualsiasi della visualizzazione e rilasciala per modificarne la dimensione.


1. Modificate la metrica Raggio. Fai clic con il pulsante destro del mouse sul titolo nella parte superiore della pagina (con titolo dopo la dimensione selezionata) e seleziona **[!UICONTROL Change Radius Metric]**.

   La metrica raggio definisce le dimensioni del punto tracciato in base alla selezione metrica. La posizione relativa dei punti non cambia nel grafico a dispersione, ma le dimensioni dei punti tracciati all’interno della visualizzazione aumentano in base al valore della metrica.

   ![](assets/3D_change_radius.png)

1. Implementare **[!UICONTROL Orthographic Camera]**. Questa opzione consente di identificare i punti tracciati in relazione alla loro prospettiva effettiva in base alla metrica del raggio per evitare distorsioni tridimensionali.

   Quando il Dispersione 3D viene visualizzato per la prima volta, viene visualizzato in una proiezione rotante tridimensionale, che causa qualche distorsione per i punti più vicini alla prospettiva, o una &quot;telecamera&quot; virtuale. (I grafici più vicini alla telecamera appaiono molto più grandi dei punti che ruotano più lontano dalla telecamera.)

   Per evitare questa distorsione prospettica, è possibile selezionare la **[!UICONTROL Orthographic Camera]** facendo clic con il pulsante destro del mouse sul titolo e selezionando dal menu. Questo consente di rappresentare gli oggetti tridimensionali in due dimensioni. In questo modo i punti tracciati vengono resi piatti e i punti vengono visualizzati come relativi alla metrica del raggio, riducendo gli offset tridimensionali.

1. Selezionare i punti dal grafico a dispersione.

   * **Per rimuovere un punto o un gruppo di punti**: Fai clic sul punto.
   * **Per aggiungere un altro punto o gruppo di punti alla selezione**: **Ctrl** + **click** un punto o **Ctrl** + **trascinare** su più punti.

   * **Per rimuovere un punto o un gruppo di punti dalla selezione**: **Maiusc** + **click** un punto o **Maiusc** **+** **trascinare** su diversi punti.

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->
