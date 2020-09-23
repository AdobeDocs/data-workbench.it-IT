---
description: Sensor automatizza l'acquisizione di dati dal tuo canale Internet eliminando la maggior parte del lavoro umano tradizionalmente coinvolto nella raccolta di dati.
solution: Analytics
title: Come funziona il processo di raccolta dei dati?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---


# Come funziona il processo di raccolta dei dati?{#how-does-the-data-collection-process-work}

Sensor automatizza l&#39;acquisizione di dati dal tuo canale Internet eliminando la maggior parte del lavoro umano tradizionalmente coinvolto nella raccolta di dati.

In molti casi, l&#39;utilizzo [!DNL Sensor] può semplificare notevolmente il processo di gestione dei dati.

I siti Internet, extranet e intranet di oggi sono spesso eseguiti su una serie di server Web. I registri e i dati prodotti possono essere molto grandi e ingombranti da gestire. Ad esempio, se il sito esegue 30 server Web, in genere uno dei dipendenti (o dipendenti del provider di servizi esternalizzati) eseguirà il pull e il consolidamento di ciascun file di registro su ciascuno dei 30 server, quindi eseguirà i rapporti su di essi. L&#39;installazione [!DNL Sensor] su ciascun server Web automatizza l&#39;intero processo, riducendo le spese e rendendo i dati disponibili in tempo reale.

Per automatizzare questo processo, [!DNL Sensor] raccoglie informazioni grezze sul traffico su un sito Web direttamente da ciascun server Web. I dati non elaborati [!DNL Sensor] acquisiti sono denominati dati evento ed è simile al tipo di dati registrato dal server Web nei relativi file di registro.

Per acquisire questi dati, la strumentazione all&#39;interno dei [!DNL Sensor] record contiene informazioni su ogni richiesta HTTP elaborata dal server Web. [!DNL Sensor] quindi invia le informazioni in modo da proteggerle da eventuali guasti della rete e le trasmette in modo sicuro tramite HTTP/S al [!DNL data workbench server] valore specificato.

Una volta [!DNL data workbench server] ricevuti i dati, elabora e archivia i file di registro in [!DNL .vsl] file di formato ad alta compressione, consentendo di mantenere facilmente grandi quantità di dati su hardware a basso costo.

Per informazioni sui campi di dati dell&#39;evento raccolti da [!DNL Sensor] nei [!DNL .vsl] file, consultate Campi [di record dati](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)evento.
