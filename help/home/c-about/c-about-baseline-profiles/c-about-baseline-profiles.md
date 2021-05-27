---
description: È stato creato un set di profili standard per ogni applicazione per consentire l’installazione di uno o più profili in un dato momento.
title: Profili della linea di base
uuid: ff76ff7e-ccde-4d99-9109-8612a4a83183
exl-id: f1bd5c1d-5f79-4b8c-9928-97169d553631
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Profili della linea di base{#baseline-profiles}

È stato creato un set di profili standard per ogni applicazione per consentire l’installazione di uno o più profili in un dato momento.

Questi profili di base includono le definizioni di metriche, dimensioni, filtri, rapporti, aree di lavoro e dashboard standard. L&#39;Adobe aggiorna continuamente questi profili e li rende disponibili ai propri licenziatari attraverso il suo programma di supporto software. Inoltre, gli utenti di applicazioni Adobe possono definire profili aggiuntivi e utilizzarli con o invece dei profili forniti da Adobe.

Il sistema di gestione dei profili consente di ignorare le configurazioni di un profilo in base a profili di livello superiore. Utilizza questa funzione quando desideri ignorare una delle definizioni incorporate in questi profili dopo l’installazione. L’installazione di nuove versioni di questi profili sovrascrive le versioni precedenti. Di conseguenza, tutte le modifiche apportate direttamente a questi profili verranno sovrascritte quando vengono installati i nuovi profili.

Possono essere disponibili profili per mercati verticali o tipi specifici di aziende o industrie anche da Adobe ClientCare. Di seguito sono riportate le descrizioni dei profili della linea di base:

* Il **profilo di base** include i file di configurazione forniti con Insight Server. Il profilo di base non deve essere modificato dall&#39;utente o dall&#39;amministratore. Qualsiasi modifica apportata nel profilo di base è soggetta a sovrascrittura quando Adobe rilascia una versione successiva di Insight Server o di un’altra applicazione software.
* Il **profilo traffico** include un set di metriche, dimensioni e filtri fondamentali per l’analisi web. Include inoltre aree di lavoro, rapporti e dashboard dei modelli che facilitano l’analisi, la generazione di rapporti e la comprensione generale delle tendenze e dei pattern complessivi di attività del sito Internet. Questo profilo funziona &quot;preconfigurato&quot; con un’installazione di base del sito.
* Il **profilo valore** include un set di metriche e dimensioni e aree di lavoro, rapporti e dashboard dei modelli associati al valore aziendale del sito e al modello di conversione incorporati. Questo profilo consente agli utenti di identificare gli eventi di valore sul sito e di associare un valore monetario a tali eventi.

   Questo profilo espande le funzionalità di analisi del sito fornendo un Business Value Model, un metodo avanzato per misurare e monitorare la quantità di valore generato dal sito. Gli eventi valore e il relativo valore sono definiti tramite una semplice interfaccia di trascinamento all’interno di Site. Il sito utilizza queste definizioni per calcolare il valore aziendale generato da ogni sessione e queste informazioni vengono utilizzate a loro volta per definire metriche quali valori, eventi di valore, conversione e così via. Queste metriche consentono di rispondere a domande quali:

   * Qual è il percorso più redditizio attraverso il sito?
   * Quale referente o campagna ha generato il maggior valore?
   * Qual è il numero medio di acquisti al giorno sul sito? (Quanti eventi di valore si verificano in media al giorno?)

   Dopo aver definito un modello di valore aziendale nel sito, puoi utilizzare le metriche e le dimensioni Valore nell’analisi.

* Il **profilo di marketing** include set di metriche e dimensioni e aree di lavoro dei modelli, rapporti e dashboard associati all&#39;analisi delle campagne di marketing Internet, inclusa l&#39;analisi di ricerca e l&#39;analisi estesa dei referenti.

L’Adobe fornisce anche i seguenti profili facoltativi da utilizzare:

* Il **profilo di geolocalizzazione IP** include dimensioni e file di livello relativi all’analisi delle posizioni dei visitatori in base ai dati di geolocalizzazione IP forniti ad Adobe da Quova, Inc. e incorporati in Data Workbench.
* Il profilo di intelligenza IP include dimensioni e file di livello relativi all’analisi delle posizioni dei visitatori in base ai dati di intelligenza IP forniti ad Adobe da Digital Envoy, Inc. e incorporati in Data Workbench.

Per informazioni sui profili IP-Geo-location e IP Geo-intelligence, contatta il personale di supporto Adobe. Le sezioni seguenti descrivono le metriche e le dimensioni definite in ciascuno dei profili della linea di base.
