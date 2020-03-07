---
description: Informazioni concettuali su aree di lavoro e visualizzazioni.
solution: Analytics
title: Aree di lavoro e visualizzazioni
topic: Data workbench
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aree di lavoro e visualizzazioni{#workspaces-and-visualizations}

Informazioni concettuali su aree di lavoro e visualizzazioni.

La figura seguente mostra una mappa delle dipendenze i cui nodi rappresentano le aree di lavoro, i rapporti, le opzioni di menu e i livelli globali definiti nel profilo. Questa opzione funziona solo se l&#39;opzione di [!DNL Query Model] visualizzazione è abilitata.

>[!NOTE]
>
>Se l&#39;opzione di [!DNL Query Model] visualizzazione non è abilitata quando si sceglie l&#39;opzione di [!DNL Workspaces and Visualizations] visualizzazione, viene visualizzato un messaggio di errore.

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* Un nodo grigio rappresenta un&#39;area di lavoro o un rapporto.
* Un nodo giallo-verde rappresenta un&#39;opzione di menu.
* Un nodo rosso rappresenta un&#39;area di lavoro, un rapporto, un&#39;opzione di menu o un livello globo con una dipendenza rotta o circolare o un altro errore.

>[!NOTE]
>
>Poiché la mappa delle dipendenze è progettata per contenere dipendenze cicliche, i nodi coinvolti in dipendenze circolari potrebbero non essere visualizzati correttamente sulla mappa. È possibile cercare dipendenze circolari digitando &quot;dipendenza circolare&quot; nella casella di [!DNL Search] testo. Per ulteriori informazioni sulla [!DNL Search] funzione, consultate [Ricerca all’interno di una mappa](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

Per una descrizione di altri nodi della mappa, vedere Componenti [del modello di](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f)query.
