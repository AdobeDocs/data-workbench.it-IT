---
description: Informazioni concettuali su aree di lavoro e visualizzazioni.
title: Aree di lavoro e visualizzazioni
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
exl-id: a70748dd-8190-4d1b-9ee1-1011b73a1a86
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 3%

---

# Aree di lavoro e visualizzazioni{#workspaces-and-visualizations}

Informazioni concettuali su aree di lavoro e visualizzazioni.

La figura seguente mostra una mappa di dipendenza i cui nodi rappresentano le aree di lavoro, i rapporti, le opzioni di menu e i livelli globali definiti nel profilo. Questa opzione funziona solo se l’opzione di visualizzazione [!DNL Query Model] è abilitata.

>[!NOTE]
>
>Se l&#39;opzione di visualizzazione [!DNL Query Model] non è abilitata quando scegli l&#39;opzione di visualizzazione [!DNL Workspaces and Visualizations], viene visualizzato un messaggio di errore.

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* Un nodo grigio rappresenta un’area di lavoro o un rapporto.
* Un nodo giallo-verde rappresenta un&#39;opzione di menu.
* Un nodo rosso rappresenta un livello area di lavoro, report, opzione di menu o globo con una dipendenza rotta o circolare o un altro errore.

>[!NOTE]
>
>Poiché la mappa di dipendenza è progettata per accogliere le dipendenze acicliche, i nodi coinvolti nelle dipendenze circolari potrebbero non essere visualizzati correttamente sulla mappa. È possibile cercare le dipendenze circolari digitando &quot;dipendenza circolare&quot; nella casella di testo [!DNL Search]. Per ulteriori informazioni sulla funzione [!DNL Search], consulta [Ricerca all&#39;interno di una mappa](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

Per una descrizione degli altri nodi sulla mappa, consulta [Componenti del modello di query](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).
