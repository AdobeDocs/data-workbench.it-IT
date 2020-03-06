---
description: Un visualizzatore modello consente di generare un modello di regressione logistica mediante la funzione Propensity Scoring (Punteggio tendenza).
solution: Analytics
title: Visualizzatore modelli
topic: Data workbench
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualizzatore modelli{#model-viewer}

Un visualizzatore modello consente di generare un modello di regressione logistica mediante la funzione Propensity Scoring (Punteggio tendenza).

Il visualizzatore modelli visualizza i pesi di coefficiente di ciascuna variabile di input (compreso il termine costante) e il relativo intervallo di errori statistici. Le variabili di input che mostrano un coefficiente assoluto elevato e un piccolo margine di errore sono i predetti più significativi del modello.

**Per aprire un grafico Visualizzatore modelli**

1. Select [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Passaggio del mouse sul modello Completato di un punteggio salvato.

![](assets/propensity_model_viewer.png)

Le variabili di input con un coefficiente >= 1 influiscono positivamente sul modello di propensione. I coefficienti &lt; 1 influiscono negativamente sul modello di propensione. L&#39;intervallo definito tra parentesi rappresenta l&#39;errore e indica la coerenza della variabile di input tra la popolazione corretta.
