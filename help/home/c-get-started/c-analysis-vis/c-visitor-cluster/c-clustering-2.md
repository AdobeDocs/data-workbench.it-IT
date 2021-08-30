---
description: Il Generatore di cluster ora include un algoritmo KMeans++ (in precedenza era supportato solo l'algoritmo KMeans) che utilizza un approccio più veloce per trovare i centri per un processo di generazione dei cluster accelerato.
title: Clustering 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
exl-id: 6a779ddc-c8f1-4c55-9c17-1119fe1aa791
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Clustering 2.0{#clustering}

Il Generatore di cluster ora include un algoritmo KMeans++ (in precedenza era supportato solo l&#39;algoritmo KMeans) che utilizza un approccio più veloce per trovare i centri per un processo di generazione dei cluster accelerato.

## Algoritmi KMeans {#section-92383a1be1d6402c95a25c902e90b850}

In [Generatore di cluster](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html?lang=en), ora puoi selezionare **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** per selezionare gli algoritmi durante la definizione dei cluster.

* **[!UICONTROL KMeans]**. Questo algoritmo utilizza il clustering canoy per definire i centri del cluster.
* **[!UICONTROL KMeans++]**. Questo algoritmo espande la creazione di cluster quando viene eseguito su grandi set di dati.

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++ è una migliore implementazione dell&#39;algoritmo di clustering KMeans perché fornisce una migliore inizializzazione dei centri k iniziali. (L&#39;algoritmo KMeans originale sceglie i centri iniziali in modo casuale.) KMeans++ seleziona il primo centro in modo casuale. I restanti centri K-1 saranno scelti uno per uno in base alla distanza che un punto di dati è al centro esistente più vicino. I punti dati più avanzati hanno maggiori possibilità di essere scelti come un nuovo centro rispetto ai punti dati vicini. Dopo aver scelto il centro iniziale, la procedura viene eseguita esattamente come il clustering KMeans originale.

Il flusso di lavoro per KMeans++ è esattamente lo stesso del flusso di lavoro per il clustering KMeans, tranne per il fatto che è necessario selezionare **Opzioni** > **Algorithm** > **KMeans++** nel generatore di cluster.

>[!NOTE]
>
>Ogni DPU esegue la propria routine KMeans++ sulla propria porzione di dati. Se la DPU ha abbastanza memoria disponibile (il rapporto è configurabile nel file PAServer.cfg), i dati delle variabili coinvolte saranno portati in memoria. La selezione iniziale del centro k-1 e le iterazioni convergenti rimanenti si verificano tutti nella memoria, che è più veloce del precedente clustering KMeans.
