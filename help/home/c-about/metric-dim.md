---
description: Crea Dimension definiti dagli attributi delle metriche (Dimensioni metriche) tramite una procedura guidata dettagliata. Quindi testa, visualizza in anteprima e salva il nuovo Dim della metrica nell’elenco dei Dimension.
title: Procedura guidata di attenuazione della metrica (Dimension)
uuid: 411b2e28-0958-43bb-a853-7de7b3063818
exl-id: 4d283a00-409c-4d74-a558-40744caba71c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 2%

---

# Procedura guidata di attenuazione della metrica{#metric-dim-wizard}

{{eol}}

Crea Dimension definiti dagli attributi delle metriche (Dimensioni metriche) tramite una procedura guidata dettagliata. Quindi testa, visualizza in anteprima e salva il nuovo Dim della metrica nell’elenco dei Dimension.

Un’attenuazione della metrica converte una metrica in una nuova dimensione. Ad esempio, un’attenuazione della metrica basata su una metrica di Visualizzazioni di pagina e livello di Visitatore visualizzerà elementi dimensionali in base al totale di Visualizzazioni di pagina per ciascun Visitatore. Consente di estendere una metrica attualmente definita basata su elementi dimensionali per creare e salvare come nuova dimensione.

## Passaggio 1: Selezionare Dimension e metrica {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. Apri la Procedura guidata di attenuazione della metrica.

   In un’area di lavoro, fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Tools]** > **[!UICONTROL Create Metric Dim]**.

1. Denomina l&#39;attenuazione della metrica.

   Per impostazione predefinita, il campo Nome viene compilato automaticamente in base alle selezioni Livello e Metrica.

1. Selezionare un livello Dimension.

   Il livello di dimensione è la dimensione padre contenente tutti i valori degli elementi costitutivi per filtrare l’input e definire un tipo di dimensione.

   I livelli di Dimension includono:

   * ClickThrough
   * Hit
   * Prodotto
   * Visita
   * Visitatore

1. Seleziona una metrica.

   Seleziona una metrica predefinita da estendere e salvare come attenuazione della metrica.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (facoltativo) Crea una formula metrica.

   Fai clic sulla casella per immettere una formula metrica personalizzata. Il valore Preview calcolato verrà visualizzato durante la convalida dell&#39;espressione.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Puoi aggiungere il tuo [espressione metrica](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) o tagliare e incollare da un altro editor di metriche o visualizzazione. Nella procedura guidata vengono segnalati errori di sintassi, errori di formula, filtri non definiti e altri errori.

1. Fai clic su **[!UICONTROL Next]**.

## Passaggio 2: Formatta e imposta intervalli {#section-5bddf3cd306545d7806a501637f80f77}

1. Seleziona un formato per la nuova metrica di attenuazione.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   Il formato definisce il modo in cui la metrica verrà presentata all’apertura in una visualizzazione. Questi formati sono selezionati [standard printf](https://www.cplusplus.com/reference/cstdio/printf/), definito di seguito:

   ```
   %[flags][width][.precision][length][specifier]
   % 0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   In **[!UICONTROL Preview]** viene visualizzato un valore in base alla metrica e al formato selezionati.

1. Aggiungi espressione Conteggio intervalli.

   Puoi definire un’attenuazione della metrica con vari intervalli o periodi fissi. Restituisce sottoinsiemi di elementi in base alle dimensioni, ad esempio [0-4], [5-10]...). Gli elementi del livello di Dimension si riferiscono agli elementi il cui intervallo contiene il valore della metrica. Consulta la descrizione dell’espressione bucket in [Sintassi delle espressioni Dimension](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html).

1. Fai clic su **[!UICONTROL Preview]** per aprire la tabella dei valori di attenuazione della metrica prima di salvare.

   ![](assets/6_4_workstation_metricdim_preview.png)

   La tabella descrive i valori delle metriche per attenuazione metrica.

1. Fai clic su **[!UICONTROL Show in Dimension Menu]** per aggiungere la nuova dimensione creata al **Dimension** nella scheda **Finder**.

1. Fai clic su **[!UICONTROL Next]**.

## Passaggio 3: Fine e salvataggio {#section-d9043235b18a425f9de0db668d4b1683}

1. Dopo il salvataggio, seleziona per avviare l’Editor di attenuazione della metrica, la visualizzazione del grafico o la tabella.

   | Campo | Descrizione |
   |---|---|
   | **[!UICONTROL Launch Metric Dim Editor]** | Apri l’Editor di attenuazione della metrica. |
   | **[!UICONTROL Launch Graph]** | Avviare un grafico PNG della tabella. |
   | **[!UICONTROL Launch Table]** | Avvia una tabella nell’area di lavoro con valori in colonne che elencano i valori della nuova attenuazione metrica rispetto ai valori della metrica selezionata. |

1. Fai clic su **[!UICONTROL Finish]** e salva.

   Viene visualizzata una finestra di dialogo di salvataggio che consente di salvare il file. Le opzioni selezionate per visualizzare i valori si apriranno nell’area di lavoro.
