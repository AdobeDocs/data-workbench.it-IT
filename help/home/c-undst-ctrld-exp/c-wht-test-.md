---
description: I risultati dei test devono essere chiari e significativi in modo da poter essere certi di prendere decisioni in dollari su larga scala sulla base di tali risultati.
solution: Analytics,Analytics
title: Cosa dovrei verificare?
topic: Data workbench
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---


# Cosa dovrei verificare?{#what-should-i-test}

I risultati dei test devono essere chiari e significativi in modo da poter essere certi di prendere decisioni in dollari su larga scala sulla base di tali risultati.

Sebbene sia possibile sottoporre a test vari layout di pagina con [!DNL Sensor] e Sito,  Adobe suggerisce di focalizzare l&#39;attenzione sul test di iniziative aziendali strategiche di alto valore, o di nuove o riprogettate funzionalità del sito Web che soddisfano gli obiettivi impostati per il sito Web e per la propria attività. Potete testare problemi quali le migliori garanzie di prezzo, la funzionalità di personalizzazione, le offerte di mercato (ad esempio, pacchetti o pacchetti), la progettazione creativa e i processi applicativi.

I seguenti concetti sono più importanti nello sviluppo dell’esperimento controllato:

* **Comprendere le modifiche giuste da apportare.** Ciò richiede alcune ricerche sul funzionamento del sito Web e sui processi aziendali sottostanti al sito Web front-end. Desiderate apportare modifiche che forniscano il massimo impatto e possano essere facilmente testate.
* **I piccoli cambiamenti possono avere un impatto significativo.** Non tutte le modifiche che si verificano devono essere drastiche per avere un impatto significativo sulla tua attività. Siate sempre disponibili a fare piccoli, ma importantissimi cambiamenti.

## Metodologie supportate {#section-1071adaf54c64ba9bc5ef228c4a23635}

Molti tipi di esperimenti con molti obiettivi diversi possono essere eseguiti utilizzando Site. Di seguito sono riportati alcuni esempi:

* Modifica di pagine, contenuti e processi basati su siti Web per migliorare i tassi di conversione.
* Modifica di campagne di marketing, promozioni, cross-selling e up-sell per incrementare le entrate.
* Tempi di caricamento delle pagine variabili per comprendere la qualità del servizio dei clienti e il valore effettivo delle prestazioni dell&#39;infrastruttura.

Per raggiungere questi obiettivi, Site supporta i seguenti tipi di metodologie per la sperimentazione e il test controllati:

* **Sostituzione pagina:** Sostituisce l’URL statico X con l’URL statico Y. Questa metodologia è di utilizzo limitato in un ambiente dinamico.
* **Sostituzione URI dinamica:** Si tratta di una variante di Sostituzione pagina che sostituisce la pagina statica X con la pagina dinamica Y per il rendering del contenuto dinamico.
* **Sostituzione oggetto:** Sostituire l&#39;oggetto fisso X con l&#39;oggetto fisso Y.
* **Sostituzione contenuto:** Sostituisce il set di contenuti X (più oggetti, pagine, tabelle e così via) con il set di contenuti Y.
* **Sostituzione della variabile di prova:** Sostituire l&#39;oggetto JavaScript /writeCookie_X.js con l&#39;oggetto JavaScript /writeCookie_Y.js per scrivere un cookie che può essere utilizzato da un sistema back-end per distribuire contenuti particolari.

>[!NOTE]
>
>Gli esperimenti controllati si basano sulla sostituzione URI, non sulla sostituzione delle stringhe di query. L’URI all’interno di un particolare URL è evidenziato nel seguente esempio:
>
>`http://www.omniture.com/index.asp?id=1`
>
>Ad esempio, nell&#39;esperimento controllato è possibile specificare che l&#39;URI del gruppo di controllo [!DNL index.asp] venga sostituito con l&#39;URI del gruppo di test [!DNL index2.asp] per determinare quale progettazione di pagina darà maggior valore.
