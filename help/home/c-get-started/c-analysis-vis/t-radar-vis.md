---
description: I grafici radar consentono di concentrarsi rapidamente sulle aree che richiedono maggiore attenzione, fornendo una visualizzazione di un insieme di metriche e sulle relative relazioni o differenze.
title: Visualizzazione radar
uuid: 39d67743-b6c1-46f1-99fd-7c71dfe07932
exl-id: 5385d903-422b-4936-bbb3-0d5ee4d286de
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---

# Visualizzazione radar{#radar-visualization}

I grafici radar consentono di concentrarsi rapidamente sulle aree che richiedono maggiore attenzione, fornendo una visualizzazione di un insieme di metriche e sulle relative relazioni o differenze.

Molte volte è necessario disporre di più metriche per comprendere e valutare le osservazioni selezionate in un’area di lavoro.

Questa visualizzazione è utile per i confronti o i benchmark tra le selezioni delle tabelle. Ad esempio, puoi aggiungere una tabella dell’area di lavoro in cui sono elencati gli archivi, quindi aggiungere una visualizzazione radar con metriche quali Entrate, Visitatori e Visualizzazioni di pagina. (Come mostrato nella schermata nella procedura seguente). Quando si eseguono le selezioni dell&#39;archivio nella tabella, l&#39;impronta del grafico radar si sposta, identificando le debolezze o i punti di forza delle metriche per l&#39;archivio selezionato.

Ogni raggio di un grafico a radar è una metrica e sono necessarie almeno tre metriche. I dati della metrica vengono tracciati in relazione a una metrica ancorata. La metrica ancorata e il parametro Scala ad ancoraggio per ogni metrica determinano la scala delle metriche rispetto ai benchmark.

**Per creare una visualizzazione radar**

1. Fai clic con il pulsante destro del mouse nell’area di lavoro, quindi fai clic su **[!UICONTROL Visualization]** > **[!UICONTROL Radar]**.

   ![](assets/client-rad.png)

1. Per aggiungere metriche, fai clic con il pulsante destro del mouse nella visualizzazione e seleziona **[!UICONTROL Add Metric]**.
1. Per ancorare una metrica al grafico, fai clic con il pulsante destro del mouse su una metrica e scegli la seguente opzione:

   **Ancoraggio a questa metrica:** utilizza questa metrica come riferimento a cui vengono tracciate altre metriche. Puoi ancorare una metrica alla volta. Ogni metrica del grafico viene filtrata dalla selezione dell’area di lavoro attiva o da nessun filtro. Il rapporto di riferimento tra questi due valori è tracciato sull&#39;asse tra il centro del grafico e il nome della metrica sul radar. Zero è tracciato al centro.

1. Per ridimensionare una metrica con la metrica ancorata, fai clic con il pulsante destro del mouse sulla metrica e scegli la seguente opzione:

   **Scala con ancoraggio:** se attivato, l’asse di questa metrica viene ridimensionato in modo che il rapporto di riferimento per la metrica di ancoraggio selezionata venga tracciato nel cerchio, con zero al centro. Se non è selezionato, il cerchio rappresenta un rapporto di riferimento di 1. In genere, si attiva l&#39;opzione Scala con ancoraggio per le metriche numerabili, ad esempio Visitatori o Visualizzazioni di pagina, e la si disattiva per le metriche delle proporzioni, come Conversione, Durata media sessione o Visualizzazioni di pagina per sessione.
