---
description: I grafici radar forniscono una rapida messa a fuoco sulle aree che richiedono maggiore attenzione, fornendo una visualizzazione di un insieme di metriche e il modo in cui si relazionano o differiscono.
solution: Analytics
title: Visualizzazione radar
topic: Data workbench
uuid: 39d67743-b6c1-46f1-99fd-7c71dfe07932
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualizzazione radar{#radar-visualization}

I grafici radar forniscono una rapida messa a fuoco sulle aree che richiedono maggiore attenzione, fornendo una visualizzazione di un insieme di metriche e il modo in cui si relazionano o differiscono.

Molte volte è necessario disporre di più metriche per comprendere e valutare le osservazioni selezionate in un’area di lavoro.

Questa visualizzazione è utile per i confronti o i benchmark tra le selezioni di tabelle. Ad esempio, puoi aggiungere una tabella dell’area di lavoro in cui sono elencati gli store, quindi una visualizzazione radar con metriche quali Entrate, Visitatori e Visualizzazioni pagina. (Come mostrato nella schermata nella procedura seguente). Quando si effettuano le selezioni dello store nella tabella, l&#39;impronta del grafico radar si sposta, identificando punti deboli o punti di forza nelle metriche per lo store selezionato.

Ogni elemento radiale di un grafico radar è una metrica e sono necessarie almeno tre metriche. I dati della metrica vengono tracciati in relazione a una metrica ancorata. La metrica ancorata e il parametro Scala ad ancoraggio per ciascuna metrica determinano il ridimensionamento delle metriche rispetto ai benchmark.

**Per creare una visualizzazione radar**

1. Fare clic con il pulsante destro del mouse nell&#39;area di lavoro, quindi scegliere **[!UICONTROL Visualization]** > **[!UICONTROL Radar]**.

   ![](assets/client-rad.png)

1. Per aggiungere metriche, fai clic con il pulsante destro del mouse nella visualizzazione e seleziona **[!UICONTROL Add Metric]**.
1. Per ancorare una metrica al grafico, fai clic con il pulsante destro del mouse su una metrica e scegli la seguente opzione:

   **Ancoraggio a questa metrica:** Utilizza questa metrica come riferimento a cui vengono tracciate altre metriche. Puoi ancorare una metrica alla volta. Ogni metrica del grafico viene filtrata dalla selezione dell&#39;area di lavoro attiva o da nessun filtro. Il rapporto di benchmark tra questi due valori viene tracciato sull’asse compreso tra il centro del grafico e il nome della metrica sul radar. Zero è tracciato al centro.

1. Per ridimensionare una metrica con la metrica ancorata, fai clic con il pulsante destro del mouse sulla metrica e scegli la seguente opzione:

   **Scala con ancoraggio:** Quando è attivato, l&#39;asse di questa metrica viene ridimensionato in modo che il rapporto di benchmark per la metrica di ancoraggio selezionata venga tracciato nel cerchio, con zero al centro. Se non è selezionato, il cerchio rappresenta un rapporto di benchmark di 1. In genere, è possibile attivare l&#39;opzione Scala con ancoraggio per le metriche numerabili, come Visitatori o Visualizzazioni pagina, e disattivarla per le metriche delle proporzioni, come Conversione, Durata media sessione o Visualizzazioni pagina per sessione.

