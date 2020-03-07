---
description: Informazioni concettuali sui componenti dataset.
solution: Analytics
title: Componenti set di dati
topic: Data workbench
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Componenti set di dati{#dataset-components}

Informazioni concettuali sui componenti dataset.

La figura seguente mostra una mappa delle dipendenze i cui nodi rappresentano le origini di registro, i campi, le trasformazioni e le dimensioni estese di un dataset.

![](assets/vis_DependencyMap.png)

* Un nodo giallo-verde rappresenta una o più origini di registro o un filtro (ad esempio una condizione di voce di registro) definito nel set di dati.

   * Un nodo per un&#39;origine di registro viene sempre visualizzato più a sinistra nella mappa. Se il set di dati ha una singola origine di registro, la mappa visualizza Origine registro: nome *origine* del registro. Se il set di dati contiene più origini di registro, la mappa visualizza *il numero* Origini di registro, dove numero è il numero di origini di registro. Ad esempio, se nel set di dati sono presenti tre origini di registro, nella mappa vengono visualizzate 3 origini di registro.

   * Nella mappa viene visualizzato un nodo Condizione voce di registro per ciascun [!DNL log processing dataset include] file, ma solo un nodo Condizione voce di registro per la trasformazione (se definito nel [!DNL Transformation.cfg] file). Se la condizione Voce di registro è vuota, non viene visualizzata sulla mappa.

* Un nodo grigio rappresenta un campo elencato nel parametro Campi di un [!DNL Log Processing.cfg] file o di un [!DNL Log Processing include] file.

* Un nodo blu rappresenta una trasformazione.
* Un nodo verde rappresenta una dimensione estesa.

>[!NOTE]
>
>Se la cartella DataSet del profilo contiene il file [!DNL Insight Transform.cfg], la mappa delle dipendenze mostra le origini di registro, le trasformazioni e gli esportatori definiti per l&#39;uso con Transform. Per informazioni sulla trasformazione, vedere la Guida alla configurazione del *set di dati*.

Quando si abilita l&#39;opzione di [!DNL File Blocks] visualizzazione Includi, la mappa visualizza un singolo nodo blu per tutte le trasformazioni definite in un file di configurazione dataset e un singolo nodo verde per tutte le dimensioni estese definite in un file di configurazione dataset. Per ulteriori informazioni su questa opzione di visualizzazione, vedere [Uso dei blocchi](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc)di file.
