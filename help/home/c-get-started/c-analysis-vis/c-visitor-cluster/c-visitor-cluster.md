---
description: Il clustering visitatore consente di sfruttare le caratteristiche del cliente per categorizzare dinamicamente i visitatori e generare set di cluster basati su input di dati selezionati, identificando così i gruppi che hanno interessi e comportamenti simili per l’analisi e il targeting dei clienti.
title: Clustering visitatore
uuid: 0c16aaa0-1d86-43a6-a7e2-b43b3ea80dc5
exl-id: 68c1845d-9c49-4ad9-adf3-c123d08cf758
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 2%

---

# Clustering visitatore{#visitor-clustering}

Il clustering visitatore consente di sfruttare le caratteristiche del cliente per categorizzare dinamicamente i visitatori e generare set di cluster basati su input di dati selezionati, identificando così i gruppi che hanno interessi e comportamenti simili per l’analisi e il targeting dei clienti.

**Processo di clustering**

Il processo di clustering richiede l’identificazione di metriche ed elementi dimensionali da utilizzare come input e consente di scegliere una popolazione target specifica per applicare questi elementi per creare cluster specifici. Quando si esegue il processo di clustering, il sistema utilizza la metrica e gli input della dimensione per determinare i centri iniziali appropriati per il numero specificato di cluster. Questi centri vengono quindi utilizzati come punto di partenza per applicare l&#39;algoritmo K-Means.

![](assets/K_algorithm.png)

* I centri iniziali sono scelti in modo intelligente tramite un passaggio Canopy Clustering.
* I cluster di dati vengono creati associando ogni punto dati al centro più vicino.
* La media di ciascuno dei cluster K diventa il nuovo centro.
* L&#39;algoritmo viene ripetuto nei passaggi 2 e 3 fino al raggiungimento della convergenza. Questo può richiedere più passaggi.

Il **[!UICONTROL Maximum Iterations]** nel menu **[!UICONTROL Options]** consente all&#39;analista di specificare il numero massimo di iterazioni da eseguire dall&#39;algoritmo di clustering. L&#39;impostazione di questa opzione può comportare un completamento più rapido del processo di clustering basato sul limite massimo di iterazioni a scapito della convergenza esatta dei centri cluster.

>[!NOTE]
>
>Una volta definiti i cluster, il Dimension Cluster può essere salvato per l&#39;utilizzo come qualsiasi altra dimensione. Può anche essere caricato in Esplora cluster per esaminare la separazione dei centri cluster.

In Cluster Builder, puoi selezionare **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** per selezionare gli algoritmi durante la definizione dei cluster. Al momento sono disponibili 3 algoritmi supportati:

* KMeans
* KMedia`++`
* Massimizzazione delle aspettative

Esistono 2 modi per eseguire il processo di clustering:

* Metodo 1 - Fare clic su **[!UICONTROL Go]** nella finestra di visualizzazione del cluster.
* Metodo 2 - Fare clic su **[!UICONTROL Submit]** nella finestra di visualizzazione del cluster, che invia direttamente il processo di clustering al server. Puoi tenere traccia dell’avanzamento tramite l’opzione &quot;Stato dettagliato per la query&quot;.

![](assets/dwb_visitorclustering.png)

L’algoritmo presenta le seguenti limitazioni:

1. Se si utilizza il metodo 1, è possibile selezionare uno qualsiasi degli algoritmi di clustering supportati.
1. Se si utilizza il metodo 2, è possibile selezionare kmedium o kmedium++. L’opzione Ottimizzazione delle aspettative non sarà disponibile.

>[!NOTE]
>
>Nel file [!DNL DPU.cfg], il valore per &#39;Query, Limite di memoria&#39; è impostato su 500 MB per impostazione predefinita. Questo valore deve essere aumentato durante l&#39;esecuzione di più processi di clustering. Ad esempio, se esegui 5 processi di clustering in parallelo, aumenta questo valore a 1 GB. Non è possibile annullare il processo di clustering senza riavviare il server.

**Consigli**

Il numero di iterazioni (il numero di volte in cui i dati vengono analizzati) e la soglia di convergenza che configuri incidono notevolmente sulle prestazioni del clustering. La tabella seguente fornisce una linea guida più ampia da seguire:

| Numero di cluster | Algoritmo | Iterazioni | Soglia di convergenza | Normalizzazione |
|---|---|---|---|---|
| 6 | Kays | 25,50 | 1e-3 | Min-Max |
| 6 | Kays | 25,50 | 1e-6 | Min-Max |
| 6 | KMedia+ | 50 | 1e-6 | Min-Max |
