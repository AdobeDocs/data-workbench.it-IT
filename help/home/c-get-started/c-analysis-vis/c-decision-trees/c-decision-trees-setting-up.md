---
description: Imposta un albero delle decisioni identificando un caso positivo e aggiungendo metriche e input di dimensioni per valutare i dati ed esplorare la struttura decisionale.
title: Creazione di un albero delle decisioni
uuid: 5790d322-5460-444d-95d8-a06696f9a55f
exl-id: 06db9e77-72ea-44c7-8451-d3f195acd196
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 0%

---

# Creazione di un albero delle decisioni{#building-a-decision-tree}

{{eol}}

Imposta un albero delle decisioni identificando un caso positivo e aggiungendo metriche e input di dimensioni per valutare i dati ed esplorare la struttura decisionale.

Segui questi passaggi per creare un albero decisionale.

1. Apri una nuova area di lavoro.

   Dopo aver aperto una nuova area di lavoro, potrebbe essere necessario fare clic su **Aggiungi** > **Sblocca temporaneamente**.

1. Per aprire il Generatore albero delle decisioni, fai clic con il pulsante destro del mouse su **[!UICONTROL Visualization]** > **Analisi predittiva** > **Classificazione** > **Generatore di alberi decisionali**.

1. Imposta un **Caso positivo**.

   È possibile definire un caso positivo per una struttura decisionale selezionando le dimensioni in un Finder o gli elementi dimensionali in una tabella oppure progettando un filtro nel filtro di progettazione. In realtà, il caso positivo può essere una combinazione di selezioni multiple nell&#39;area di lavoro tra cui filtri, dimensioni, elementi e tutti i tipi di valori di visualizzazione Data Workbench.

   * **Progettazione e applicazione di un filtro** come caso positivo. Fai clic con il pulsante destro del mouse nell’area di lavoro e seleziona **[!UICONTROL Tools]** > **[!UICONTROL Filter Editor]** per progettare e applicare un filtro.

   * Aggiungi **Dimension** come caso positivo. Nell’area di lavoro, fai clic con il pulsante destro del mouse e seleziona **Strumenti** > **Finder** o seleziona **[!UICONTROL Add]** > **[!UICONTROL Finders]** nel riquadro a sinistra). Digita un nome di dimensione nel **Ricerca** quindi seleziona una dimensione.

   * Aggiungi **Metriche** come caso positivo. Fai clic con il pulsante destro del mouse e seleziona **Strumenti** > **Finder** o seleziona **[!UICONTROL Add]** > **[!UICONTROL Finders]** nel riquadro a sinistra per aprire una tabella Metriche. Seleziona una metrica come caso positivo.

   * Aggiungi **Elementi Dimension** come caso positivo. Fai clic con il pulsante destro del mouse nell’area di lavoro e seleziona **[!UICONTROL Table]** per aprire gli elementi dimensionali, seleziona dagli elementi dimensionali per impostare il caso positivo.

1. Fai clic su **[!UICONTROL Options]** > **[!UICONTROL Set Positive Case]**.

   Questo imposta il caso positivo e consente di denominarlo. Il nome verrà visualizzato sotto la **[!UICONTROL Positive Case]** nell’area di lavoro.

   >[!NOTE]
   >
   >Quando si imposta il caso positivo, l&#39;albero delle decisioni utilizza la selezione dell&#39;area di lavoro corrente, che può essere definita come Visitatori (o qualsiasi altro valore contabile di livello superiore definito, ma nella maggior parte dei casi Visitatori) che corrispondono alla selezione corrente all&#39;interno dell&#39;area di lavoro. Questi si combinano come un unico filtro per un singolo caso positivo (non più casi positivi).

   Clic **[!UICONTROL Set Positive Case]** quando non vi è alcuna selezione, il caso positivo viene cancellato.

1. (facoltativo) Seleziona **[!UICONTROL Set Population Filters]** per definire la popolazione del visitatore da classificare.

   Se non viene applicato alcun filtro per la popolazione, il set di formazione viene tratto da tutti i visitatori (l’impostazione predefinita è &quot;Tutti&quot;).

   >[!NOTE]
   >
   >Fai clic sul pulsante **[!UICONTROL Show Complex Filter Description]** per visualizzare gli script di filtro per il filtro Case positivo e Population Filter.

1. Aggiungi **Metriche**, **Dimension** e **Elementi Dimension** come input.

   È possibile selezionare gli input trascinandoli dai pannelli del Finder o dalle tabelle per i singoli elementi dimensionali. Puoi anche selezionare tra le **[!UICONTROL Metrics]** nella barra degli strumenti.

   * Aggiungi **Metriche** come input.

      Seleziona Metriche dalla barra degli strumenti. Press **Ctrl** + **Alt** per trascinare una o più metriche nel Generatore albero delle decisioni.

      La metrica verrà visualizzata nella **Elenco Input (Metriche)** come input con codifica a colori univoca.

      ![](assets/decision_tree_add_Metrics_inputs.png)

   * Aggiungi **Dimension** come input.

      Nell’area di lavoro, fai clic con il pulsante destro del mouse e seleziona **Strumenti** > **Finder** e digita il nome della dimensione nel **Ricerca** campo . Press **Ctrl** + **Alt**, selezionate una quota e trascinatela nel Generatore albero delle decisioni.

      La dimensione viene visualizzata nella **Ingresso (Dimension)** elenco con una codifica colore univoca.

   * Aggiungi **Elementi Dimension** come input.

      Nell’area di lavoro, fare clic con il pulsante destro del mouse e selezionare una tabella di Dimension. Seleziona Elementi Dimension, premi **Ctrl** + **Alt** e trascinare gli elementi selezionati nel Generatore albero delle decisioni.

      Gli elementi dimensionali verranno visualizzati nella sezione **Ingresso (elementi)** elenco con una codifica colore univoca.
   >[!IMPORTANT]
   >
   >È possibile selezionare fino a un massimo di quattordici input da valutare. Se vengono aggiunti troppi input, viene visualizzato un messaggio di errore.

