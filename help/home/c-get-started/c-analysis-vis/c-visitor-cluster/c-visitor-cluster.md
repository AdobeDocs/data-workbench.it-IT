---
description: Il clustering dei visitatori consente di sfruttare le caratteristiche dei clienti per classificare in modo dinamico i visitatori e generare set di cluster basati su input di dati selezionati, identificando così i gruppi che hanno interessi e comportamenti simili per l'analisi e il targeting dei clienti.
solution: Analytics
title: Clustering visitatore
topic: Data workbench
uuid: 0c16aaa0-1d86-43a6-a7e2-b43b3ea80dc5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Clustering visitatore{#visitor-clustering}

Il clustering dei visitatori consente di sfruttare le caratteristiche dei clienti per classificare in modo dinamico i visitatori e generare set di cluster basati su input di dati selezionati, identificando così i gruppi che hanno interessi e comportamenti simili per l&#39;analisi e il targeting dei clienti.

**Processo di cluster**

Il processo di clustering richiede l&#39;identificazione di metriche ed elementi dimensionali da utilizzare come input e consente di scegliere una popolazione target specifica per applicare questi elementi per creare cluster specifici. Quando si esegue il processo di clustering, il sistema utilizza gli input di metrica e dimensione per determinare i centri iniziali appropriati per il numero specificato di cluster. Questi centri vengono quindi utilizzati come punto di partenza per applicare l&#39;algoritmo K-Means.

![](assets/K_algorithm.png)

* I centri iniziali vengono scelti in modo intelligente tramite un passaggio di Clustering Canopy.
* I cluster di dati vengono creati associando ogni punto dati al centro più vicino.
* La media di ciascun cluster K diventa il nuovo centro.
* L&#39;algoritmo viene ripetuto nei passaggi 2 e 3 fino al raggiungimento della convergenza. Questo può richiedere più passaggi.

Il **[!UICONTROL Maximum Iterations]** **[!UICONTROL Options]** menu consente all&#39;analista di specificare il numero massimo di iterazioni da eseguire dall&#39;algoritmo di clustering. L&#39;impostazione di questa opzione può comportare un completamento più rapido del processo di clustering basato sul limite massimo di iterazioni a scapito della convergenza esatta dei centri cluster.

>[!NOTE]
>
>Una volta definiti i cluster, la Dimensione cluster può essere salvata per l&#39;utilizzo come qualsiasi altra dimensione. È inoltre possibile caricarlo in Esplora cluster per esaminare la separazione dei centri cluster.

In Generatore cluster, potete selezionare **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** per selezionare gli algoritmi al momento della definizione dei cluster. Attualmente, sono supportati 3 algoritmi:

* KMeans
* Kway`++`
* Ottimizzazione delle aspettative

Il processo di clustering può essere eseguito in due modi:

* Metodo 1 - Fare clic **[!UICONTROL Go]** nella finestra di visualizzazione del cluster.
* Metodo 2 - Fare clic **[!UICONTROL Submit]** nella finestra di visualizzazione del cluster, che invia direttamente il processo di clustering al server. Potete tenere traccia dell’avanzamento tramite l’opzione &quot;Stato dettagliato per la query&quot;.

![](assets/dwb_visitorclustering.png)

L&#39;algoritmo presenta le seguenti limitazioni:

1. Se si utilizza il metodo 1, è possibile selezionare uno qualsiasi degli algoritmi di clustering supportati.
1. Se si utilizza il metodo 2, è possibile selezionare kmedium o kmedium++. L&#39;opzione Ottimizzazione attesa non sarà disponibile.

>[!NOTE]
>
>Nel [!DNL DPU.cfg] file, il valore per &#39;Query, Limite di memoria&#39; è impostato su 500 MB per impostazione predefinita. Questo valore deve essere aumentato durante l&#39;esecuzione di più processi di clustering. Ad esempio, se eseguite 5 processi di clustering in parallelo, aumentate questo valore a 1 GB. Non è possibile annullare il processo di clustering senza riavviare il server.

**Consigli**

Il numero di iterazioni (il numero di volte che i dati vengono sottoposti a scansione) e la soglia di convergenza configurata, influiscono notevolmente sulle prestazioni del clustering. La tabella seguente contiene una linea guida più ampia che potete seguire:

| Numero di cluster | Algoritmo | Iterazioni | Soglia convergenza | Normalizzazione |
|---|---|---|---|---|
| 6 | Kway | 25,50 | 1e-3 | Min-Max |
| 6 | Kway | 25,50 | 1e-6 | Min-Max |
| 6 | KMedia+ | 50 | 1e-6 | Min-Max |
