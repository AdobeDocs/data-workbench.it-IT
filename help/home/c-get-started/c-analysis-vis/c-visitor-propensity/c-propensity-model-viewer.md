---
description: Un visualizzatore di modelli consente di generare un modello di regressione logistica utilizzando la funzione Punteggio tendenza.
title: Visualizzatore modelli
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
exl-id: e0e4acd4-76a2-436a-993b-2bb7ca91ae1a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 3%

---

# Visualizzatore modelli{#model-viewer}

Un visualizzatore di modelli consente di generare un modello di regressione logistica utilizzando la funzione Punteggio tendenza.

Il Visualizzatore modelli visualizza i pesi del coefficiente di ciascuna variabile di input (compreso il termine costante) e il relativo intervallo di errori statistici. Le variabili di input che mostrano un coefficiente assoluto elevato e un piccolo margine di errore sono i preditori più significativi nel modello.

**Per aprire un grafico Visualizzatore modelli**

1. Select [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Passaggio del mouse sul modello Completato di un punteggio salvato.

![](assets/propensity_model_viewer.png)

Le variabili di input con un coefficiente >= 1 sono influenze positive sul modello di propensione. I coefficienti &lt; 1 sono influenzati negativi sul modello di propensione. L’intervallo definito tra parentesi è l’errore e indica la coerenza della variabile di input tra la popolazione corretta.
