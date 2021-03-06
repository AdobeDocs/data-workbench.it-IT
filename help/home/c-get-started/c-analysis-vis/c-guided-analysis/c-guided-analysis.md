---
description: Una visualizzazione di analisi guidata fornisce suggerimenti per ulteriori analisi in base alle selezioni effettuate in un’area di lavoro.
title: Analisi guidata
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
exl-id: c19b52b6-52db-455e-adde-8b2400aae006
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---

# Analisi guidata{#guided-analysis}

Una visualizzazione di analisi guidata fornisce suggerimenti per ulteriori analisi in base alle selezioni effettuate in un’area di lavoro.

Questa visualizzazione ti aiuta a identificare quali dimensioni possono fornirti ulteriori informazioni, ovvero quelle strettamente correlate alle selezioni. La visualizzazione dell’analisi guidata nell’applicazione Adobe mostra le dimensioni rilevanti per il set di dati, come nella seguente [!DNL Site] visualizzazione dell’analisi guidata.

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>Se un nome di dimensione viene visualizzato in rosso, non è definito nel set di dati.

Quando effettui una selezione all’interno di un’area di lavoro, la visualizzazione di analisi guidata mostra i segni di spunta a sinistra e i punti a destra delle dimensioni per mostrare quali forniscono le informazioni più rilevanti:

* **Controlla** marksidentify le dimensioni i cui valori differiscono dal valore di riferimento in modo statisticamente significativo (cioè, la differenza tra la selezione e il valore di riferimento non è dovuta a casualità).
* **** Indica il grado di differenza tra la selezione e il valore di riferimento. Il primo punto rappresenta la statistica U e il secondo punto rappresenta la statistica V. Consulta [Informazioni sulle misure statistiche](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708). Più i punti sono luminosi e più grandi, maggiore è la differenza e più sono pertinenti le informazioni per la dimensione in base alla selezione (ovvero, i punti più luminosi e più grandi rappresentano informazioni più utili).
