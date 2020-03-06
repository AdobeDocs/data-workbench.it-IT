---
description: I grafici Incremento e Guadagno offrono visualizzazioni per valutare le prestazioni potenziali di un modello con punteggio, al fine di valutare le prestazioni su porzioni definite di pubblico.
solution: Analytics
title: Guadagno tendenza e grafici di incremento
topic: Data workbench
uuid: 4f08277e-deea-48d3-ab15-214c43ad6664
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Guadagno tendenza e grafici di incremento{#propensity-gain-and-lift-charts}

I grafici Incremento e Guadagno offrono visualizzazioni per valutare le prestazioni potenziali di un modello con punteggio, al fine di valutare le prestazioni rispetto a porzioni definite di pubblico.

I grafici di incremento e guadagno sono visualizzazioni create per valutare le prestazioni potenziali del modello con punteggio. Questi grafici valutano le prestazioni su ogni parte della popolazione.

**Per aprire un grafico di incremento o guadagno**

1. Select [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Passa il cursore sopra **[!UICONTROL Model Complete]** una valutazione salvata.

![](assets/propensity_lift_gain_1.png)

**Informazioni su Lift and Gain Charts**

I grafici incremento e guadagno sono utili strumenti visivi per misurare il valore di un modello predittivo. Entrambi i grafici sono composti da una curva di incremento (verde) e una linea di base (rosa). Per il **Gain Chart**, la distanza tra la curva di incremento e la linea di base rappresenta quanto è possibile migliorare le prestazioni nelle risposte (o il &quot;guadagno&quot;) utilizzando la modalità predittiva. Il guadagno si realizza dando priorità e indirizzando i potenziali (clienti/visitatori) che più probabilmente verranno convertiti, piuttosto che marketing a clienti/visitatori a caso. In questo modo, potete quantificare il valore previsto utilizzando il modello predittivo per scegliere quali prospettive contattare.

Come per il grafico del guadagno, il grafico **dell&#39;** incremento mostra quanto è più probabile che si riceva una risposta positiva rispetto a quando si contattano dei potenziali clienti a caso. Si desidera che la distanza tra la curva di incremento e la linea di base sia il più ampia possibile, rappresentando guadagni attesi maggiori dall&#39;uso del modello predittivo per contattare i clienti. Dal punto di vista matematico, i grafici di guadagno e di incremento sono definiti come segue:

* **Guadagno** = (Risposta prevista tramite il modello predittivo alle prospettive di contatto) / (Risposta prevista da prospettive di contatto casuali)
* **Lift** = (Risposta prevista tra le dimensioni specifiche del gruppo di prospettive identificate tramite il modello predittivo) / (Risposta prevista tra le stesse dimensioni specifiche del gruppo di prospettive identificate casualmente)

**Esempio di grafici di incremento e guadagno**

Ad esempio, si consideri l&#39;esempio di un rivenditore che desidera lanciare una campagna di ricommercializzazione e-mail per vendere pantaloni yoga. Storicamente, l&#39;analista prevede un tasso di risposta medio del 20% basato su campagne di ricommercializzazione e-mail passate simili a questa. Mentre l&#39;analista ha quasi 5 milioni di clienti nel suo database di posta elettronica, l&#39;azienda vuole solo commercializzare i clienti che più probabilmente risponderanno all&#39;e-mail e all&#39;acquisto. In questo modo, l&#39;azienda ottimizzerà il ROI della campagna, garantendo al contempo che non inviino inutilmente e-mail a clienti non interessati. Dato un tasso di risposta previsto del 20%, l&#39;esperto di marketing e l&#39;analista si aspettano che circa 1 milione di clienti rispondano e acquistino. Invece di indovinare a caso quale di questi clienti sarà tra le risposte del 20%, l&#39;analista vuole essere intelligente nel prevedere quale tra i 1 milione di potenziali clienti (tra i 5 milioni di database di clienti) sarà più probabile che risponda.

Utilizzando la funzionalità Adobe Audience Scoring (Punteggio pubblico), l&#39;analista definisce il successo come clic potenziali su un&#39;e-mail e acquista pantaloni yoga (la variabile dipendente). Dopo aver selezionato le variabili indipendenti (in base all&#39;esperienza e alle conoscenze acquisite dall&#39;analisi delle correlazioni dei dati e del clustering di audience tra le altre analisi), ogni prospettiva è valutata sulla probabilità di rispondere positivamente alla campagna di ricommercializzazione delle e-mail (cliccando sul email e acquistando pantaloni di yoga). L&#39;analista apre i grafici Guadagno e Lift risultanti in base al modello predittivo.

L’asse y mostra la percentuale delle risposte positive cumulative previste. Nel nostro esempio, ci aspettiamo un totale di 1 milione di risposte positive. Un valore del 20% sull&#39;asse y corrisponde al 20% del milione di risposte positive previste, o a 200.000 risposte positive. L’asse x mostra la percentuale di potenziali clienti contattati. Nel nostro esempio, l&#39;asse x rappresenta una frazione dei 5 milioni di clienti presenti nel database delle e-mail. La linea di base (rosa) è il tasso di risposta complessivo. Se contattate l&#39;X% dei potenziali, riceverete l&#39;X% delle risposte positive totali. Utilizzando il modello predittivo, la curva di incremento (verde) mostra la percentuale di risposte positive ottenute (asse y) contattando una determinata percentuale di potenziali (asse x).

Il grafico Incremento riassume l&#39;incremento previsto come risultato dell&#39;utilizzo del modello predittivo per determinare i migliori 1 milione di potenziali clienti che più probabilmente acquisteranno i pantaloni yoga dopo aver ricevuto e cliccando sul email. Per contattare il 20% dei potenziali selezionati in modo casuale senza un modello predittivo, dovreste aspettarvi di ottenere il 20% dei partecipanti. Tuttavia, utilizzando il modello predittivo per identificare il 20% delle prospettive più probabile che rispondano, ci si aspetta di ottenere il 50% dei partecipanti. Il valore y della curva di incremento al 20% è 50/20 = 2,5. Il grafico di incremento mostra quanto più probabile sarà la ricezione dei partecipanti rispetto a un campione casuale di potenziali clienti. Ad esempio, contattando solo il 20% dei potenziali clienti in base al modello predittivo, si raggiungerà 2,5 volte il numero di partecipanti rispetto a non aver utilizzato alcun modello predittivo.
