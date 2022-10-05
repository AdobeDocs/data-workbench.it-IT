---
description: Sensor è costituito da tre componenti principali Data Collector, Disk Queue e Data Transmitter.
title: Componenti di base
uuid: 32e6e8d9-90ee-4db1-8883-dbdf245df26f
exl-id: aee6a601-590a-43e0-aeeb-42a4522e55c8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 0%

---

# Componenti di base{#what-are-basic-components}

{{eol}}

Il sensore è costituito da tre componenti principali: Agente di raccolta dati, coda disco e trasmettitore dati.

![](assets/Visual-Sensor.png)

## Raccoglitore dati {#section-f970eaff30364a3c8106d5ec9c1b5caa}

Il raccoglitore di dati (collettore) è un modulo NSAPI, ISAPI, servlet di filtro J2EE o Apache che viene eseguito all’interno del processo del server web.

Acquisisce i dati dell&#39;evento non elaborati relativi a ogni richiesta HTTP elaborata dal server web e li deposita nella coda del disco. Se esegui più istanze di un server web sullo stesso computer, ogni istanza carica la propria istanza del modulo di raccolta; tuttavia, tutte le istanze del raccoglitore scrivono i propri dati evento nella stessa coda del disco.

## Coda disco {#section-41aac77ab30e48478d1b31eac288df05}

La coda del disco (coda) è un file di coda con mappatura della memoria FIFO (primo in, primo out) che memorizza in buffer i dati dell&#39;evento non elaborati raccolti da Sensor, fornendo la memorizzazione temporanea per i dati dell&#39;evento raccolti sul server Web in cui è installato.

Per evitare che la coda si espanda senza vincoli (e quindi consuma tutto lo spazio su disco disponibile), la coda viene mantenuta in un file a dimensione fissa, il che significa che contiene solo la quantità di dati evento che gli è stata data la capacità di contenere. La dimensione del file della coda è configurata nel parametro QueueSize del file di configurazione Sensor, txlogd.conf, quando è installato Sensor. Per informazioni sui parametri txlogd.conf, consulta Parametri del file Sensor Txlogd.conf .

Una volta stabilita, la lunghezza fisica del file non cresce o si riduce. Il raccoglitore semplicemente deposita i nuovi dati dell&#39;evento nella coda e il trasmettitore estrae gli eventi da esso. Se il raccoglitore raggiunge la fine del file, smette di scrivere nel file della coda.

Generalmente, il trasmettitore estrae gli eventi dalla coda rapidamente come il collettore li deposita. Tuttavia, se la connessione tra il trasmettitore e Insight Server è lenta o non disponibile, la coda può riempire con eventi non trasmessi. In questo caso, il raccoglitore smette di raccogliere i dati finché il trasmettitore non disegna la coda. Le informazioni sulle richieste che il server web elabora durante questo periodo di tempo vengono perse definitivamente.

**Determinazione della dimensione della coda**

Prima di installare Sensor, è necessario determinare la dimensione della coda. Per evitare la perdita permanente di dati, è importante creare una coda sufficientemente grande da contenere il numero di eventi che potrebbero accumularsi durante l’interruzione più lunga e probabile della connessione a Insight Server (ovvero, archiviazione sufficiente per diversi giorni di attività di picco). La coda deve essere configurata in modo da contenere dati evento sufficienti per consentire agli amministratori di sistema di ripristinare l’accessibilità di rete a Target Insight Server oppure per ripristinare o sostituire Insight Server senza perdere dati. Se il sensore non è riuscito e non è disponibile un file di coda valido e accessibile per contenere i dati dell&#39;evento, i dati successivi andranno persi.

>[!NOTE]
>
>È importante che gli amministratori di ogni computer su cui viene eseguito Sensor comprendano la natura unica del file di coda locale per assicurarsi che non lo tratti come un file di log ordinario che può essere eliminato, archiviato o compresso.

L&#39;Adobe consiglia di configurare la coda in modo da contenere almeno dieci (10) giorni di picco di dati evento prodotti dal server in cui è installato il sensore. Cioè, prendete la quantità di dati dell&#39;evento da qualsiasi giorno di picco nell&#39;ultimo anno e moltiplicatela per dieci.

Questa raccomandazione presuppone quanto segue:

* Il team IT della tua azienda sta monitorando ogni sensore nel modo descritto in Sensore di amministrazione di questa guida e lo sta facendo almeno una volta al giorno. In caso contrario, tale periodo dovrebbe essere opportunamente prorogato.
* Il team di Information Technology della tua azienda è in grado di ripristinare l’accessibilità della rete o sostituire o riparare qualsiasi Insight Server installato entro 72 ore. In caso contrario, tale periodo dovrebbe essere opportunamente prorogato.
* La configurazione del sensore rimane la stessa.
* Nessun evento esterno (ad esempio, una campagna di marketing di grandi dimensioni) farà aumentare in modo significativo la quantità di dati evento generati dai server web.

La scelta della dimensione della coda dipende in larga misura dal livello desiderato di monitoraggio del sistema alla luce delle pratiche e delle politiche aziendali in materia di tempi di risposta e amministrazione del sistema weekend/ferie. Poiché le dimensioni di coda più grandi sono migliori, l’Adobe consiglia all’azienda di ingrandire la coda il più possibile.

>[!NOTE]
>
>Dimensioni file in coda più grandi non hanno alcun impatto sulle prestazioni.

Per ulteriori raccomandazioni sul ridimensionamento della coda, contatta Adobe Consulting Services.

## Trasmettitore dati {#section-2dc03d37d73b4cc6bdd5af6b346350d4}

Il trasmettitore è un processo indipendente (ad esempio, un daemon su un computer basato su UNIX o un servizio su un computer Windows) che viene eseguito sullo stesso computer del server Web.

Il trasmettitore legge i dati dell&#39;evento dalla coda del disco, li comprime e li invia tramite HTTP/S a Insight Server specificato, dove viene elaborato e memorizzato in **.vsl** file.
