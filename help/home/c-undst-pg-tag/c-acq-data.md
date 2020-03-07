---
description: Sensor consente di acquisire dati di richiesta Web (dati di evento o registro) e dati di misurazione estesi.
solution: Analytics
title: Che tipo di dati posso acquisire?
topic: Data workbench
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Che tipo di dati posso acquisire?{#what-kind-of-data-can-i-acquire}

Sensor consente di acquisire dati di richiesta Web (dati di evento o registro) e dati di misurazione estesi.

I dati di misurazione estesi non sono disponibili sui server Web come parte del normale funzionamento.

Sono descritti i seguenti argomenti:

## Dati richiesta Web {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] consente l&#39;acquisizione e il trasporto automatico dei dati delle richieste Web (dati di eventi o log) in una posizione centrale per l&#39;archiviazione e l&#39;elaborazione per l&#39;analisi. A meno che non si scelga in modo specifico di filtrare determinati tipi di richieste e di non raccogliere dati su tali tipi di richieste, [!DNL Sensor] acquisisce i dati su tutte le richieste GET effettuate dai server Web su cui è installato.

[!DNL Sensor] automatizza questo processo di acquisizione dei dati per tutte le richieste GET che vengono effettuate sui server e presenta vantaggi tecnici e aziendali significativi rispetto ai metodi alternativi per l&#39;acquisizione dei dati delle richieste dei siti Web. Tali vantaggi comprendono:

* Le richieste non necessarie per l&#39;analisi e la creazione di report possono essere filtrate prima di sostenere costi per l&#39;acquisizione, il trasporto, l&#39;archiviazione e l&#39;elaborazione.
* Gli amministratori del sito non devono ruotare i file di registro in batch, manualmente o tramite script.
* [!DNL Sensor] aggrega i file di registro in una posizione centrale per consentire un facile accesso all&#39;elaborazione.
* [!DNL Sensor] organizza e archivia i file di registro in un formato comune per il mantenimento dei dati, eliminando la necessità di preelaborarli prima che possano essere utilizzati a scopo di analisi e reporting.
* Le istanze di determinati tipi di contenuto possono essere incluse nei file di registro anche se la maggior parte delle richieste per un determinato tipo di contenuto vengono filtrate automaticamente.
* [!DNL Sensor] comprime le voci dei file di registro, che richiedono molto meno spazio di archiviazione, riducendo i costi e consentendo di mantenere i dati disponibili per l&#39;analisi per periodi di tempo più lunghi.
* [!DNL Sensor’s] le funzioni di tolleranza di errore consentono di correggere gli errori di sistema e di rete, garantendo al contempo la trasmissione dei dati di registro a un archivio centrale.
* [!DNL Sensor] consente l&#39;implementazione di esperimenti controllati con contenuti Web, processi e campagne di marketing.
* [!DNL Sensor] le voci del registro delle marche temporali sono in unità da 100 ns, consentendo nuovi tipi di funzionalità analitiche.
* [!DNL Sensor] consente ai proprietari del sito di aggiungere dati (misurazioni) alle voci di registro dopo l’implementazione iniziale per essere presi in considerazione nell’analisi e nella generazione dei rapporti.

Per ulteriori informazioni sull&#39;acquisizione di dati di misurazione estesi, vedere [Acquisizione di misurazioni](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe)di base.

## Dati di misurazione estesi {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] supporta inoltre l&#39;utilizzo di tag pagina (o richieste di oggetti incorporati) per acquisire dati di misurazione non disponibili sui server Web come parte del normale funzionamento. I tag pagina vengono comunemente utilizzati per misurare:

* Visualizzazione di una pagina logica in un sito Web dinamico.
* Visualizzazione di contenuti o annunci su un sito Web controllato da terze parti.
* Visualizzazione del contenuto distribuito dalla cache di un browser o dalla rete CDN.
* Informazioni dettagliate sul browser di un visitatore, comprese misure quali il tempo di caricamento della pagina, la risoluzione dello schermo, i campi modulo compilati dal visitatore e così via.
* Altri dati che non vengono altrimenti inviati dai browser ai server Web.

[!DNL Sensor] raccoglie tutte le informazioni inserite in qualsiasi richiesta GET effettuata a un server Web in esecuzione [!DNL Sensor]. Tali richieste possono provenire da richieste di oggetti incorporati di qualsiasi tipo, per misurare semplicemente che la richiesta è stata fatta in un certo momento da un determinato browser o per trasmettere altri dati di misurazione nel flusso di raccolta dei dati in modo che possa essere elaborata a fini di analisi e di reporting.

[!DNL Sensor] offre il meglio dei mondi di acquisizione dei dati lato client e lato server: acquisisce i dati del registro web lato server e raccoglie le misurazioni lato client, sito di terze parti o cache rilevate dalle richieste di oggetti incorporati. In altre parole, [!DNL Sensor] acquisisce sia i dati di richiesta normalmente noti ai server Web (misure lato server), sia eventuali dati di misurazione aggiuntivi raccolti tramite l&#39;uso di tag di pagina (misure lato client) che inviano i loro dati a qualsiasi server Web in esecuzione [!DNL Sensor]. Tali server Web possono essere dedicati alla raccolta di misurazioni lato client, ma non sono richiesti.

Per ulteriori informazioni sull&#39;acquisizione di dati di misurazione estesi, vedere [Acquisizione di misurazioni](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944)estese.
