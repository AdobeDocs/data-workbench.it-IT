---
description: Cluster Builder ora include un algoritmo KMeans++ (in precedenza era supportato solo l'algoritmo KMeans) che utilizza un approccio più veloce per individuare i centri per un processo di generazione dei cluster accelerato.
title: Clustering 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Clustering 2.0{#clustering}

Cluster Builder ora include un algoritmo KMeans++ (in precedenza era supportato solo l&#39;algoritmo KMeans) che utilizza un approccio più veloce per individuare i centri per un processo di generazione dei cluster accelerato.

## Algoritmi KMeans {#section-92383a1be1d6402c95a25c902e90b850}

In [Cluster Builder](https://docs.adobe.com/help/en/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html), è ora possibile selezionare **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** per selezionare gli algoritmi al momento della definizione dei cluster.

* **[!UICONTROL KMeans]** (Progetto > scarica CSV). Questo algoritmo utilizza il clustering canoy per definire i centri del cluster.
* **[!UICONTROL KMeans++]** (Progetto > scarica CSV). Questo algoritmo consente di velocizzare la creazione dei cluster quando viene eseguito su grandi set di dati.

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++ è una migliore implementazione dell&#39;algoritmo di clustering KMeans perché fornisce una migliore inizializzazione dei centri k iniziali. L’algoritmo KMeans originale sceglie i centri iniziali in modo casuale. KMeans++ seleziona il primo centro in modo casuale. I restanti centri K-1 saranno scelti uno per uno in base alla distanza che un punto dati è al centro esistente più vicino. I punti dati più avanzati hanno maggiori possibilità di essere scelti come un nuovo centro rispetto ai punti dati vicini. Dopo aver scelto il centro iniziale, la procedura viene eseguita esattamente come il cluster KMeans originale.

Il flusso di lavoro per KMeans++ è identico al flusso di lavoro per il clustering KMeans, con la differenza che è necessario selezionare **Opzioni** > **Algoritmo** > **KMeans++** nel generatore di cluster.

>[!NOTE]
>
>Ogni DPU esegue la propria procedura KMeans++ sulla propria porzione di dati. Se il DPU dispone di memoria sufficiente (il rapporto è configurabile nel file PAServer.cfg), i dati delle variabili coinvolte saranno messi in memoria. La selezione iniziale del centro k-1 e le iterazioni convergenti rimanenti avvengono in memoria, il che è più veloce del precedente clustering KMeans.

