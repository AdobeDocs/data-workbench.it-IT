---
description: È stato creato un set di profili standard per ciascuna applicazione per consentire l'installazione di uno o più profili in un dato momento.
solution: Analytics
title: Profili di base
topic: Data workbench
uuid: ff76ff7e-ccde-4d99-9109-8612a4a83183
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Profili di base{#baseline-profiles}

È stato creato un set di profili standard per ciascuna applicazione per consentire l’installazione di uno o più profili in un dato momento.

Questi profili di base includono le definizioni di metriche standard, dimensioni, filtri, rapporti, aree di lavoro e dashboard. Adobe aggiorna continuamente questi profili e li rende disponibili ai propri licenziatari attraverso il suo programma di supporto software. Inoltre, gli utenti delle applicazioni Adobe possono definire profili aggiuntivi e utilizzarli con o invece dei profili forniti da Adobe.

Il sistema di gestione dei profili consente di sovrascrivere le configurazioni di un profilo con profili di livello superiore. Utilizzate questa funzione quando desiderate ignorare una delle definizioni incorporate in questi profili dopo che sono stati installati. L&#39;installazione di nuove versioni di questi profili sovrascriverà tutte le versioni precedenti. Di conseguenza, eventuali modifiche apportate direttamente a tali profili verranno sovrascritte al momento dell&#39;installazione dei nuovi profili.

Possono essere disponibili profili per mercati verticali o tipi specifici di società o industrie anche da Adobe ClientCare. Di seguito sono riportate le descrizioni dei profili di base:

* Il profilo **** Base include i file di configurazione forniti con Insight Server. Il profilo di base non deve essere modificato dall&#39;utente o dall&#39;amministratore. Eventuali modifiche apportate al profilo di base sono soggette a sovrascrittura quando Adobe rilascia una versione successiva di Insight Server o un&#39;altra applicazione software.
* Il profilo **** Traffico include una serie di metriche, dimensioni e filtri fondamentali per l&#39;analisi Web. Include inoltre aree di lavoro modello, rapporti e dashboard che semplificano l&#39;analisi, la generazione di rapporti e la comprensione generale delle tendenze e dei modelli generali dell&#39;attività del sito Internet. Questo profilo funziona &quot;out-of-the-box&quot; con un&#39;installazione di base di Site.
* Il profilo **** Valore include un insieme di metriche e dimensioni e aree di lavoro, report e dashboard dei modelli associati al valore aziendale e al modello di conversione incorporati di Site. Questo profilo consente agli utenti di identificare gli eventi di valore sul sito e di associare un valore monetario a tali eventi.

   Questo profilo espande le capacità di analisi del sito fornendo un Business Value Model, un metodo avanzato per misurare e monitorare la quantità di valore generato dal sito. Gli eventi di valore e il relativo valore sono definiti tramite una semplice interfaccia di trascinamento all&#39;interno di Site. Site utilizza queste definizioni per calcolare il valore aziendale generato da ogni sessione, e queste informazioni vengono utilizzate a loro volta per definire metriche quali eventi di valore, conversione e così via. Queste metriche consentono di rispondere a domande quali:

   * Qual è il percorso più redditizio attraverso il sito?
   * Quale referente o campagna ha generato il maggior valore?
   * Qual è il numero medio di acquisti al giorno sul sito? (Quanti eventi di valore si verificano giornalmente in media?)
   Dopo aver definito un Business Value Model nel sito, puoi utilizzare le metriche e le dimensioni Valore nell&#39;analisi.

* Il profilo **** Marketing include un insieme di metriche e dimensioni e aree di lavoro modello, rapporti e dashboard associati all&#39;analisi delle campagne di marketing Internet, inclusa l&#39;analisi di ricerca e l&#39;analisi estesa dei referenti.

Adobe fornisce inoltre i seguenti profili facoltativi da usare:

* Il profilo **Geolocalità** IP include dimensioni e file di livello correlati all’analisi delle posizioni dei visitatori in base ai dati di geolocalità IP forniti ad Adobe da Quova, Inc. e incorporati nel workbench dati.
* Il profilo di intelligenza IP include dimensioni e file di livello correlati all&#39;analisi delle posizioni dei visitatori in base ai dati di intelligenza IP forniti ad Adobe da Digital Envoy, Inc. e incorporati nel workbench dati.

Per informazioni sui profili IP-Geo-location e IP Geo-intelligence, contattate il personale di supporto di Adobe. Le sezioni seguenti descrivono le metriche e le dimensioni definite in ciascuno dei profili di base.
