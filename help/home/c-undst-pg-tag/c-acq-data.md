---
description: Il sensore consente di acquisire i dati della richiesta web (dati evento o registro) e i dati di misurazione estesi.
title: Che tipo di dati posso acquisire?
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
exl-id: 97d87084-cac3-4a94-89e0-f01a66e20324
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 2%

---

# Che tipo di dati posso acquisire?{#what-kind-of-data-can-i-acquire}

Il sensore consente di acquisire i dati della richiesta web (dati evento o registro) e i dati di misurazione estesi.

I dati di misurazione estesi non sono disponibili per i server web come parte del loro normale funzionamento.

Vengono descritti i seguenti argomenti:

## Dati richiesta Web {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] consente di acquisire e trasportare automaticamente i dati della richiesta web (dati di evento o di registro) in una posizione centrale per lo storage e il trattamento ai fini dell&#39;analisi. A meno che tu non scelga specificamente di filtrare determinati tipi di richieste e non raccolga dati su tali tipi di richieste, [!DNL Sensor] acquisisce dati su tutte le richieste di GET effettuate sui server web in cui è installato.

[!DNL Sensor] automatizza questo processo di acquisizione dei dati per tutte le richieste di GET effettuate sui server e presenta vantaggi tecnici e aziendali significativi rispetto ai metodi alternativi di acquisizione dei dati di richiesta dei siti web. Questi vantaggi includono:

* Le richieste non necessarie per l’analisi e la generazione di rapporti possono essere filtrate prima di sostenere i costi di acquisizione, trasporto, archiviazione ed elaborazione.
* Gli amministratori del sito non devono ruotare i file di registro in batch, manualmente o tramite script.
* [!DNL Sensor] aggrega i file di registro in una posizione centrale per consentire un accesso facile all’elaborazione.
* [!DNL Sensor] organizza e archivia i file di registro in un formato comune per il mantenimento dei dati, eliminando la necessità di preelaborarli prima di poter essere utilizzati a scopo di analisi e reporting.
* Le istanze di determinati tipi di contenuto possono essere incluse nei file di registro anche se la maggior parte delle richieste per un determinato tipo di contenuto vengono filtrate automaticamente.
* [!DNL Sensor] comprime le voci dei file di log, che richiedono uno spazio di archiviazione notevolmente inferiore, riducendo i costi e consentendo di mantenere i dati disponibili per l&#39;analisi per periodi di tempo più lunghi.
* [!DNL Sensor’s] le funzioni a tolleranza di errore consentono errori di sistema e di rete, garantendo al contempo la trasmissione dei dati di log a un archivio centrale.
* [!DNL Sensor] consente l’implementazione di esperimenti controllati con contenuti web, processi e campagne di marketing.
* [!DNL Sensor] le voci del registro vengono stampate in unità da 100 ns, consentendo nuovi tipi di funzionalità analitiche.
* [!DNL Sensor] consente ai proprietari del sito di aggiungere dati (misurazioni) alle voci di registro dopo l&#39;implementazione iniziale per essere presi in considerazione in analisi e reporting.

Per ulteriori informazioni sull&#39;acquisizione di dati di misurazione estesi, vedere [Acquisizione delle misurazioni della linea di base](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe).

## Dati di misurazione estesi {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] supporta anche l’uso di tag pagina (o richieste di oggetti incorporati) per acquisire dati di misurazione non disponibili per i server web come parte del loro normale funzionamento. I tag pagina vengono comunemente utilizzati per misurare:

* Visualizzazione di una pagina logica in un sito web dinamico.
* La visualizzazione di contenuti o annunci su un sito web controllato da terze parti.
* Visualizzazione del contenuto distribuito da una cache del browser o CDN.
* Informazioni dettagliate sul browser di un visitatore, comprese misurazioni quali il tempo di caricamento della pagina, la risoluzione dello schermo, i campi del modulo compilati dal visitatore e così via.
* Altri dati che non vengono altrimenti inviati dai browser ai server web.

[!DNL Sensor] raccoglie tutte le informazioni inserite in qualsiasi richiesta di GET effettuata a un server web in esecuzione  [!DNL Sensor]. Tali richieste possono provenire da richieste di oggetti incorporati di qualsiasi tipo, sia per misurare semplicemente che la richiesta è stata effettuata in un certo momento da un determinato browser o per trasmettere altri dati di misurazione nel flusso di raccolta dei dati in modo che possa essere elaborata a scopo di analisi e reporting.

[!DNL Sensor] offre il meglio sia sul lato client che sul lato server: acquisisce i dati dei log web lato server e raccoglie le misurazioni relative al busting della cache, lato client, o sito di terze parti, eseguite dalle richieste di oggetti incorporati. In altre parole, [!DNL Sensor] acquisisce sia i dati di richiesta normalmente noti ai tuoi server web (misurazioni lato server) sia i dati di misurazione aggiuntivi raccolti tramite l&#39;uso di tag di pagina (misurazioni lato client) che inviano i loro dati a qualsiasi server web che esegue [!DNL Sensor]. Tali server web possono essere dedicati alla raccolta delle misurazioni lato client, ma non sono tenuti ad esserlo.

Per ulteriori informazioni sull&#39;acquisizione di dati di misurazione estesi, consulta [Acquisizione di misurazioni estese](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944).
