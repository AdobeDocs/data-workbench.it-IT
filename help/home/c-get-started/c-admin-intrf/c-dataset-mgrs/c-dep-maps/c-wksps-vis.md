---
description: Informazioni concettuali su aree di lavoro e visualizzazioni.
title: Aree di lavoro e visualizzazioni
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
exl-id: a70748dd-8190-4d1b-9ee1-1011b73a1a86
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 3%

---

# Aree di lavoro e visualizzazioni{#workspaces-and-visualizations}

{{eol}}

Informazioni concettuali su aree di lavoro e visualizzazioni.

La figura seguente mostra una mappa di dipendenza i cui nodi rappresentano le aree di lavoro, i rapporti, le opzioni di menu e i livelli globali definiti nel profilo. Questa opzione funziona solo se [!DNL Query Model] l’opzione di visualizzazione è abilitata.

>[!NOTE]
>
>Se la [!DNL Query Model] l&#39;opzione di visualizzazione non è attivata quando si sceglie la [!DNL Workspaces and Visualizations] viene visualizzato un messaggio di errore.

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* Un nodo grigio rappresenta un’area di lavoro o un rapporto.
* Un nodo giallo-verde rappresenta un&#39;opzione di menu.
* Un nodo rosso rappresenta un livello area di lavoro, report, opzione di menu o globo con una dipendenza rotta o circolare o un altro errore.

>[!NOTE]
>
>Poiché la mappa di dipendenza è progettata per accogliere le dipendenze acicliche, i nodi coinvolti nelle dipendenze circolari potrebbero non essere visualizzati correttamente sulla mappa. È possibile cercare le dipendenze circolari digitando &quot;dipendenza circolare&quot; nel [!DNL Search] casella di testo. Per ulteriori informazioni sulla [!DNL Search] funzionalità, vedi [Ricerca all’interno di una mappa](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

Per le descrizioni di altri nodi sulla mappa, vedi [Componenti del modello di query](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).
