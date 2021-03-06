---
description: Vengono definiti i calcoli statistici per il Punteggio tendenza.
title: Calcolo del punteggio tendenza
uuid: 67270864-0468-4cc9-b48b-0e880f813555
exl-id: 679e1363-fd10-4a44-a85a-ef0daefaf303
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 1%

---

# Calcolo del punteggio tendenza{#calculating-propensity-scoring}

Vengono definiti i calcoli statistici per il Punteggio tendenza.

Concettualmente, il punteggio calcolato per ogni visitatore è una probabilità stimata che l&#39;evento specificato (definito dal filtro target) possa verificarsi, con conseguente intervallo di valori del punteggio da 0 a 100%. La procedura di valutazione utilizza campioni esistenti come dati di formazione per trovare la relazione tra la probabilità dell’evento e le variabili indipendenti selezionate di interesse.

Dal punto di vista matematico, tali relazioni si riflettono in ciascun valore quantitativo associato a ciascuna variabile indipendente. Questi valori sono chiamati coefficienti del modello. ScoreDim utilizza attualmente l&#39;algoritmo IRLS (Iterically Reweighted Least Squares) per stimare i coefficienti del modello. L&#39;IRLS passa attraverso i campioni più volte fino a quando la differenza dei coefficienti tra la passata di corrente e la passata precedente non è inferiore a 1,0e-6, in cui si chiama **converged**. Tuttavia, a seconda dei dati, gli IRLS potrebbero non essere in grado di raggiungere la convergenza.

In tal caso, l&#39;iterazione di formazione del modello terminerà quando

* la differenza di coefficiente diventa più grande invece di più piccola,
* sono stati raggiunti 1000 passaggi, oppure
* un errore matematico impedisce il proseguimento dell’iterazione.

Se l’IRLS non converge, verrà utilizzato un algoritmo di backup denominato SGD (Stochastic Gradient Decent). SGD passerà anche attraverso i campioni di formazione più volte. Ma a differenza di IRLS, i coefficienti del modello SGD sono controllati in modo che la differenza tra iterazioni diminuisca sempre in modo esponenziale. Analogamente, SGD terminerà quando la differenza di coefficiente scende al di sotto di 1.0e-6 o 100.000 passaggi sono stati raggiunti. Il guasto dell&#39;IRLS e l&#39;impegno del SGD saranno registrati nel registro di traccia.

Per entrambi gli algoritmi, non tutti i campioni vengono inseriti nella formazione del modello. L&#39;80% viene attualmente utilizzato per addestrare il modello. Dopo aver appreso la formazione del modello, i campioni rimanenti del 20% verranno utilizzati per valutare la resistenza del modello in termini di precisione, richiamata e precisione calcolati dalla matrice di confusione. Più vicino al 100%, migliore sarà il modello di punteggio.
