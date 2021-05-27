---
description: Un browser percorsi consente di analizzare la sequenza in cui è stato effettuato l’accesso agli elementi di una particolare dimensione.
title: Browser del percorso
uuid: 548091dc-935f-41ac-b67c-39080988f1ea
exl-id: 563cf0e3-39d7-49b7-b808-b0233169fb1a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 0%

---

# Browser del percorso{#path-browsers}

Un browser percorsi consente di analizzare la sequenza in cui è stato effettuato l’accesso agli elementi di una particolare dimensione.

Puoi creare un browser percorsi trascinando e rilasciando un elemento di una dimensione su una visualizzazione del browser percorsi vuota. L’elemento trascinato nel browser percorsi diventa la directory principale del browser percorsi. Il browser percorsi visualizza i percorsi che passano attraverso la radice, consentendo di vedere la sequenza di elementi a cui è stato effettuato l’accesso prima e dopo la radice.

Il seguente browser percorsi mostra la sequenza di filmati che gli utenti hanno valutato prima e dopo la valutazione del filmato *L&#39;Aviator*, che è la radice del browser percorsi. Ogni nome del filmato è un elemento della dimensione Filmato, che è definita in un set di dati costituito da dati relativi ai film che includono i nomi dei film e le valutazioni dei visualizzatori di tali filmati.

![](assets/vis_PathBrowser_Movies.png)

Puoi creare browser a percorsi per mostrare la sequenza di accesso agli elementi di qualsiasi dimensione nel set di dati. Ad esempio, se lavori con i dati del sito web, puoi creare un browser percorsi che mostri la sequenza di pagine del sito web a cui è stato effettuato l’accesso prima e dopo la directory principale per ogni sessione in cui è stata visualizzata la radice o per ogni visitatore del sito che ha visualizzato la radice.

![](assets/vis_PathBrowser_Pages.png)

Ogni browser del percorso ha una dimensione di base, una dimensione di gruppo, una dimensione di livello e una metrica associate, che forniscono chiavi per interpretare i dati visualizzati nel browser del percorso.

* **Dimensione di base:** quando trascini e rilascia un elemento principale nel browser percorsi, trascini e rilascia un elemento della dimensione di base. Tutti gli altri elementi visualizzati nei percorsi sono elementi della dimensione di base. Puoi modificare la dimensione di base trascinando e rilasciando un elemento di un’altra dimensione nel browser percorsi.
* **Dimensione livello:** ogni dimensione del set di dati presenta una dimensione di livello associata (detta anche dimensione principale). La dimensione del livello per il browser percorsi deve essere la stessa della dimensione di livello (o superiore) per la dimensione di base del browser percorsi. La dimensione a livello di browser del percorso è importante per due motivi principali:

   * Seguendo un percorso da un elemento dimensionale di base a quello successivo, ci si sposta da un elemento dimensionale di livello a quello successivo. Ad esempio, supponiamo di aver creato un browser percorsi che mostra le pagine di un sito web. Ogni pagina è un elemento della dimensione Pagina e la dimensione di livello per Pagina è Visualizzazione pagina. Mentre ci si sposta da una pagina all’altra, si passa dalla visualizzazione di una pagina a quella successiva.
   * Quando selezioni un percorso di elementi dimensionali di base all’interno di un browser percorsi, selezioni i dati per gli elementi corrispondenti della dimensione di livello. La selezione include sempre gli elementi della dimensione di livello che si riferiscono alla radice e viene perfezionata aggiungendo più elementi al percorso. Ad esempio, quando selezioni un percorso di pagine, come radice > A > B, selezioni i dati per le visualizzazioni di pagina associate alla pagina principale in cui la pagina successiva è A e la pagina successiva è B.

      Per informazioni sulla selezione di un percorso in un browser percorsi, consulta [Selezione di percorsi](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/t-sel-paths.md#task-bf44d08c71954ef2adec4b82f840adeb). Per informazioni sulle selezioni, consulta [Effettuare selezioni in Visualizations](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).
   >[!NOTE]
   >
   >Il browser percorsi ignora gli elementi della dimensione del livello senza elementi della dimensione di base associati. Questa situazione può verificarsi quando si crea un browser del percorso da una mappa del processo. Consulta [Creazione di browser del percorso](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-create-path-browsers.md#concept-e120de6a740d4b6f98dda9e2b638f6ff).

* **Dimensione gruppo:** la dimensione gruppo determina il modo in cui gli elementi della dimensione livello vengono raggruppati per formare i percorsi di un browser del percorso. In particolare, gli elementi dimensionali di livello associati a un singolo percorso in un browser percorsi non possono estendersi su più di un elemento di una dimensione di gruppo.

   Per comprendere questo aspetto, considera un esempio utilizzando i dati web. Supponiamo che le dimensioni di base, livello e gruppo per il browser percorsi siano rispettivamente Pagina, Visualizzazione pagina e Sessione. Un percorso nel browser percorsi mostra la sequenza di pagine A > B > C. La dimensione di gruppo (Sessione) indica che le visualizzazioni di pagina (elementi della dimensione Visualizzazione pagina) associate alla sequenza di pagine A > B > C si sono verificate durante una singola sessione. È importante notare che potrebbero esserci più sessioni durante le quali erano presenti visualizzazioni di pagina per la sequenza di pagine A > B > C. Pertanto, il percorso che mostra la sequenza di pagine A > B > C rappresenta tutte le singole sessioni in cui si sono verificate le visualizzazioni di pagina per quella sequenza.

* **Metrica**: Lo spessore del percorso che porta a un dato elemento è proporzionale al valore della metrica per tale elemento. I percorsi più spessi indicano valori di metrica maggiori rispetto ai percorsi più sottili.

L’etichetta nell’angolo in alto a sinistra del browser percorsi denomina le dimensioni di base e di gruppo rappresentate nella visualizzazione. Il nome della dimensione del livello non è visibile nella visualizzazione del browser del percorso. L’etichetta assume la forma di &quot;Sequenza di *nome della dimensione di base*+s per ciascun *nome della dimensione di gruppo*.&quot; Ad esempio, l’etichetta Sequenza di filmati per ogni utente indica che la dimensione di base è Filmato e la dimensione di gruppo è Utente.

![](assets/vis_PathBrowser_Movies.png)

Facendo clic con il pulsante destro del mouse su un elemento nel browser percorsi, puoi vedere il nome della metrica associata al browser percorsi e il relativo valore per tale elemento.

![](assets/vis_PathBrowser_RightClick.png)

>[!NOTE]
>
>Puoi modificare le dimensioni e la metrica predefinite per un browser percorsi. Per istruzioni su come configurare una visualizzazione del browser del percorso, consulta [Configurazione dei browser del percorso](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).
