---
description: Una visualizzazione di analisi guidata fornisce suggerimenti per ulteriori analisi in base alle selezioni effettuate in un’area di lavoro.
solution: Analytics
title: Analisi guidata
topic: Data workbench
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Analisi guidata{#guided-analysis}

Una visualizzazione di analisi guidata fornisce suggerimenti per ulteriori analisi in base alle selezioni effettuate in un’area di lavoro.

Questa visualizzazione consente di identificare le dimensioni che possono fornire ulteriori informazioni, ovvero quelle strettamente correlate alle selezioni. La visualizzazione dell’analisi guidata nell’applicazione Adobe mostra le dimensioni rilevanti per il set di dati, come nella seguente visualizzazione dell’analisi [!DNL Site] guidata.

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>Se il nome di una dimensione viene visualizzato in rosso, non è definito nel set di dati.

Quando si effettua una selezione all’interno di un’area di lavoro, la visualizzazione dell’analisi guidata mostra i segni di spunta a sinistra e i punti a destra delle dimensioni per mostrare quali sono le informazioni più rilevanti:

* **I segni** di controllo identificano le dimensioni i cui valori differiscono dal parametro di riferimento in modo statisticamente significativo (cioè, la differenza tra la selezione e il parametro di riferimento non è dovuta a casualità).
* **I puntini** indicano il grado di differenza tra la selezione e l&#39;indice di riferimento. Il primo punto rappresenta la statistica U, mentre il secondo rappresenta la statistica V. Vedere [Informazioni sulle misure](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708)statistiche. Più sono chiari e più grandi i punti, maggiore è la differenza e più pertinenti sono le informazioni per la dimensione in base alla selezione (ossia, puntini più luminosi e più grandi rappresentano informazioni più utili).

