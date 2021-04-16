---
description: Segui questi passaggi per utilizzare la visualizzazione Punteggio tendenza .
title: Impostazione del punteggio tendenza
uuid: afc9aada-3bf9-4ce6-8c43-a955771065b4
exl-id: e16a7062-636e-44a9-a07d-343d48bf1b4c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# Impostazione del punteggio tendenza{#setting-up-propensity-scoring}

Segui questi passaggi per utilizzare la visualizzazione Punteggio tendenza .

1. Apri una nuova area di lavoro e fai clic su **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

   ![](assets/propensity_visualization.png)

1. Imposta la variabile **[!UICONTROL Target]** (la variabile dipendente).

   Imposta la variabile dipendente selezionando:

* **Elementi** Dimension: Fai clic con il pulsante destro del mouse nell’area di lavoro e seleziona  **[!UICONTROL Table]**. Quindi seleziona un elemento di Dimension come variabile dipendente.

   O

* **[!UICONTROL Filter Editor]**. Fai clic su **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Filter Editor]** per aprire la visualizzazione Editor filtro.

   ![](assets/propensity_visualization_filter_editor.png)

   Dopo aver selezionato un elemento di Dimension o Filtro come variabile dipendente, fare clic su **[!UICONTROL Set Target]**, immettere un nome per descrivere la variabile dipendente. Quindi fai clic su **[!UICONTROL OK]** (e assicurati che la casella del filtro sia evidenziata) per impostare Target.

   ![](assets/propensity_visualization_setTarget.png)

   Il nome assegnato alla destinazione è la variabile dipendente che verrà visualizzata nel riquadro a sinistra.
1. Aggiungi variabili indipendenti.

   Aggiungi le variabili indipendenti utilizzando Metriche o Elementi Dimension.

   ![](assets/propensity_visualization_metrics.png)

* **Metriche**. Dalla barra degli strumenti Punteggio tendenza , seleziona una metrica dal menu **[!UICONTROL Metrics]** .

* **Elementi** Dimension: Fai clic con il pulsante destro del mouse nell’area di lavoro e seleziona  **[!UICONTROL Table]**. Seleziona uno o più elementi del Dimension e trascina sulla colonna a sinistra sotto **[!UICONTROL Independent Variables]** o nella casella **[!UICONTROL Element]** utilizzando i tasti `<Ctrl>` + `<Alt>`.

1. Imposta **[!UICONTROL Training Filter]**. Puoi definire il set di visitatori che desideri valutare facendo clic su **[!UICONTROL Options]** > **[!UICONTROL Set Training Filter]** nella barra degli strumenti Propensity Scoring (Punteggio tendenza). Questo fornirà un sottoinsieme di dati generati utilizzando solo i visitatori che desideri valutare. Ad esempio, chi ha visitato l’ultimo mese, i visitatori che risiedono in Australia o i visitatori che hanno visualizzato prodotti specifici.

   Il filtro predefinito è **[!UICONTROL Train on Everyone]**, ma puoi modificarlo attivando **[!UICONTROL Dimension Elements]** in una tabella o creando un filtro utilizzando **[!UICONTROL Filter Editor]**.

   Dopo aver selezionato un elemento di Dimension o creato un filtro e durante l&#39;attivazione, fare clic su **Opzioni** > **Imposta filtro di formazione**, immettere un nome per descrivere il filtro, quindi fare clic su **[!UICONTROL OK]**.
1. Una volta identificati tutti gli input, premere **[!UICONTROL Go]**.

   ![](assets/propensity_visualization_GO.png)

   Il processo di valutazione inizierà passando i dati più volte. I risultati verranno quindi visualizzati come grafici a barre su una linea percentuale.
1. Salva punteggio tendenza.

   A partire dalla versione 6.1, ora è disponibile un’opzione quando si utilizza il punteggio tendenza per il salvataggio:

* Dimensione
* Dimension e metrica

   Puoi ottenere due file salvati, sia una dimensione che una metrica definita.

   >[!NOTE]
   >
   >Se invii il Punteggio tendenza per l’elaborazione, otterrai solo una dimensione.

   La metrica derivata è la metrica del punteggio medio associata.
1. Verifica la precisione.

   Il sistema visualizza **[!UICONTROL Model Complete]** e genera un modello di punteggio al termine del processo.

   Fai clic con il pulsante destro del mouse su **[!UICONTROL Model Complete]** per identificare la precisione del modello di punteggio come definito dal sistema. Valori compresi tra lo 0% e il 100% identificano la probabilità che i visitatori corrispondano alla variabile **[!UICONTROL Target]**.

   La matrice di confusione fornisce quattro conteggi per combinazione di Positivo Effettivo (AP), Negativo Effettivo (AN), Positivo Previsto (PP) e Negativo Predetto (PN). Questi numeri si ottengono applicando il modello di punteggio ottenuto al 20% dei dati di test trattenuti di cui conosciamo la vera risposta. Se il punteggio è maggiore del 50%, viene previsto come caso positivo (corrispondente all’evento definito).

   ![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"><b> Precisione</b> </td> 
   <td colname="col2"> Indica la precisione del modello identificando le previsioni corrette su tutte le previsioni. <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Richiama</b> </td> 
   <td colname="col2"> Identifica la possibilità di reidentificare il modello di punteggio. <p><b>TP / (TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Precisione</b> </td> 
   <td colname="col2">Identifica il livello di discrepanza. <p>TP / (TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Apri un [Grafico di incremento o guadagno](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a) o un [Visualizzatore modelli](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-9f2593a8218140b7bd132a4c74e159f9).

   Fai clic con il pulsante destro del mouse sulla visualizzazione **Modello completo** e seleziona **[!UICONTROL Lift Chart]**, **[!UICONTROL Gain Chart]** o **[!UICONTROL Model Viewer.]**
