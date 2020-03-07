---
description: Segui questi passaggi per utilizzare la visualizzazione Punteggio tendenza.
solution: Analytics
title: Impostazione del punteggio tendenza
topic: Data workbench
uuid: afc9aada-3bf9-4ce6-8c43-a955771065b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Impostazione del punteggio tendenza{#setting-up-propensity-scoring}

Segui questi passaggi per utilizzare la visualizzazione Punteggio tendenza.

1. Aprite una nuova area di lavoro e fate clic su **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

   ![](assets/propensity_visualization.png)

1. Impostate la variabile **[!UICONTROL Target]** (la variabile dipendente).

   Impostate la variabile dipendente selezionando:

* **Elementi** dimensione: Fare clic con il pulsante destro del mouse nell&#39;area di lavoro e selezionare **[!UICONTROL Table]**. Quindi seleziona un elemento Dimensione come variabile dipendente.

   O

* **[!UICONTROL Filter Editor]** (Progetto > scarica CSV). Fai clic **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Filter Editor]** per aprire la visualizzazione Editor filtri.

   ![](assets/propensity_visualization_filter_editor.png)

   Dopo aver selezionato un elemento Dimensione o Filtro come variabile dipendente, fate clic su **[!UICONTROL Set Target]**, immettete un nome per descrivere la variabile dipendente. Quindi fate clic **[!UICONTROL OK]** (e accertatevi che la casella del filtro sia evidenziata) per impostare Target.

   ![](assets/propensity_visualization_setTarget.png)

   Il nome assegnato alla destinazione è la variabile dipendente che verrà visualizzata nel riquadro a sinistra.
1. Aggiungere variabili indipendenti.

   Aggiungete le variabili indipendenti utilizzando Metriche o Elementi dimensione.

   ![](assets/propensity_visualization_metrics.png)

* **Metriche**. Dalla barra degli strumenti Propensity Scoring (Punteggio tendenza), selezionate una metrica dal **[!UICONTROL Metrics]** menu.

* **Elementi** dimensione: Fare clic con il pulsante destro del mouse nell&#39;area di lavoro e selezionare **[!UICONTROL Table]**. Seleziona uno o più elementi Dimensione e trascina sulla colonna sinistra sotto **[!UICONTROL Independent Variables]** o alla **[!UICONTROL Element]** casella utilizzando i tasti `<Ctrl>` + `<Alt>` .

1. Set **[!UICONTROL Training Filter]**. Per definire il set di visitatori da valutare, fai clic su **[!UICONTROL Options]** > **[!UICONTROL Set Training Filter]** nella barra degli strumenti Propensity Scoring (Punteggio tendenza). Questo fornisce un sottoinsieme di dati generati utilizzando solo i visitatori che si desidera segnare. Ad esempio, che ha visitato l&#39;ultimo mese, i visitatori che risiedono in Australia o i visitatori che hanno visualizzato prodotti specifici.

   Il filtro predefinito è **[!UICONTROL Train on Everyone]**, ma potete modificarlo attivando **[!UICONTROL Dimension Elements]** in una tabella o creando un filtro utilizzando il **[!UICONTROL Filter Editor]**.

   Dopo aver selezionato un elemento Dimensione o creato un filtro e mentre è attivato, fate clic su **Opzioni** > **Imposta filtro** formazione, immettete un nome per descrivere il filtro, quindi fate clic su **[!UICONTROL OK]**.
1. Una volta identificati tutti gli input, premere **[!UICONTROL Go]**.

   ![](assets/propensity_visualization_GO.png)

   Il processo di assegnazione del punteggio inizierà passando i dati più volte. I risultati verranno quindi visualizzati come grafici a barre su una linea percentuale.
1. Salva punteggio tendenza.

   A partire dalla versione 6.1, ora è disponibile un&#39;opzione per l&#39;opzione Salva punteggio tendenza:

* Dimensione
* Dimensioni e metrica

   È possibile ottenere due file salvati, sia una dimensione che una metrica definita.

   >[!NOTE]
   >
   >Se si invia il Propensity Score (Punteggio tendenza) per l&#39;elaborazione, si otterrà solo una dimensione.

   La metrica derivata è la metrica punteggio medio associata.
1. Verifica la precisione.

   Al termine del processo, il sistema visualizzerà **[!UICONTROL Model Complete]** e genererà un modello di punteggio.

   Facendo clic con il pulsante destro del mouse su **[!UICONTROL Model Complete]** verrà identificata la precisione del modello di punteggio definito dal sistema. Valori compresi tra 0% e 100% identificano la probabilità che i visitatori corrispondano alla **[!UICONTROL Target]** variabile.

   La matrice Confusione fornisce quattro conteggi per combinazione di Effettivo positivo (AP), Negativo effettivo (AN), Predicato positivo (PP) e Predicato negativo (PN). Questi numeri si ottengono applicando il modello di punteggio ottenuto al 20% di dati di test rifiutati di cui conosciamo la vera risposta. Se il punteggio è maggiore del 50%, viene previsto come un caso positivo (corrispondente all&#39;evento definito).

   ![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"><b> Precisione</b> </td> 
   <td colname="col2"> Indica la precisione del modello identificando le previsioni corrette su tutte le previsioni. <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Richiama</b> </td> 
   <td colname="col2"> Identifica la capacità di identificare nuovamente il modello di punteggio. <p><b>TP / (TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Precisione</b> </td> 
   <td colname="col2">Identifica il livello di discrepanza. <p>TP / (TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Aprite un [grafico](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a)di incremento o guadagno o il visualizzatore [](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-9f2593a8218140b7bd132a4c74e159f9)modelli.

   Fare clic con il pulsante destro del mouse sulla visualizzazione **Modello completo** e selezionare **[!UICONTROL Lift Chart]**, **[!UICONTROL Gain Chart]** oppure **[!UICONTROL Model Viewer.]**
