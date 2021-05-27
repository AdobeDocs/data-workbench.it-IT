---
description: I grafici Incremento e Guadagno offrono visualizzazioni per la valutazione delle prestazioni potenziali di un modello con punteggio, al fine di valutare le prestazioni su parti definite del pubblico.
title: Guadagno tendenza e grafici di accuratezza
uuid: 4f08277e-deea-48d3-ab15-214c43ad6664
exl-id: 5ac08512-ac9c-4e85-a4f9-ea6d819095d8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 1%

---

# Guadagno tendenza e grafici di accuratezza{#propensity-gain-and-lift-charts}

I grafici Incremento e Guadagno offrono visualizzazioni per la valutazione delle prestazioni potenziali di un modello con punteggio, al fine di valutare le prestazioni su parti definite del pubblico.

I grafici di incremento e guadagno sono visualizzazioni create per valutare le prestazioni potenziali del modello con punteggio. Questi grafici valutano le prestazioni su ogni parte della popolazione.

**Apertura di un grafico ad incremento o guadagno**

1. Select [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Passa il puntatore del mouse sopra **[!UICONTROL Model Complete]** di un punteggio salvato.

![](assets/propensity_lift_gain_1.png)

**Informazioni su grafici di incremento e guadagno**

I grafici di incremento e guadagno sono strumenti visivi utili per misurare il valore di un modello predittivo. Entrambi i grafici sono costituiti da una curva di incremento (verde) e una linea di base (rosa). Per il **Grafico guadagno**, la distanza tra la curva di incremento e la linea di base rappresenta quanto è possibile migliorare le prestazioni nelle risposte (o il &quot;guadagno&quot;) utilizzando la modalità predittiva. Il guadagno si ottiene assegnando priorità e rivolgendo il targeting ai potenziali (clienti/visitatori) che hanno più probabilità di effettuare la conversione, anziché commercializzare a clienti/visitatori in modo casuale. In questo modo, puoi quantificare il valore previsto dell&#39;utilizzo del modello predittivo per scegliere quali potenziali contatti.

Simile al grafico del guadagno, il **Grafico di incremento** mostra quanto è più probabile ricevere risposte positive rispetto a quando si contattano i potenziali clienti a caso. Si desidera che la distanza tra la curva di incremento e la linea di base sia il più grande possibile, rappresentando guadagni attesi maggiori utilizzando il modello predittivo per contattare i clienti. I grafici di guadagno e di incremento sono definiti matematicamente come segue:

* **Guadagno** = (Risposta prevista utilizzando il modello predittivo per le prospettive di contatto) / (Risposta prevista da prospettive di contatto casuali)
* **Incremento**  = (Risposta prevista tra una dimensione specifica del gruppo di prospettive identificata utilizzando il modello predittivo) / (Risposta prevista tra le stesse dimensioni specifiche del gruppo di prospettive identificate casualmente)

**Esempio di grafici di incremento e guadagno**

Ad esempio, considera l’esempio di un rivenditore che desidera lanciare una campagna di ricommercializzazione e-mail per vendere pantaloni da yoga. Storicamente, l’analista si aspetta un tasso di risposta medio del 20% basato su campagne di ricommercializzazione delle e-mail passate simili a questa. Mentre l&#39;analista ha quasi 5 milioni di clienti nel suo database di e-mail, l&#39;azienda vuole solo vendere a quei clienti che hanno più probabilità di rispondere all&#39;e-mail e l&#39;acquisto. In questo modo, l&#39;azienda massimizzerà il ROI della campagna, garantendo al contempo che non inviino inutilmente e-mail a clienti non interessati. Dato un tasso di risposta atteso del 20%, l&#39;addetto al marketing e l&#39;analista si aspettano che circa 1 milione di clienti risponderanno e acquistino. Anziché indovinare casualmente quale di questi clienti sarà tra le risposte del 20%, l&#39;analista vuole essere intelligente nel prevedere quale tra i 1 milione di potenziali clienti (tra i 5 milioni di database di clienti) è più probabile che risponderà.

Utilizzando la funzionalità di valutazione del pubblico di Adobe, l’analista definisce il successo come un potenziale clic su un’e-mail e acquista pantaloni da yoga (la variabile dipendente). Dopo aver selezionato le variabili indipendenti (in base all’esperienza e alle conoscenze acquisite dall’analisi delle correlazioni dei dati e del clustering del pubblico, tra le altre analisi), ogni potenziale cliente riceve un punteggio sulla probabilità di rispondere positivamente alla campagna di ricommercializzazione delle e-mail (facendo clic sull’e-mail e acquistando pantaloni yoga). L&#39;analista apre i grafici Guadagno e Incremento risultanti in base al modello predittivo.

L&#39;asse y mostra la percentuale delle risposte positive previste cumulative. Nel nostro esempio, ci aspettiamo un totale di 1 milione di risposte positive. Un valore del 20% sull&#39;asse y corrisponde al 20% del 1 milione di risposte positive previste, o 200.000 risposte positive. L’asse x mostra la percentuale di potenziali clienti contattati. Nel nostro esempio, l’asse x rappresenta una frazione dei 5 milioni di clienti nel database e-mail. La linea di base (rosa) è il tasso di risposta complessivo - se si contatta l’X% dei potenziali, si riceverà l’X% delle risposte positive totali. Utilizzando il modello predittivo, la curva di incremento (verde) mostra la percentuale di risposte positive ottenute (asse y) contattando una determinata percentuale di potenziali clienti (asse x).

Il grafico Lift traccia l’incremento previsto come risultato dell’utilizzo del modello predittivo per determinare i migliori 1 milione di potenziali clienti che più probabilmente acquisteranno pantaloni yoga dopo aver ricevuto e cliccando sull’e-mail. Per contattare il 20% dei potenziali selezionati in modo casuale senza un modello predittivo, si dovrebbe aspettare di ottenere il 20% dei rispondenti. Tuttavia, utilizzando il modello predittivo per identificare il 20% delle prospettive più probabile che rispondano, si prevede di ottenere il 50% dei rispondenti. Il valore y della curva di incremento al 20% è 50/20 = 2,5. Il grafico di incremento mostra quanto è più probabile ricevere gli intervistati che se si contatta un campione casuale di potenziali clienti. Ad esempio, contattando solo il 20% dei potenziali clienti in base al modello predittivo, raggiungerai 2,5 volte il numero di rispondenti rispetto a non aver utilizzato alcun modello predittivo.
