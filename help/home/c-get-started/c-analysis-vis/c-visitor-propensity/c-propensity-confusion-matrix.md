---
description: Vengono definiti i calcoli statistici per il punteggio tendenza.
solution: Analytics
title: Calcolo del punteggio tendenza
topic: Data workbench
uuid: 67270864-0468-4cc9-b48b-0e880f813555
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Calcolo del punteggio tendenza{#calculating-propensity-scoring}

Vengono definiti i calcoli statistici per il punteggio tendenza.

Concettualmente, la valutazione calcolata per ogni visitatore è una probabilità stimata che l&#39;evento specificato (definito dal filtro di destinazione) possa verificarsi, con un valore di punteggio compreso tra 0 e 100%. La procedura di punteggio utilizza esempi esistenti come dati di formazione per trovare la relazione tra la probabilità dell’evento e le variabili indipendenti selezionate di interesse.

Dal punto di vista matematico, tali relazioni si riflettono in ogni valore quantitativo associato a ciascuna variabile indipendente. Tali valori sono denominati coefficienti del modello. ScoreDim utilizza attualmente l’algoritmo IRLS (Iterational Reweight Least Squares) per stimare i coefficienti del modello. L’IRLS attraversa i campioni più volte fino a quando la differenza dei coefficienti tra la passata di corrente e la passata precedente non è inferiore a 1,0 e-6, a cui si chiama **convergente**. Tuttavia, a seconda dei dati, l&#39;IRLS potrebbe non essere in grado di raggiungere la convergenza.

In tal caso, l&#39;iterazione di formazione del modello terminerà quando

* la differenza di coefficiente diventa maggiore invece di minore,
* sono stati raggiunti 1000 passaggi, o
* un errore matematico impedisce la continuazione dell&#39;iterazione.

Se IRLS non converge, verrà utilizzato un algoritmo di backup denominato Decent sfumatura stocastica (SGD). SGD passerà anche attraverso gli esempi di formazione più volte. Ma a differenza di IRLS, i coefficienti del modello SGD sono controllati in modo che la differenza tra iterazione diminuisca sempre in modo esponenziale. Allo stesso modo, SGD terminerà quando la differenza di coefficiente scende al di sotto di 1.0 e-6 o 100.000 passaggi sono stati raggiunti. Il guasto di IRLS e l&#39;impegno di SGD saranno registrati nel registro di traccia.

Per entrambi gli algoritmi, non tutti gli esempi seguono la formazione sul modello. L&#39;80% è attualmente utilizzato per formare il modello. Dopo aver preparato il modello, i restanti campioni del 20% verranno utilizzati per valutare la resistenza del modello in termini di precisione, richiamata e precisione calcolati dalla matrice di confusione. Più vicino al 100%, migliore sarà il modello di punteggio.
