---
description: Informazioni concettuali sui componenti del set di dati.
title: Componenti set di dati
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 1%

---

# Componenti set di dati{#dataset-components}

Informazioni concettuali sui componenti del set di dati.

La figura seguente mostra una mappa di dipendenza i cui nodi rappresentano le origini di registro, i campi, le trasformazioni e le dimensioni estese di un set di dati.

![](assets/vis_DependencyMap.png)

* Un nodo giallo-verde rappresenta una o più origini di registro o un filtro (ad esempio una condizione di voce di registro) definito nel set di dati.

   * Un nodo per un&#39;origine di registro appare sempre più a sinistra nella mappa. Se il set di dati ha una singola origine di registro, la mappa visualizza Origine registro: *nome origine registro*. Se il set di dati dispone di più origini di registro, la mappa visualizza *number* Origini di registro, dove number è il conteggio delle origini di registro. Ad esempio, se nel set di dati sono presenti tre origini di registro, nella mappa vengono visualizzate 3 Origini di registro.

   * La mappa visualizza un nodo Condizione voce registro per ciascun file [!DNL log processing dataset include], ma un solo nodo Condizione voce registro per la trasformazione (se definito nel file [!DNL Transformation.cfg]). Se la condizione della voce di registro è vuota, non viene visualizzata sulla mappa.

* Un nodo grigio rappresenta un campo elencato nel parametro Fields in un file [!DNL Log Processing.cfg] o [!DNL Log Processing include].

* Un nodo blu rappresenta una trasformazione.
* Un nodo verde rappresenta una dimensione estesa.

>[!NOTE]
>
>Se la cartella Dataset del profilo contiene il file [!DNL Insight Transform.cfg], la mappa di dipendenza mostra le origini di registro, le trasformazioni e gli esportatori definiti per l’utilizzo con Transform. Per informazioni sulla trasformazione, vedere la *Guida alla configurazione del set di dati*.

Quando abiliti l’opzione di visualizzazione Includi [!DNL File Blocks] , la mappa visualizza un singolo nodo blu per tutte le trasformazioni definite in un file di configurazione del set di dati e un singolo nodo verde per tutte le dimensioni estese definite in un file di configurazione del set di dati. Per ulteriori informazioni su questa opzione di visualizzazione, vedere [Uso dei blocchi di file](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
