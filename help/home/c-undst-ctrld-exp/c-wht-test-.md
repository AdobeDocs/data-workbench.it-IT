---
description: I risultati dei test devono essere chiari e significativi in modo da poter essere certi di prendere decisioni in dollari grandi sulla base di tali risultati.
solution: Analytics,Analytics
title: Cosa dovrei verificare?
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
exl-id: 0f06ff0f-b385-4614-8007-afdb85191a85
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---

# Cosa dovrei verificare?{#what-should-i-test}

I risultati dei test devono essere chiari e significativi in modo da poter essere certi di prendere decisioni in dollari grandi sulla base di tali risultati.

Anche se è possibile testare vari layout di pagina con [!DNL Sensor] e Sito, l&#39;Adobe suggerisce di concentrarsi sul test di iniziative aziendali strategiche di alto valore o di nuova o riprogettata funzionalità del sito web che rispondono agli obiettivi impostati per il sito web e per la tua attività. Puoi verificare problemi quali le migliori garanzie di prezzo, la funzionalità di personalizzazione, le offerte di mercato (ad esempio, pacchetti o bundle), la progettazione creativa e i processi applicativi.

I seguenti concetti sono più importanti quando si sviluppa un esperimento controllato:

* **Comprendere le modifiche corrette da apportare.** Questo richiede alcune ricerche sul funzionamento del sito web e sui processi aziendali alla base del sito web front-end. Desideri apportare modifiche che garantiscano il massimo impatto e possano essere testate facilmente.
* **I piccoli cambiamenti possono avere un impatto significativo.** Non tutte le modifiche che si verificano devono essere drastiche per avere un impatto significativo sulla tua attività. Siate sempre aperti a fare piccoli ma importanti cambiamenti.

## Metodologie supportate {#section-1071adaf54c64ba9bc5ef228c4a23635}

Molti tipi di esperimenti con molti obiettivi diversi possono essere eseguiti utilizzando il sito. Di seguito sono riportati alcuni esempi:

* Modifica di pagine, contenuti e processi del sito web per migliorare i tassi di conversione.
* Modifica di campagne di marketing, promozioni, cross-selling e up-sell per aumentare i ricavi.
* Tempi di caricamento delle pagine variabili per comprendere la qualità del servizio e il valore effettivo delle prestazioni dell’infrastruttura.

Per raggiungere questi obiettivi, Site supporta i seguenti tipi di metodologie per la sperimentazione e il test controllati:

* **Sostituzione pagina:** sostituisci l’URL statico X con l’URL statico Y. Questa metodologia è di utilizzo limitato in un ambiente dinamico.
* **Sostituzione URI dinamici:** questa è una variante di Sostituzione pagina che sostituisce la pagina statica X con la pagina dinamica Y per il rendering del contenuto dinamico.
* **Sostituzione oggetto:** sostituire l&#39;oggetto fisso X con l&#39;oggetto fisso Y.
* **Sostituzione del contenuto:** sostituisci il set di contenuti X (più oggetti, pagine, tabelle e così via) con il set di contenuti Y.
* **Sostituzione delle variabili di esperimento:** sostituisci l’oggetto JavaScript /writeCookie_X.js con l’oggetto JavaScript /writeCookie_Y.js per scrivere un cookie che può essere utilizzato da un sistema back-end per distribuire contenuti particolari.

>[!NOTE]
>
>Gli esperimenti controllati si basano sulla sostituzione degli URI, non sulla sostituzione delle stringhe di query. L’URI all’interno di un particolare URL viene evidenziato nell’esempio seguente:
>
>`https://www.omniture.com/index.asp?id=1`
>
>Ad esempio, nell’esperimento controllato è possibile specificare la sostituzione dell’URI del gruppo di controllo [!DNL index.asp] con l’URI del gruppo di test [!DNL index2.asp] per determinare quale progetto di pagina risulterebbe in un valore maggiore.
