---
description: Informazioni concettuali sui componenti del modello di query.
solution: Analytics
title: Componenti del modello di query
topic: Data workbench
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Componenti del modello di query{#query-model-components}

Informazioni concettuali sui componenti del modello di query.

La figura seguente mostra una mappa di dipendenza i cui nodi rappresentano le metriche del modello di query, le dimensioni derivate e i filtri definiti nelle cartelle Dimensioni, Metriche e Filtri all&#39;interno del profilo, nonché le dimensioni estese definite nel set di dati che vi si riferiscono in qualche modo.

![](assets/vis_DependencyMap_QueryModel.png)

* Un nodo giallo-verde rappresenta un filtro.
* Un nodo viola rappresenta una metrica.
* Un nodo blu-verde rappresenta una dimensione derivata.
* Un nodo verde rappresenta una dimensione estesa (definita nel dataset).
* Un nodo rosso rappresenta una metrica, una dimensione derivata o un filtro con una dipendenza rotta o circolare o con un altro errore.

>[!NOTE]
>
>Poiché la mappa delle dipendenze è progettata per contenere dipendenze cicliche, i nodi coinvolti in dipendenze circolari potrebbero non essere visualizzati correttamente sulla mappa. È possibile cercare dipendenze circolari digitando &quot;dipendenza circolare&quot; nella casella di [!DNL Search] testo. Per ulteriori informazioni sulla [!DNL Search] funzione, consultate [Ricerca all’interno di una mappa](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

