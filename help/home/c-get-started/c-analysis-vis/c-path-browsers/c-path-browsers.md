---
description: Un browser di percorsi consente di analizzare la sequenza in cui è stato effettuato l’accesso agli elementi di una particolare dimensione.
solution: Analytics
title: Browser percorso
topic: Data workbench
uuid: 548091dc-935f-41ac-b67c-39080988f1ea
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Browser percorso{#path-browsers}

Un browser di percorsi consente di analizzare la sequenza in cui è stato effettuato l’accesso agli elementi di una particolare dimensione.

Per creare un browser di percorsi, trascinate e rilasciate un elemento di una dimensione su una visualizzazione browser di percorsi vuota. L’elemento trascinato e rilasciato nel browser Percorsi diventa la directory principale del browser Percorsi. Il browser dei percorsi visualizza i percorsi che passano attraverso il livello principale, consentendo di visualizzare la sequenza di elementi a cui si è effettuato l&#39;accesso prima e dopo il livello principale.

Il seguente browser di percorsi mostra la sequenza di filmati che gli utenti hanno valutato prima e dopo il filmato *Aviator*, che è la radice del browser dei percorsi. Ogni nome del filmato è un elemento della dimensione Filmato, che è definita in un set di dati costituito da dati del filmato che include i nomi dei filmati e le valutazioni degli utenti di tali filmati.

![](assets/vis_PathBrowser_Movies.png)

È possibile creare browser di percorsi per mostrare la sequenza in cui sono stati accessibili gli elementi di qualsiasi dimensione del set di dati. Ad esempio, se state lavorando con i dati del sito Web, potete creare un browser di percorsi che mostri la sequenza di pagine del sito Web a cui è stato effettuato l’accesso prima e dopo la radice per ogni sessione in cui è stata visualizzata la radice o per ogni visitatore del sito che ha visualizzato la radice.

![](assets/vis_PathBrowser_Pages.png)

Ogni browser con percorsi ha una dimensione di base, una dimensione di gruppo, una dimensione di livello e una metrica associate, che forniscono le chiavi per interpretare i dati visualizzati nel browser percorsi.

* **Dimensione di base:** Quando si trascina e rilascia un elemento principale nel browser percorso, si trascina e rilascia un elemento della dimensione base. Tutti gli altri elementi visualizzati nei percorsi sono elementi della dimensione di base. È possibile modificare la dimensione di base trascinando e rilasciando un elemento di un’altra dimensione nel browser percorso.
* **Dimensione livello:** Ogni dimensione nel set di dati ha una dimensione di livello associata (detta anche padre). La dimensione del livello del browser percorso deve essere la stessa della dimensione di livello (o elemento padre) della dimensione di base del browser percorso. La dimensione a livello di browser percorso è importante per due motivi principali:

   * Seguendo un percorso da un elemento della dimensione di base a quello successivo, si passa da un elemento della dimensione di livello a quello successivo. Ad esempio, se avete creato un browser di percorsi con le pagine di un sito Web, Ogni pagina è un elemento della dimensione Pagina e la dimensione del livello per Pagina è Visualizzazione pagina. Quando si passa da una pagina all’altra, si passa da una vista a quella successiva.
   * Quando si seleziona un percorso di elementi dimensionali di base all&#39;interno di un browser percorso, si selezionano i dati per gli elementi corrispondenti della dimensione livello. La selezione include sempre gli elementi della dimensione del livello che si riferiscono al livello principale, ed è ridefinita aggiungendo più elementi al percorso. Ad esempio, quando si seleziona un percorso di pagine, ad esempio root > A > B, si selezionano i dati per le visualizzazioni di pagina associate al livello principale in cui la pagina successiva è A e la pagina successiva è B.

      Per informazioni sulla selezione di un percorso in un browser di percorsi, consultate [Selezione di percorsi](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/t-sel-paths.md#task-bf44d08c71954ef2adec4b82f840adeb). Per informazioni sulle selezioni, consulta [Effettuare selezioni in Visualizzazioni](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).
   >[!NOTE]
   >
   >Il browser Percorsi ignora gli elementi della dimensione del livello senza elementi della dimensione di base associati. Questa situazione può verificarsi quando si crea un browser di percorsi da una mappa di processo. Consultate [Creazione di browser](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-create-path-browsers.md#concept-e120de6a740d4b6f98dda9e2b638f6ff)di percorsi.

* **Dimensione gruppo:** La dimensione del gruppo determina il modo in cui gli elementi della dimensione del livello vengono raggruppati per formare i percorsi di un browser di percorsi. Nello specifico, gli elementi dimensione livello associati a un singolo percorso in un browser percorso non possono estendersi su più di un elemento di una dimensione gruppo.

   Per comprendere questo aspetto, prendere in considerazione un esempio di utilizzo di dati Web. Supponiamo che le dimensioni di base, livello e gruppo per il browser Percorsi siano rispettivamente Pagina, Visualizzazione pagina e Sessione. Un percorso nel browser dei percorsi mostra la sequenza di pagine A > B > C. La dimensione di gruppo (Sessione) indica che le visualizzazioni di pagina (elementi della dimensione Visualizzazione pagina) associate alla sequenza di pagine A > B > C si sono verificate durante una singola sessione. È importante notare che potrebbero essere presenti più sessioni durante le quali sono state visualizzate visualizzazioni di pagina per la sequenza di pagine A > B > C. Pertanto, il percorso che mostra la sequenza di pagine A > B > C rappresenta tutte le sessioni individuali in cui si sono verificate le visualizzazioni di pagina per quella sequenza.

* **Metrica**: Lo spessore del percorso che porta a un dato elemento è proporzionale al valore della metrica per tale elemento. I percorsi più spessi indicano valori di metrica maggiori rispetto a quelli più sottili.

L’etichetta nell’angolo in alto a sinistra del browser Percorsi indica le dimensioni di base e di gruppo rappresentate nella visualizzazione. Il nome della dimensione del livello non è visibile nella visualizzazione del browser percorso. L&#39;etichetta assume la forma &quot;Sequenza di nomi *+s della dimensione di* base per ciascun nome *della dimensione di* gruppo.&quot; Ad esempio, l’etichetta Sequenza di filmati per ogni utente indica che la dimensione di base è Filmato e la dimensione del gruppo è Utente.

![](assets/vis_PathBrowser_Movies.png)

Facendo clic con il pulsante destro del mouse su un elemento nel browser dei percorsi, puoi visualizzare il nome della metrica associata al browser dei percorsi e il relativo valore per tale elemento.

![](assets/vis_PathBrowser_RightClick.png)

>[!NOTE]
>
>Puoi modificare le dimensioni e la metrica predefinite per un browser di percorsi. Per istruzioni su come configurare la visualizzazione del browser dei percorsi, consulta [Configurazione dei browser](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3)dei percorsi.

