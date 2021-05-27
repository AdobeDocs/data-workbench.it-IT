---
description: Un set di dati di Adobe contiene i dati caricati ed elaborati dal server di Data Workbench.
title: Informazioni sulla costruzione del set di dati
uuid: 540d159d-3f72-49dd-9929-107f1fc62b2b
exl-id: 111e98b5-d899-4f79-90ce-70f520d527d6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 0%

---

# Informazioni sulla costruzione del set di dati{#understanding-dataset-construction}

Un set di dati di Adobe contiene i dati caricati ed elaborati dal server di Data Workbench.

I passaggi necessari per il caricamento e l’elaborazione dei dati da parte del server di Data Workbench (InsightServer64.exe) costituiscono il processo di costruzione del set di dati.

>[!NOTE]
>
>Un server di Data Workbench che elabora e invia dati da un set di dati di Adobe è denominato unità di elaborazione dati o DPU. A volte viene definito server di elaborazione o server di query. I client Data Workbench e [!DNL Report] interagiscono direttamente con le DPU.

Durante la costruzione del set di dati, il server di Data Workbench legge i dati di origine dalle origini del registro, applica le trasformazioni a campi di dati specifici e definisce le dimensioni estese da creare dai campi trasformati. Il processo di costruzione si svolge in due fasi: *Elaborazione log* e *Trasformazione*. Una volta costruito il set di dati, puoi utilizzare le dimensioni estese del set di dati per creare metriche e dimensioni derivate per scopi di analisi specifici.

La costruzione del set di dati è come un processo di produzione. Selezionare i dati (le materie prime) da utilizzare per creare il set di dati e definire le trasformazioni di dati (le fasi del processo) che manipolano le informazioni disponibili nei dati per creare dimensioni estese (i prodotti fabbricati).

<!--
c_log_proc.xml
-->

I registri vengono filtrati e i campi di dati da trasmettere alla fase di trasformazione sono identificati. Al termine della fase di elaborazione del registro, i dati vengono raggruppati per ID di tracciamento (cioè, tutte le voci di registro con lo stesso ID di tracciamento sono raggruppate insieme) e ordinate nel tempo. Durante la fase di elaborazione del registro, non è possibile accedere ai dati elaborati da utilizzare per l’analisi.

## Specifica delle origini di registro {#section-75279dd6a7304d469735562796741d0f}

Le origini di registro sono file che contengono i dati da utilizzare per creare un set di dati. I dati disponibili nelle origini di registro sono chiamati dati evento perché ogni record di dati rappresenta un record di transazione o una singola istanza di un evento. Inoltre, ogni record o voce di registro contiene un valore noto come ID di tracciamento.

>[!NOTE]
>
>Quando selezioni le origini di registro, assicurati che ogni voce di registro contenga un ID di tracciamento per l’entità che rappresenti il livello più alto al quale devono essere raggruppati i dati. Ad esempio, se lavori con i dati raccolti dal traffico del sito web, è probabile che scegli che il visitatore sia questa entità. Ogni visitatore ha un ID di tracciamento univoco e tutti i dati su un particolare visitatore del sito possono essere raggruppati insieme. Per assistenza, contatta l&#39;Adobe.

I dati evento delle origini di registro vengono raccolti in tempo reale da [!DNL Sensors] o estratti da origini dati archiviate da Insight Server. I dati evento raccolti da Sensor da HTTP e da server applicazioni vengono trasmessi a Insight Server, che convertono i dati in file di log ( [!DNL .vsl]) altamente compressi. I dati evento contenuti in un file flat, in un file XML o in un&#39;origine dati ODBC vengono letti da Insight Server, che fornisce decodificatori definiti per estrarre un set comune di campi di registro da questi diversi formati.

## Definizione delle trasformazioni {#section-55a8cdb47379484081e53087f074778d}

Una trasformazione è un insieme di istruzioni che è possibile definire per estrarre o manipolare informazioni nei dati dell’evento. Ogni trasformazione definita viene applicata a ogni record di dati evento (voce di registro) per aggiornare i campi di registro esistenti o produrre nuovi campi. I risultati delle trasformazioni vengono utilizzati insieme alle condizioni di ingresso del registro per valutare quali voci di registro vengono filtrate fuori dal set di dati durante l’elaborazione del registro.

Non tutti i tipi di trasformazione possono essere utilizzati durante la fase di elaborazione del registro del processo di costruzione del set di dati.

## Registri di filtro {#section-6172ca0fb0eb4177925151bb49fdbc02}

Il set di dati contiene diversi parametri utilizzati per filtrare i dati che escono dalle trasformazioni. Il filtro viene utilizzato per specificare quali voci di registro vengono utilizzate nelle fasi di elaborazione successive. Ad esempio, i filtri possono essere definiti da, intervallo di tempo, lo stato della risposta del server o l&#39;indirizzo IP e le informazioni dell&#39;agente utente. Il [!DNL Log Entry Condition] è un test di filtro personalizzabile. Il test cerca alcune condizioni nei campi di ciascuna voce di registro per determinare se tale voce debba procedere ulteriormente nel processo di costruzione del set di dati. Se una voce di registro non soddisfa la condizione, la voce viene rimossa dal processo di costruzione.

## Identificazione dei campi per la trasformazione {#section-eef98ca723e54547b887aefdf0514c47}

Se un campo di dati deve essere passato dalla fase di elaborazione del registro alla fase di trasformazione per un&#39;ulteriore elaborazione, è necessario identificarlo durante l&#39;elaborazione del registro. Questo requisito si applica a prescindere dal fatto che il campo sia disponibile dalle origini di registro o creato da trasformazioni di dati applicate ai dati durante l’elaborazione del registro.

<!--
c_transformation.xml
-->

Durante la fase di trasformazione della costruzione del set di dati, l’elaborazione avviene sui dati raggruppati e ordinati che vengono emessi dall’elaborazione del registro. Vengono eseguite trasformazioni aggiuntive di dati e vengono create dimensioni dati estese da utilizzare nelle analisi. Durante la fase di trasformazione, è possibile accedere a un campione statistico dei dati che si ingrandisce man mano che la fase di trasformazione si avvicina al completamento.

## Definizione delle trasformazioni {#section-001b3fd4c1dd4dd38a5536872bc9de68}

Puoi definire le trasformazioni da utilizzare durante la fase di trasformazione del processo di costruzione del set di dati per facilitare la creazione delle dimensioni estese. Ogni trasformazione viene applicata a ogni record di dati evento (voce di registro) passato dall’elaborazione del registro.

## Registri di filtro {#section-3fed0a00ca344a719b5e8db363f64f06}

È possibile applicare [!DNL Log Entry Condition] durante la trasformazione per cercare condizioni specifiche nei campi di ogni voce di registro proveniente dall’elaborazione del registro. Se una voce di registro non soddisfa la condizione, la voce viene rimossa dal processo di costruzione.

## Definizione delle dimensioni estese {#section-25efafd0bfc84c86b9717d453a88c91b}

Le dimensioni estese sono i prodotti finali del processo di costruzione del set di dati. Rappresentano relazioni tra i campi del registro nei dati. Puoi utilizzarli per creare visualizzazioni, generare metriche estese o eseguire analisi per comprendere le operazioni e i problemi specifici della tua azienda.
