---
description: Un filtro binario nella matrice di correlazione consente di vincolare i valori di una o entrambe le metriche correlate per rendere più focale il confronto.
solution: Analytics
title: Filtro binario nella matrice di correlazione
topic: Data workbench
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Filtro binario nella matrice di correlazione{#binary-filter-in-the-correlation-matrix}

Un filtro binario nella matrice di correlazione consente di vincolare i valori di una o entrambe le metriche correlate per rendere più focale il confronto.

Per impostare un filtro binario su una matrice di correlazione:

1. Dalla matrice di correlazione, fai clic con il pulsante destro del mouse sul nome di una metrica.
1. Selezionate **Modifica dettagli** metrica.

   ![](assets/correlation_matrix_binary_filter.png)

   Si aprirà **[!UICONTROL Edit Correlation Metric Details]** la finestra.

   ![](assets/correlation_matrix_metric_details.png)

1. Impostare un filtro binario.

   Innanzitutto, fate clic sull’ **[!UICONTROL Inactive]** impostazione. Il filtro viene attivato e vengono visualizzati i campi **[!UICONTROL Active]** Confronto **e** Valore **** .

   Quindi, selezionate un **[!UICONTROL Comparison]** operatore e impostatene **[!UICONTROL Value]** l&#39;impostazione in modo da impostare un filtro per la metrica selezionata.

>[!IMPORTANT]
>
>Il filtro binario per Workbench dati 6.2 è stato aggiornato con nuove funzioni, per cui è necessario rigenerare qualsiasi matrice di correlazione con un filtro binario creato nelle versioni precedenti.

## Aggiunta di elementi dimensione {#section-f19f4e0368ca488e92d1e28bcc24417c}

Puoi anche aggiungere un elemento dimensione per vincolare una metrica. A una metrica può essere associato solo un elemento.

![](assets/correlation_matrix_element.png)

Fare clic con il pulsante destro del mouse nell&#39;area di lavoro e selezionare **Tabella**. Aprite una dimensione con i relativi elementi e trascinate fino all’ **[!UICONTROL Element]** impostazione nella finestra Modifica dettagli metrica correlazione oppure rilasciate una metrica nella Matrice di correlazione.