1. Seleziona **[!UICONTROL Go]** dalla barra degli strumenti.

   La struttura decisionale verrà creata in base alle dimensioni e alle metriche selezionate. Metriche semplici come Incrementi carrello verranno generate rapidamente, mentre dimensioni complesse come la Durata della visita con più punti di dati verranno generate più lentamente con una percentuale del completamento visualizzata durante la conversione. La mappa ad albero viene quindi troncata e aperta per l’interazione dell’utente. Gli input delle dimensioni e delle metriche saranno codificati in base al colore in linea con i nomi dei nodi.

   ![](assets/decision_tree_builder.png)

   Il nodo foglia viene visualizzato come verde (true) o rosso (false) se l&#39;albero è stato potato e se è presente una previsione di **True** o **False** seguendo i rami potati.

   >[!NOTE]
   >
   >L’esempio di formazione viene estratto dal set di dati per il generatore di albero da utilizzare. La Data Workbench utilizza l&#39;80% del campione per costruire l&#39;albero e il restante 20% per valutare la precisione del modello ad albero.

1. Verificare la precisione utilizzando **[!UICONTROL Confusion Matrix]**.

   Fai clic su **[!UICONTROL Options]** > **[!UICONTROL Confusion Matrix]** per visualizzare i valori Precisione, Richiama, Precisione e Punteggio F. Più vicino al 100%, migliore è il punteggio.

   La Matrice di Confusione fornisce quattro conteggi di precisione del modello utilizzando una combinazione di valori:

   * Positivo effettivo (AP)
   * Positivo previsto (PP)
   * Negativo effettivo (AN)
   * Negativo previsto (PN)

   >[!TIP]
   >
   >Questi numeri si ottengono applicando il modello di punteggio risultante dei dati di test del 20% conservati e già noti come risposta vera. Se il punteggio è maggiore del 50%, viene previsto come caso positivo (che corrisponde al filtro definito). Quindi, Precisione = (TP + TN)/(TP + FP + TN + FN), Richiama = TP / (TP + FN) e Precisione = TP / (TP + FP).

1. **Esplora la struttura decisionale**.

   Dopo aver generato un albero decisionale, puoi visualizzare il percorso della previsione e identificare tutti i visitatori che soddisfano i criteri definiti. La struttura ad albero identifica la suddivisione dell&#39;input per ogni ramo in base alla posizione e alla codifica dei colori. Ad esempio, se selezioni il nodo Dominio di riferimento, i nodi che conducono a tale divisione vengono elencati dal codice colore a sinistra della struttura.

   È possibile effettuare selezioni dei nodi foglia per selezionare i rami (set di regole) della struttura decisionale.

   Per questo esempio: Se la durata della visita è inferiore a 1, non esiste alcuna campagna, esiste almeno una visualizzazione di pagina, non vi sono registrazioni e-mail e vi è stata almeno una visita. Le proiezioni relative a questo criterio di rispondenza e l&#39;ordine sono **94,73** percentuale.

   ![](assets/decision_tree_explore.png)

   **Interazione con Albero decisionale**: È possibile selezionare più nodi nella struttura utilizzando lo standard **Ctrl-clic** aggiungere, oppure **Maiusc-clic** da eliminare.

   **Nodi a colori**: Il colore dei nodi corrisponde al colore delle dimensioni e delle metriche di input assegnato dalla Data Workbench.

   I nodi verdi e rossi chiari a livello di foglia di un ramo potato prevedono il nodo come True o False.

   | ![](assets/decision_tree_node_true.png) Verde chiaro | Identifica che il nodo è uguale a true e che tutte le condizioni sono soddisfatte. |
   |---|---|
   | ![](assets/decision_tree_node_false.png) Rosso brillante | Identifica che il nodo è uguale a falso e non tutte le condizioni sono soddisfatte. |

1. **Salva l&#39;albero delle decisioni**.

   È possibile salvare l&#39;albero delle decisioni in diversi formati:

   ![](assets/decison_tree_save.png)

   * Linguaggio di marcatura predittiva (**PMML**), un formato di file basato su XML utilizzato dalle applicazioni per descrivere e scambiare modelli ad albero decisionali.
   * **Testo** visualizzazione di colonne e righe semplici con true o false, percentuali, numero di membri e valori di input.
   * A **Dimension** con rami corrispondenti agli elementi del risultato previsto.
