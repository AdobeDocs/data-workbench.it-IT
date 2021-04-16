---
description: Seleziona le variabili di input, il numero di cluster e una popolazione target (se desiderato) per definire i cluster nel set di dati.
title: Creazione di cluster
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
exl-id: 60bc75bf-2f89-455b-8be9-aa20bb837752
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 1%

---

# Creazione di cluster{#building-clusters}

Seleziona le variabili di input, il numero di cluster e una popolazione target (se desiderato) per definire i cluster nel set di dati.

**Creazione di cluster**

1. Apri **[!UICONTROL Cluster Builder]**.

   Fai clic su **Visualizzazione** > **Analisi predittiva** > **Clustering** > **Generatore di cluster**.

   ![](assets/cluster-builder-step1.png)

1. Seleziona le variabili di input.

   * Aggiungi le metriche all’elenco **[!UICONTROL Input Variables]** selezionando dal menu **[!UICONTROL Metric]** nella barra degli strumenti.

      ![](assets/cluster_metric_select.png)

   * Aggiungi elementi dimensionali all&#39;elenco **[!UICONTROL Input Variables]** trascinandoli da una tabella del Dimension.

      Premi **[!UICONTROL Ctrl + Alt]** e trascina gli elementi dimensionali selezionati nell’elenco **[!UICONTROL Input Variables]** o nella casella **[!UICONTROL Element]** della barra degli strumenti.

      ![](assets/cluster_dim_select.png)
   Per impostazione predefinita, il clustering viene eseguito sull&#39;intero set di dati. Puoi visualizzare tutte le variabili di input nel riquadro a sinistra **[!UICONTROL Preprocessing]**.
1. Utilizza il menu **[!UICONTROL Options]** per selezionare il numero desiderato di cluster.

   ![](assets/build_cluster_2.png)

1. Se desideri raggruppare un sottoinsieme di visitatori nel set di dati, puoi definire un filtro di popolazione.

   ![](assets/build_cluster_3.png)

   Per iniziare, definisci il sottoinsieme desiderato utilizzando le selezioni nell’area di lavoro o utilizzando il simbolo **[!UICONTROL Filter Editor]**. Dopo aver selezionato il sottoinsieme desiderato, impostate Popolazione di destinazione nel menu **[!UICONTROL Options]** . Si consiglia di assegnare al gruppo di destinazione un nome di identificazione.

   Il menu **[!UICONTROL Options]** dispone anche di impostazioni per controllare il numero massimo di passate e la soglia accettabile per la convergenza centrale.

1. Dopo aver configurato gli input e le opzioni, fai clic sul pulsante **Vai** per eseguire il clustering localmente oppure premi **[!UICONTROL Submit]** per inviare l&#39;attività al server Predictive Analytics. Le invii al server salveranno la dimensione risultante nel set di dati al termine della convergenza.

   Quando viene eseguito localmente, verrà visualizzato il Generatore cluster che si sposta attraverso quattro fasi di clustering canoy mentre definisce centri intelligenti basati sugli input.

   Una volta che i centri dei cluster smettono di cambiare più della soglia di convergenza specificata, il Dimension Cluster viene convertito e il Generatore di cluster visualizza informazioni aggiuntive su quanto rilevante era un input per ciascun cluster.

1. Personalizza i cluster.

   Fai clic con il pulsante destro del mouse sulla barra dei colori delle statistiche per aprire un menu di scelta rapida che ti consente di personalizzare le soglie di rilevanza e, nel caso delle distribuzioni degli elementi di dimensione, di scegliere quale test viene visualizzato.

   ![](assets/build_cluster_7.png)

   Gli input delle metriche forniscono un test t per ciascun cluster, mentre gli input degli elementi dimensionali forniscono tre test di distribuzione (Chi al quadrato, una statistica dell&#39;entropia U e la statistica del V di Cramer) per ciascun cluster.

   >[!NOTE]
   >
   >Se aggiungi o rimuovi gli input durante la convergenza, il processo verrà messo in pausa fino a quando non premi nuovamente **Go**.

   Dopo aver creato i cluster, puoi aprire il selettore colore per assegnare i colori per diversi risultati di distribuzione.

   ![](assets/build_cluster_5.png)

1. Con il Dimension Cluster convergente, puoi aggiungere metriche alla tabella e effettuare selezioni come normali. Puoi anche fare clic con il pulsante destro del mouse sui nomi degli elementi (Cluster 1, Cluster 2, ecc.) per aprire il menu di scelta rapida e rinominarli in modo più significativo.

   ![](assets/build_cluster_6.png)

1. Se desideri utilizzare questa dimensione cluster in altre visualizzazioni, puoi **[!UICONTROL Save]** localmente o **[!UICONTROL Submit]** sul server.

Se desideri eseguire nuovamente la convergenza o vedere la pertinenza degli input, Cluster Builder può anche caricare le dimensioni cluster esistenti.

>[!TIP]
>
>Quando questa opzione è selezionata, **[!UICONTROL Reset]** rilascerà completamente tutte le variabili di input e fornirà una visualizzazione vuota del generatore di cluster per definire nuovi cluster.
