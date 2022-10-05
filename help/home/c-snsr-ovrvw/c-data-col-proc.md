---
description: Sensor automatizza l'acquisizione di dati dal tuo canale Internet eliminando la maggior parte del lavoro umano tradizionalmente coinvolto nella raccolta dei dati.
title: Come funziona il processo di raccolta dei dati?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# Come funziona il processo di raccolta dei dati?{#how-does-the-data-collection-process-work}

{{eol}}

Sensor automatizza l&#39;acquisizione di dati dal tuo canale Internet eliminando la maggior parte del lavoro umano tradizionalmente coinvolto nella raccolta dei dati.

In molti casi, utilizzando [!DNL Sensor] può semplificare notevolmente il processo di gestione dei dati.

I grandi siti Internet, extranet e intranet di oggi sono spesso eseguiti su un array di server web. I registri e i dati prodotti possono essere molto grandi e ingombranti da gestire. Ad esempio, se il tuo sito esegue 30 server web, in genere uno dei tuoi dipendenti (o dipendenti del provider di servizi in outsourcing) richiama e consolida ogni file di log su ciascuno dei 30 server, quindi esegui report su di essi. Installazione [!DNL Sensor] su ciascuno dei server web automatizza l&#39;intero processo, riducendo le spese e rendendo disponibili i dati in tempo reale.

Per automatizzare questo processo, [!DNL Sensor] raccoglie informazioni grezze sul traffico su un sito web direttamente da ogni server web. I dati non elaborati che [!DNL Sensor] acquisisce è denominato dati evento ed è simile al tipo di dati registrato dal server web nei relativi file di registro.

Per acquisire questi dati, la strumentazione all&#39;interno di [!DNL Sensor] registra informazioni su ogni richiesta HTTP elaborata dal server web. [!DNL Sensor] quindi memorizza le informazioni per proteggerle da un errore di rete e le trasmette in modo sicuro tramite HTTP/S al [!DNL data workbench server] che si specifica.

Dopo la [!DNL data workbench server] riceve i dati, elabora e archivia i file di log in file altamente compressi [!DNL .vsl] file di formato, che consentono di gestire facilmente grandi quantità di dati su hardware a basso costo.

Per informazioni sui campi di dati dell’evento raccolti da [!DNL Sensor] in [!DNL .vsl] file, vedi [Campi record dati evento](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
