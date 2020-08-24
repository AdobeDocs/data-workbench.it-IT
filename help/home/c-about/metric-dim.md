---
description: Create Dimension definiti dagli attributi della metrica (Metric Dims) tramite una procedura guidata dettagliata. Quindi verificate, visualizzate in anteprima e salvate il nuovo Dim metrica nell’elenco dei vostri Dimension.
title: Procedura guidata di attenuazione della metrica
uuid: 411b2e28-0958-43bb-a853-7de7b3063818
translation-type: tm+mt
source-git-commit: 35e6e9280ab36e8b39e89039b791199d1de54e03
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 2%

---


# Procedura guidata di attenuazione della metrica{#metric-dim-wizard}

Create Dimension definiti dagli attributi della metrica (Metric Dims) tramite una procedura guidata dettagliata. Quindi verificate, visualizzate in anteprima e salvate il nuovo Dim metrica nell’elenco dei vostri Dimension.

Un Dim della metrica converte una metrica in una nuova dimensione. Ad esempio, un Dim della metrica basato su una metrica Visualizzazioni di pagina e livello di Visitatore visualizzerà elementi dimensionali basati sul totale Visualizzazioni di pagina per ciascun Visitatore. Consente di estendere una metrica correntemente definita basata su elementi dimensionali per creare e salvare come nuova dimensione.

## Step 1: Select Dimension and Metric {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. Aprite la Creazione guidata Dim metrica.

   In un’area di lavoro, fate clic con il pulsante destro del mouse e selezionate **[!UICONTROL Tools]** > **[!UICONTROL Create Metric Dim]**.

1. Denominate il valore di attenuazione della metrica.

   Per impostazione predefinita, il campo Nome viene compilato automaticamente in base alle selezioni Livello e Metrica.

1. Selezionate un livello di Dimension.

   Il livello della dimensione è la dimensione padre che contiene tutti i valori degli elementi costitutivi per filtrare l’input e definire un tipo di dimensione.

   I livelli di Dimension includono:

   * Clic
   * Hit
   * Prodotto
   * Visita
   * Visitatore

1. Selezionare una metrica.

   Seleziona una metrica pregenerata per estenderla e salvarla come un&#39;attenuazione della metrica.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (facoltativo) Crea una formula metrica.

   Fare clic sulla casella per immettere una formula metrica personalizzata. Il valore Preview calcolato verrà visualizzato convalidando l&#39;espressione.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Puoi aggiungere la tua espressione [di](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) metrica oppure tagliare e incollare da un altro editor o visualizzazione di metriche. Errori di sintassi, errori di formula, filtri non definiti e altri errori vengono segnalati nella procedura guidata.

1. Fai clic su **[!UICONTROL Next]**.

## Passaggio 2: Formato e imposta intervalli {#section-5bddf3cd306545d7806a501637f80f77}

1. Selezionare un formato per la nuova metrica dim.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   Il formato definisce il modo in cui la metrica verrà presentata quando viene aperta in una visualizzazione. Questi formati sono selezionati [standard](http://www.cplusplus.com/reference/cstdio/printf/)di stampa, definiti di seguito:

   ```
   %[flags][width][.precision][length][specifier]
   % 0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   Nel **[!UICONTROL Preview]** campo viene visualizzato un valore basato sulla metrica e sul formato selezionati.

1. Aggiungi espressione Conteggio intervalli.

   Puoi definire una metrica con vari intervalli o intervalli. Questo restituisce sottoinsiemi di elementi basati sulle dimensioni, ad esempio [0-4], [5-10],...). Gli elementi del livello Dimension si riferiscono agli elementi il cui intervallo contiene il valore della metrica. Consultate la descrizione dell&#39;espressione bucket in [Sintassi per le espressioni](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html)di Dimension.

1. Fare clic **[!UICONTROL Preview]** per aprire la tabella dei valori di Dim metrica prima di salvare.

   ![](assets/6_4_workstation_metricdim_preview.png)

   La tabella specifica i valori delle metriche per la metrica dim.

1. Fate clic **[!UICONTROL Show in Dimension Menu]** per aggiungere la dimensione appena creata alla scheda **Dimension** nel **Finder**.

1. Fai clic su **[!UICONTROL Next]**.

## Passaggio 3: Fine e Salva {#section-d9043235b18a425f9de0db668d4b1683}

1. Selezionate questa opzione per avviare l’Editor di attenuazione metrica, la visualizzazione grafico o la tabella dopo il salvataggio.

   | Campo | Descrizione |
   |---|---|
   | **[!UICONTROL Launch Metric Dim Editor]** | Aprite l’Editor di attenuazione della metrica. |
   | **[!UICONTROL Launch Graph]** | Avviate un elemento grafico PNG della tabella. |
   | **[!UICONTROL Launch Table]** | Avviate una tabella nell’area di lavoro con valori in colonne che elencano i valori della nuova metrica dim rispetto ai valori della metrica selezionata. |

1. Fate clic su **[!UICONTROL Finish]** e salvate.

   Viene aperta una finestra di dialogo di salvataggio che consente di salvare il file. Le opzioni selezionate per visualizzare i valori si apriranno nell’area di lavoro.

