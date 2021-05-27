---
description: Informazioni concettuali sui componenti del modello di query.
title: Componenti del modello di query
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
exl-id: 1f5d0a3a-6647-4762-ab20-9d80e467d48f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 3%

---

# Componenti del modello di query{#query-model-components}

Informazioni concettuali sui componenti del modello di query.

La figura seguente mostra una mappa di dipendenza i cui nodi rappresentano le metriche, le dimensioni derivate e i filtri di un modello di query definiti nelle cartelle Dimension, Metriche e Filtri all’interno del profilo, nonché le dimensioni estese definite nel set di dati che vi si riferiscono in qualche modo.

![](assets/vis_DependencyMap_QueryModel.png)

* Un nodo giallo-verde rappresenta un filtro.
* Un nodo viola rappresenta una metrica.
* Un nodo blu-verde rappresenta una dimensione derivata.
* Un nodo verde rappresenta una dimensione estesa (definita nel set di dati).
* Un nodo rosso rappresenta una metrica, una dimensione derivata o un filtro con una dipendenza interrotta o circolare o con un altro errore.

>[!NOTE]
>
>Poiché la mappa di dipendenza è progettata per accogliere le dipendenze acicliche, i nodi coinvolti nelle dipendenze circolari potrebbero non essere visualizzati correttamente sulla mappa. È possibile cercare le dipendenze circolari digitando &quot;dipendenza circolare&quot; nella casella di testo [!DNL Search]. Per ulteriori informazioni sulla funzione [!DNL Search], consulta [Ricerca all&#39;interno di una mappa](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).
