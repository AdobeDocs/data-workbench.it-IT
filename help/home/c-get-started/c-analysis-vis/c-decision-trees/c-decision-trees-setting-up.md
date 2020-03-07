---
description: Imposta una struttura decisionale identificando un caso positivo e aggiungendo metriche e dati di input per valutare i dati ed esplorare la struttura decisionale.
title: Creazione di una struttura decisionale
uuid: 5790d322-5460-444d-95d8-a06696f9a55f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creazione di una struttura decisionale{#building-a-decision-tree}

Imposta una struttura decisionale identificando un caso positivo e aggiungendo metriche e dati di input per valutare i dati ed esplorare la struttura decisionale.

Per creare una struttura decisionale, eseguire le operazioni riportate di seguito.

1. Aprite una nuova area di lavoro.

   Dopo aver aperto una nuova area di lavoro, potrebbe essere necessario fare clic su **Aggiungi** > Sblocca **** temporaneamente.

1. Per aprire il Generatore albero decisionale, fare clic con il pulsante destro del mouse **[!UICONTROL Visualization]** > **Predictive Analytics** > **Classification** > **Decision Tree Builder**.

1. Impostate un caso **** positivo.

   È possibile definire un caso positivo per una struttura decisionale selezionando dimensioni in un Finder o elementi dimensione in una tabella oppure progettando un filtro nel filtro di progettazione. In realtà, il caso positivo può essere una combinazione di selezioni multiple nell&#39;area di lavoro, inclusi filtri, dimensioni, elementi e tutti i tipi di valori di visualizzazione Workbench dati.

   * **Progettare e applicare un filtro** come caso positivo. Fare clic con il pulsante destro del mouse nell&#39;area di lavoro e selezionare **[!UICONTROL Tools]** > **[!UICONTROL Filter Editor]** per progettare e applicare un filtro.

   * Aggiungi **dimensioni** come caso positivo. Nell’area di lavoro, fare clic con il pulsante destro del mouse e selezionare **Strumenti** > **Finder** (oppure selezionare **[!UICONTROL Add]** > **[!UICONTROL Finders]** nel riquadro a sinistra). Digitare un nome di dimensione nel campo **Ricerca** , quindi selezionare una dimensione.

   * Aggiungi **metriche** come caso positivo. Fai clic con il pulsante destro del mouse e seleziona **Strumenti** > **Finder** oppure seleziona **[!UICONTROL Add]** > **[!UICONTROL Finders]** nel riquadro a sinistra per aprire una tabella Metriche. Seleziona una metrica come caso positivo.

   * Aggiungi elementi **di** quota come caso positivo. Fai clic con il pulsante destro del mouse nell’area di lavoro e seleziona **[!UICONTROL Table]** per aprire gli elementi dimensionali, quindi seleziona uno degli elementi dimensionali per impostare il caso positivo.

1. Fai clic su **[!UICONTROL Options]** > **[!UICONTROL Set Positive Case]**.

   Questo imposta il caso positivo e consente di denominarlo. Il nome verrà visualizzato sotto l’ **[!UICONTROL Positive Case]** intestazione nell’area di lavoro.

   >[!NOTE]
   >
   >Quando si imposta il caso positivo, l&#39;albero decisionale utilizza la selezione dell&#39;area di lavoro corrente, che può essere definita come Visitatori (o qualsiasi altro elemento contabile di primo livello definito, ma nella maggior parte dei casi Visitatori) che corrispondono alla selezione corrente all&#39;interno dell&#39;area di lavoro. Questi vengono combinati come un singolo filtro per un singolo caso positivo (non più casi positivi).

   Facendo clic **[!UICONTROL Set Positive Case]** quando non è presente alcuna selezione, il caso positivo viene cancellato.

1. (facoltativo) Selezionate **[!UICONTROL Set Population Filters]** per definire la popolazione di visitatori da classificare.

   Se non viene applicato alcun filtro per la popolazione, il set di formazione viene disegnato da tutti i visitatori (il valore predefinito è &quot;Tutti&quot;).

   >[!NOTE]
   >
   >Fate clic su per **[!UICONTROL Show Complex Filter Description]** visualizzare gli script di filtraggio per il filtro maiuscole/minuscole e la popolazione.

1. Aggiungi **metriche**, **dimensioni** ed elementi **** dimensione come input.

   È possibile selezionare gli input trascinandoli dai pannelli del Finder o dalle tabelle per i singoli elementi dimensionali. È inoltre possibile selezionare il **[!UICONTROL Metrics]** menu nella barra degli strumenti.

   * Aggiungi **metriche** come input.

      Selezionate Metriche dalla barra degli strumenti. Premere **Ctrl** + **Alt** per trascinare una o più metriche nel Generatore albero decisionale.

      La metrica verrà visualizzata nell&#39;elenco **** Input (Metriche) come input con una codifica colore univoca.

      ![](assets/decision_tree_add_Metrics_inputs.png)

   * Aggiungi **dimensioni** come input.

      Nell’area di lavoro, fare clic con il pulsante destro del mouse e selezionare **Strumenti** > **Finder** , quindi digitare il nome della dimensione nel campo **Ricerca** . Premere **Ctrl** + **Alt**, selezionare una quota e trascinare la quota nel Generatore albero decisionale.

      La dimensione verrà visualizzata nell&#39;elenco **Input (Dimensioni)** con una codifica colore univoca.

   * Aggiungi elementi **di** quota come input.

      Nell’area di lavoro, fare clic con il pulsante destro del mouse e selezionare una tabella Dimensioni. Selezionare Elementi dimensione, premere **Ctrl** + **Alt** e trascinare gli elementi selezionati nel Generatore albero decisionale.

      Gli elementi dimensionali verranno visualizzati nell&#39;elenco **Input (Elements)** con una codifica colore univoca.
   >[!IMPORTANT]
   >
   >È possibile selezionare fino a un massimo di quattordici input da valutare. Se vengono aggiunti troppi input, viene visualizzato un messaggio di errore.

1. Selezionate **[!UICONTROL Go]** dalla barra degli strumenti.

   La struttura decisionale si svilupperà in base alle dimensioni e alle metriche selezionate. Metriche semplici, come le aggiunte di carrello, si svilupperanno rapidamente, mentre dimensioni complesse, come la durata della visita con più punti dati, si svilupperanno più lentamente con una percentuale del completamento visualizzata durante la conversione. La mappa ad albero viene quindi troncata e aperta per l&#39;interazione con l&#39;utente. Gli input di metrica e dimensione saranno codificati in base al colore in base ai nomi dei nodi.

   ![](assets/decision_tree_builder.png)

   Il nodo foglia viene visualizzato come verde (true) o rosso (false) se la struttura è stata troncata e se è presente una previsione di **True** o **False** dopo i rami troncati.

   >[!NOTE]
   >
   >L’esempio di formazione viene estratto dal set di dati da utilizzare per il generatore ad albero. Workbench dati utilizza l&#39;80% del campione per creare la struttura ad albero e il restante 20% per valutare la precisione del modello ad albero.

1. Verificare la precisione utilizzando l&#39; **[!UICONTROL Confusion Matrix]**.

   Fate clic **[!UICONTROL Options]** > **[!UICONTROL Confusion Matrix]** per visualizzare i valori Precisione, Richiama, Precisione e Punteggio F. Più vicino al 100%, migliore sarà il punteggio.

   La Matrice di Confusione fornisce quattro conteggi di precisione del modello utilizzando una combinazione di valori:

   * Positivo effettivo (AP)
   * Previsto positivo (PP)
   * Negativo effettivo (AN)
   * Predicted Negative (PN)
   >[!TIP]
   >
   >Questi numeri si ottengono applicando il modello di punteggio ottenuto dei dati di test del 20% conservati e già noti come risposta vera. Se il punteggio è maggiore del 50%, viene previsto come caso positivo (che corrisponde al filtro definito). Precisione = (TP + TN)/(TP + FP + TN + FN), Recall = TP / (TP + FN) e Precision = TP / (TP + FP).

1. **Esplora la struttura** decisionale.

   Dopo aver generato una struttura decisionale, potete visualizzare il percorso della previsione e identificare tutti i visitatori che soddisfano i criteri definiti. La struttura ad albero identifica la divisione di input per ciascun ramo in base alla posizione e alla codifica del colore. Ad esempio, se si seleziona il nodo Dominio di riferimento, i nodi che conducono a tale divisione sono elencati dal codice colore a sinistra della struttura.

   È possibile selezionare i nodi foglia per selezionare i rami (set di regole) della struttura decisionale.

   Per questo esempio: Se la durata della visita è inferiore a 1, non esiste alcuna campagna, esiste almeno una visualizzazione di pagina, non esistono registrazioni e-mail e vi è stata almeno una visita. Le proiezioni relative a questo criterio di riunione e l&#39;ordine sono del **94,73** %.

   ![](assets/decision_tree_explore.png)

   **Interazione** albero decisionale: È possibile selezionare più nodi nella struttura utilizzando il **Ctrl+clic** standard per aggiungere, oppure **Maiusc+clic** per eliminarli.

   **Nodi** codificati a colori: Il colore dei nodi corrisponde al colore delle dimensioni e delle metriche di input assegnato da Workbench dati.

   I nodi verdi e rossi chiari a livello di foglia di un ramo stampato prevedono che il nodo sia True o False.

   | ![](assets/decision_tree_node_true.png) Verde brillante | Identifica che il nodo è uguale a true e che tutte le condizioni sono soddisfatte. |
   |---|---|
   | ![](assets/decision_tree_node_false.png) Rosso vivo | Identifica che il nodo è uguale a false e non tutte le condizioni sono soddisfatte. |

1. **Salvare la struttura** decisionale.

   È possibile salvare la struttura decisionale in diversi formati:

   ![](assets/decison_tree_save.png)

   * Predictive Markup Language (**PMML**), un formato di file basato su XML utilizzato dalle applicazioni per descrivere e scambiare modelli di struttura decisionale.
   * **Testo** che visualizza colonne e righe semplici con valori vero o falso, percentuali, numero di membri e valori di input.
   * Una **dimensione** con rami corrispondenti agli elementi di risultato previsti.

