---
description: Un dataset Adobe contiene i dati caricati ed elaborati dal server workbench dati.
solution: Analytics
title: Informazioni sulla costruzione del set di dati
topic: Data workbench
uuid: 540d159d-3f72-49dd-9929-107f1fc62b2b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informazioni sulla costruzione del set di dati{#understanding-dataset-construction}

Un dataset Adobe contiene i dati caricati ed elaborati dal server workbench dati.

Le fasi di caricamento ed elaborazione dei dati da parte del server workbench dati (InsightServer64.exe) costituiscono il processo di costruzione del dataset.

>[!NOTE]
>
>Un server workbench dati che elabora e invia dati da un dataset Adobe è denominato unità di elaborazione dati o DPU. Talvolta viene definito server di elaborazione o server di query. Workbench dati e [!DNL Report] client interagiscono direttamente con gli UPU.

Durante la costruzione del dataset, il server workbench dati legge i dati di origine dalle origini log, applica le trasformazioni a campi di dati specifici e definisce le dimensioni estese da creare dai campi trasformati. Il processo di costruzione si svolge in due fasi: Elaborazione *e* trasformazione dei ** registri. Una volta costruito il set di dati, puoi utilizzare le dimensioni estese del set di dati per creare metriche e dimensioni derivate a scopi di analisi specifici.

La costruzione del set di dati è come un processo di produzione. Selezionare i dati (le materie prime) da utilizzare per creare il dataset e definire le trasformazioni di dati (le fasi del processo) che manipolano le informazioni disponibili nei dati per creare dimensioni estese (i prodotti fabbricati).

<!--
c_log_proc.xml
-->

I registri vengono filtrati e i campi di dati da passare alla fase di trasformazione sono identificati. Al termine della fase di elaborazione del registro, i dati vengono raggruppati per ID di tracciamento (tutte le voci di registro con lo stesso ID di tracciamento vengono raggruppate) e ordinati nel tempo. Durante la fase di elaborazione del registro, non è possibile accedere ai dati elaborati da utilizzare per l&#39;analisi.

## Specifica delle origini di registro {#section-75279dd6a7304d469735562796741d0f}

Le origini di registro sono file che contengono i dati da utilizzare per creare un dataset. I dati disponibili nelle origini del registro sono denominati dati evento perché ogni record di dati rappresenta un record di transazione o una singola istanza di un evento. Inoltre, ogni record o voce di registro contiene un valore denominato ID di tracciamento.

>[!NOTE]
>
>Quando selezionate le origini di registro, accertatevi che ciascuna voce di registro contenga un ID di tracciamento per l&#39;entità che deve rappresentare il livello più alto al quale i dati devono essere raggruppati. Ad esempio, se state lavorando con i dati raccolti dal traffico del sito Web, è probabile che sceglierete il visitatore come questa entità. Ogni visitatore ha un ID di tracciamento univoco e tutti i dati su un particolare visitatore del sito possono essere raggruppati insieme. Per assistenza, contattate Adobe.

I dati evento delle origini di registro vengono raccolti in tempo reale da [!DNL Sensors] o estratti da origini dati archiviate da Insight Server. I dati degli eventi raccolti dai Sensor dai server HTTP e applicativi vengono trasmessi ai server Insight, che convertono i dati in file di registro ( [!DNL .vsl]) altamente compressi. I dati evento contenuti in un file semplice, in un file XML o in un&#39;origine dati ODBC vengono letti da Insight Server, che fornisce i decodificatori definiti per estrarre un set comune di campi di registro da questi diversi formati.

## Definizione delle trasformazioni {#section-55a8cdb47379484081e53087f074778d}

Una trasformazione è un insieme di istruzioni che è possibile definire per estrarre o manipolare informazioni nei dati dell&#39;evento. Ogni trasformazione definita viene applicata a ciascun record di dati dell&#39;evento (voce di registro) per aggiornare i campi di registro esistenti o generare nuovi campi. I risultati delle trasformazioni vengono utilizzati insieme alle condizioni di immissione del registro per valutare quali voci di registro vengono filtrate dal dataset durante l&#39;elaborazione del registro.

Non tutti i tipi di trasformazioni possono essere utilizzati durante la fase di elaborazione del log del processo di costruzione del dataset.

## Filtrare I Registri {#section-6172ca0fb0eb4177925151bb49fdbc02}

Il set di dati contiene diversi parametri utilizzati per filtrare i dati che escono dalle trasformazioni. Il filtro viene utilizzato per specificare quali voci di registro vengono utilizzate nelle fasi di elaborazione successive. Ad esempio, i filtri possono essere definiti da, intervallo di tempo, lo stato della risposta del server o l&#39;indirizzo IP e le informazioni dell&#39;agente utente. È [!DNL Log Entry Condition] un test di filtraggio personalizzabile. Il test cerca determinate condizioni nei campi di ciascuna voce di registro per determinare se tale voce debba proseguire ulteriormente nel processo di costruzione del set di dati. Se una voce di registro non soddisfa la condizione, la voce viene rimossa dal processo di costruzione.

## Identificazione dei campi per la trasformazione {#section-eef98ca723e54547b887aefdf0514c47}

Se un campo di dati deve essere passato dalla fase di elaborazione del registro alla fase di trasformazione per un&#39;ulteriore elaborazione, è necessario identificarlo durante l&#39;elaborazione del registro. Questo requisito si applica indipendentemente dal fatto che il campo sia disponibile dalle origini di registro o creato da trasformazioni di dati applicate ai dati durante l&#39;elaborazione del registro.

<!--
c_transformation.xml
-->

Durante la fase di trasformazione della costruzione del dataset, l&#39;elaborazione avviene sui dati raggruppati e ordinati che vengono emessi dall&#39;elaborazione del log. Vengono eseguite ulteriori trasformazioni di dati e vengono create ulteriori dimensioni di dati da utilizzare nelle analisi. Durante la fase di trasformazione, è possibile accedere a un campione statistico dei dati che si ingrandisce man mano che la fase di trasformazione si avvicina al completamento.

## Definizione delle trasformazioni {#section-001b3fd4c1dd4dd38a5536872bc9de68}

È possibile definire le trasformazioni da utilizzare durante la fase di trasformazione del processo di costruzione del dataset per facilitare la creazione delle dimensioni estese. Ogni trasformazione viene applicata a ciascun record di dati dell&#39;evento (voce di registro) passato dall&#39;elaborazione del registro.

## Filtrare I Registri {#section-3fed0a00ca344a719b5e8db363f64f06}

È [!DNL Log Entry Condition] possibile applicare l’applicazione durante la trasformazione per cercare condizioni specifiche nei campi di ciascuna voce di registro proveniente dall’elaborazione del registro. Se una voce di registro non soddisfa la condizione, la voce viene rimossa dal processo di costruzione.

## Definizione delle dimensioni estese {#section-25efafd0bfc84c86b9717d453a88c91b}

Le dimensioni estese sono i prodotti finali del processo di costruzione del set di dati. Rappresentano le relazioni tra i campi di registro nei dati. Puoi utilizzarli per creare visualizzazioni, generare metriche estese o eseguire analisi per comprendere le operazioni e i problemi specifici della tua attività.
