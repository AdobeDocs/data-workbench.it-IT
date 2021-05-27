---
description: Le mappe dei processi consentono di analizzare il flusso di attività tra gli elementi di una dimensione.
title: Mappa del processo
uuid: f1db41a9-400e-467a-ba59-39831fb166af
exl-id: 019cee7b-a704-4b47-84c6-d3ddc277c43e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 0%

---

# Mappa del processo{#process-map}

Le mappe dei processi consentono di analizzare il flusso di attività tra gli elementi di una dimensione.

Puoi creare mappe di processo trascinando e rilasciando gli elementi di una dimensione su una mappa bidimensionale (2D) o tridimensionale (3D) vuota. Gli elementi diventano nodi sulla mappa. I nodi sono cerchi nelle mappe del processo 2D e barre nelle mappe del processo 3D.

![](assets/vis_2DProcessMap.png)

![](assets/vis_3DProcessMap.png)

>[!NOTE]
>
>Una mappa del processo ottiene il proprio nome dal relativo utilizzo nell’analisi del flusso di attività tra i passaggi di un processo. In questo tipo di analisi, ogni elemento sulla mappa rappresenta un passaggio del processo.

A differenza dei browser del percorso, le mappe del processo possono mostrare il numero di elementi necessari per l&#39;analisi. Scegli gli elementi di interesse e trascinali sulla mappa. Anche a differenza dei browser del percorso, le mappe del processo rappresentano il flusso di attività in entrambe le direzioni tra un elemento e uno o più altri elementi.

>[!NOTE]
>
>Affinché queste mappe funzionino nel modo più efficace, devi aprire una legenda colore nell&#39;area di lavoro. Per informazioni sull&#39;utilizzo delle legende a colori con le mappe del processo, vedere [Attivazione dei collegamenti a colori](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-act-color-lnks.md#concept-2c9b9f67f2bd4cd7a5431fa21c094edc). Per ulteriori informazioni sulle legende a colori, consulta [Color Legends](../../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

A ogni mappa del processo sono associate una dimensione di base, una dimensione di gruppo, una dimensione di livello e una metrica, che forniscono le chiavi per interpretare i dati visualizzati nella mappa del processo.

Le impostazioni predefinite per le dimensioni e la metrica di una mappa del processo dipendono dall’applicazione Data Workbench in uso. Per informazioni sulle dimensioni e metriche disponibili per le mappe dei processi, consulta la guida dell’applicazione per l’applicazione Data Workbench.

* **Dimensione di base:** quando trascini e rilascia un elemento su una mappa del processo, trascini e rilascia un elemento della dimensione di base.
* **Dimensione livello:** ogni dimensione del set di dati presenta una dimensione di livello associata (detta anche dimensione principale). La dimensione del livello per la mappa del processo deve essere la stessa della dimensione del livello (o superiore) per la dimensione di base della mappa del processo. Ad esempio, se trascini una pagina (un elemento della dimensione Pagina) sulla mappa, la dimensione di livello corrispondente sarà Visualizzazione pagina.
* **Dimensione gruppo:** la dimensione gruppo determina il modo in cui gli elementi della dimensione livello vengono raggruppati per formare le connessioni tra i nodi. Per le mappe del processo, la dimensione del gruppo è importante per tre motivi principali:

   * Una connessione tra due nodi non può estendersi su più di un elemento di una dimensione di gruppo. Per comprendere questo aspetto, considera un esempio utilizzando i dati web. Supponiamo che le dimensioni di base, livello e gruppo per la mappa del processo siano rispettivamente Pagina, Visualizzazione pagina e Sessione. Una connessione dalla pagina A alla pagina B indica che, durante una singola sessione, si è verificata una visualizzazione della pagina A prima di una visualizzazione della pagina B senza visualizzazioni di pagina intermedie di altre pagine (nodi) sulla mappa. Tieni presente che le visualizzazioni di pagina di altre pagine del sito potrebbero essersi verificate tra le visualizzazioni di pagina per le pagine A e B durante la stessa sessione, ma queste pagine non vengono visualizzate su questa mappa.
   * Una connessione tra due nodi può rappresentare più elementi della dimensione del gruppo. Ad esempio, potrebbero esserci più sessioni in cui si è verificata una visualizzazione di pagina della pagina A prima di una visualizzazione di pagina della pagina B. Pertanto, la connessione tra la pagina A e la pagina B rappresenta tutte le singole sessioni in cui si è verificata una visualizzazione di pagina della pagina A prima di una visualizzazione di pagina della pagina B senza visualizzazioni di pagina intervenienti di altre pagine (nodi) sulla mappa.
   * Quando effettui una selezione basata su un nodo all’interno di una mappa del processo, stai selezionando tutti gli elementi della dimensione del gruppo che coinvolgono quel nodo. Consulta [Effettuare selezioni in Visualizations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746). Per informazioni sulle selezioni, consulta [Effettuare selezioni in Visualizations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

* **Metrica:** la dimensione del nodo di un dato elemento è proporzionale al valore della metrica per quell’elemento. I nodi più grandi indicano valori di metrica maggiori dei nodi più piccoli.

Ad esempio, se utilizzi l’applicazione [!DNL Site] o HBX, puoi trascinare, per impostazione predefinita, elementi della dimensione Pagina nella mappa del processo. La dimensione di ciascun nodo è correlata alla quantità di sessioni (definite dalla metrica Sessions) in cui è stata visualizzata la pagina.

>[!NOTE]
>
>Puoi modificare le dimensioni o la metrica predefinite per una mappa del processo. Per i passaggi per configurare una mappa del processo, consulta [Configurazione di mappe del processo](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).
