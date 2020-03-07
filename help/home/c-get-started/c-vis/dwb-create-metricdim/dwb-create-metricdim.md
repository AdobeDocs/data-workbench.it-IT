---
description: Utilizzate la procedura guidata Dim metrica per creare una nuova dimensione metrica.
title: Procedura guidata di attenuazione delle metriche
uuid: 77b9bc8e-7625-4fef-9de4-f113f9b2debd
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Procedura guidata di attenuazione delle metriche{#metric-dim-wizard}

Utilizzate la procedura guidata Dim metrica per creare una nuova dimensione metrica.

Un Dim della metrica converte una metrica in una nuova dimensione. Ad esempio, un Dim della metrica basato su una metrica Visualizzazioni di pagina e livello di Visitatore visualizzerà elementi dimensionali basati sul totale Visualizzazioni di pagina per ciascun Visitatore. Consente di estendere una metrica correntemente definita basata su elementi dimensionali per creare e salvare come nuova dimensione.

## Passaggio 1: seleziona dimensione e metrica {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. **Aprite la procedura guidata** Dim metrica.

   In un’area di lavoro, fare clic con il pulsante destro del mouse e selezionare **Strumenti** > **Crea immagine** metrica.

1. **Denominate il valore di attenuazione** della metrica.

   Per impostazione predefinita, il campo Nome viene compilato automaticamente in base alle selezioni Livello e Metrica.

1. **Selezionare un livello dimensione.** Il livello della dimensione è la dimensione padre che contiene tutti i valori degli elementi costitutivi per filtrare l’input e definire un tipo di dimensione.

   I livelli di dimensione includono:

   * Clic
   * Hit
   * Prodotto
   * Visita
   * Visitatore

1. **Selezionare una metrica**.

   Seleziona una metrica pregenerata per estenderla e salvarla come un&#39;attenuazione della metrica.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (facoltativo) **Create una formula** metrica.

   Fare clic sulla casella per immettere una formula metrica personalizzata. Il valore Preview calcolato verrà visualizzato convalidando l&#39;espressione.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Puoi aggiungere la tua espressione [di](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) metrica oppure tagliare e incollare da un altro editor o visualizzazione di metriche. Errori di sintassi, errori di formula, filtri non definiti e altri errori vengono segnalati nella procedura guidata.

1. Fai clic su **Successivo**.

## Passaggio 2: formati e set bucket {#section-5bddf3cd306545d7806a501637f80f77}

È possibile selezionare il formato della metrica e impostare i valori del bucket per un&#39;espressione di dimensione.

1. Selezionate un **formato** per il nuovo dim della metrica.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   Il formato definisce il modo in cui la metrica verrà presentata quando viene aperta in una visualizzazione. Questi formati sono selezionati [standard](http://www.cplusplus.com/reference/cstdio/printf/)di stampa, definiti di seguito:

   ```
   %[flags][width][.precision][length][specifier]
   %
   0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   Nel campo **Anteprima** , verrà visualizzato un valore basato sulla metrica e sul formato selezionati.

1. Aggiungi espressione **Conteggio** intervalli.

   Puoi definire una metrica con vari intervalli o intervalli. Questo restituisce sottoinsiemi di elementi basati sulle dimensioni, ad esempio [0-4], [5-10],...). Gli elementi del livello dimensione si riferiscono agli elementi il cui intervallo contiene il valore della metrica. Consultate la descrizione dell&#39;espressione bucket in [Sintassi per le espressioni](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html)dimensione.

1. Fate clic su **Anteprima** per aprire la tabella dei valori di Dim metrica prima di salvare.

   ![](assets/6_4_workstation_metricdim_preview.png)

   La tabella specifica i valori delle metriche per la metrica dim.

1. Fai clic su **Mostra nel menu** dimensioni per aggiungere la dimensione appena creata alla scheda **Dimensione** nel **Finder**.
1. Fai clic su **Successivo**.

## Passaggio 3: fine e salva {#section-d9043235b18a425f9de0db668d4b1683}

1. Selezionate questa opzione per avviare l’Editor di attenuazione metrica, la visualizzazione grafico o la tabella dopo il salvataggio.

   | Campo | Descrizione |
   |---|---|
   | Avvia editor Dim della metrica | Aprite l’Editor di attenuazione della metrica. |
   | Avvia grafico | Avviate un elemento grafico PNG della tabella. |
   | Avvia tabella | Avviate una tabella nell’area di lavoro con valori in colonne che elencano i valori della nuova metrica dim rispetto ai valori della metrica selezionata. |

1. Fate clic su **Fine** e salvate.

   Viene aperta una finestra di dialogo di salvataggio che consente di salvare il file. Le opzioni selezionate per visualizzare i valori si apriranno nell’area di lavoro.

