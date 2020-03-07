---
description: Le mappe dei processi consentono di analizzare il flusso di attività tra gli elementi di una dimensione.
solution: Analytics
title: Mappa del processo
topic: Data workbench
uuid: f1db41a9-400e-467a-ba59-39831fb166af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mappa del processo{#process-map}

Le mappe dei processi consentono di analizzare il flusso di attività tra gli elementi di una dimensione.

Per creare mappe di processo, trascinate e rilasciate gli elementi di una dimensione su una mappa bidimensionale (2D) o tridimensionale (3D) vuota. Gli elementi diventano nodi sulla mappa. I nodi sono cerchi nelle mappe di processo 2D e barre nelle mappe di processo 3D.

![](assets/vis_2DProcessMap.png)

![](assets/vis_3DProcessMap.png)

>[!NOTE]
>
>Una mappa di processo ottiene il proprio nome dal relativo utilizzo nell&#39;analisi del flusso di attività tra i passaggi di un processo. In questo tipo di analisi, ogni elemento sulla mappa rappresenta un passo nel processo.

A differenza dei browser di percorsi, le mappe di processo possono mostrare il numero di elementi necessari per l&#39;analisi. Potete scegliere gli elementi di interesse e trascinarli sulla mappa. Anche a differenza dei browser dei percorsi, le mappe dei processi rappresentano il flusso di attività in entrambe le direzioni tra un elemento e uno o più altri elementi.

>[!NOTE]
>
>Affinché queste mappe funzionino nel modo più efficace, è necessario aprire una legenda di colore nell&#39;area di lavoro. Per informazioni sull’uso delle legende a colori con le mappe di processo, consultate [Attivazione dei collegamenti](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-act-color-lnks.md#concept-2c9b9f67f2bd4cd7a5431fa21c094edc)a colori. Per ulteriori informazioni sulle legende a colori, consultate Legende [a](../../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)colori.

Ogni mappa di processo ha una dimensione di base, una dimensione di gruppo, una dimensione di livello e una metrica associate, che forniscono le chiavi per interpretare i dati visualizzati nella mappa di processo.

Le impostazioni predefinite per le dimensioni e la metrica di una mappa di processo dipendono dall&#39;applicazione Workbench dati in uso. Per informazioni sulle dimensioni e le metriche disponibili per le mappe dei processi, consultare la guida dell&#39;applicazione per l&#39;applicazione Workbench dati.

* **Dimensione di base:** Quando trascinate un elemento su una mappa di processo, trascinate e rilasciate un elemento della dimensione di base.
* **Dimensione livello:** Ogni dimensione nel set di dati ha una dimensione di livello associata (detta anche padre). La dimensione del livello per la mappa di processo deve corrispondere alla dimensione del livello (o elemento padre) per la dimensione di base della mappa di processo. Ad esempio, se trascinate una pagina (un elemento della dimensione Pagina) sulla mappa, la dimensione del livello corrispondente sarà Visualizzazione pagina.
* **Dimensione gruppo:** La dimensione del gruppo determina il modo in cui gli elementi della dimensione del livello vengono raggruppati per formare le connessioni tra i nodi. Per le mappe di processo, la dimensione del gruppo è importante per tre motivi principali:

   * Una connessione tra due nodi non può estendersi su più di un elemento di una dimensione gruppo. Per comprendere questo aspetto, prendere in considerazione un esempio di utilizzo di dati Web. Supponiamo che le dimensioni di base, livello e gruppo per la mappa di processo siano rispettivamente Pagina, Visualizzazione pagina e Sessione. Una connessione tra la pagina A e la pagina B indica che, durante una singola sessione, si è verificata una visualizzazione della pagina A prima della visualizzazione della pagina B senza alcuna visualizzazione della pagina intermedia di altre pagine (nodi) sulla mappa. Si noti che le visualizzazioni di pagina di altre pagine del sito potrebbero essersi verificate tra le visualizzazioni di pagina per le pagine A e B durante la stessa sessione, ma queste pagine non sono visualizzate su questa mappa.
   * Una connessione tra due nodi può rappresentare più elementi della dimensione del gruppo. Ad esempio, potrebbero essere presenti più sessioni in cui si è verificata una visualizzazione della pagina A prima della visualizzazione della pagina B. Di conseguenza, la connessione tra la pagina A e la pagina B rappresenta tutte le sessioni individuali in cui si è verificata una visualizzazione di pagina della pagina A prima della visualizzazione di pagina B, senza alcuna visualizzazione di pagina interveniente di altre pagine (nodi) sulla mappa.
   * Quando si effettua una selezione basata su un nodo all&#39;interno di una mappa di processo, si selezionano tutti gli elementi della dimensione del gruppo che hanno interessato tale nodo. Consulta [Selezione in Visualizzazioni](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746). Per informazioni sulle selezioni, consulta [Effettuare selezioni in Visualizzazioni](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

* **Metrica:** La dimensione del nodo per un dato elemento è proporzionale al valore della metrica per quell&#39;elemento. I nodi più grandi indicano valori di metrica maggiori rispetto ai nodi più piccoli.

Ad esempio, se si utilizza l’applicazione [!DNL Site] o HBX, è possibile trascinare, per impostazione predefinita, elementi della dimensione Pagina nella mappa del processo. La dimensione di ciascun nodo è correlata alla quantità di sessioni (definita dalla metrica Sessioni) in cui è stata visualizzata la pagina.

>[!NOTE]
>
>È possibile modificare le dimensioni o la metrica predefinite per una mappa di processo. Per i passaggi necessari per configurare una mappa di processo, consultate [Configurazione delle mappe](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6)di processo.

