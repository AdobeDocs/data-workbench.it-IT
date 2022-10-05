---
description: Le mappe di dipendenza consentono di visualizzare e gestire la configurazione dei componenti del profilo.
title: Mappe di dipendenza
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
exl-id: 4618c735-f507-4abc-a4b4-d52a37c64c60,733407ca-3326-406a-a642-a3ea3d3f6b8b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 1%

---

# Mappe di dipendenza{#dependency-maps}

{{eol}}

Le mappe di dipendenza consentono di visualizzare e gestire la configurazione dei componenti del profilo.

* **Componenti set di dati:** Origini di registro, filtri, campi, trasformazioni e dimensioni estese definite nel set di dati [!DNL Log Processing.cfg], [!DNL Transformation.cfg]e [!DNL dataset include] file.

* **Componenti del modello di query:** Metriche, dimensioni e filtri definiti nelle cartelle Dimension, Metriche e Filtri .
* **Aree di lavoro e visualizzazioni:** Aree di lavoro, rapporti, opzioni di menu e livelli globo.

Per ulteriori informazioni sull’utilizzo dei componenti del modello di query, delle aree di lavoro e delle visualizzazioni nelle mappe delle dipendenze, consulta la sezione *Guida utente di Data Workbench*.

I componenti profilo sono rappresentati da punti colorati (nodi) nella mappa. Le linee che collegano i nodi rappresentano le dipendenze, ovvero il modo in cui i componenti si relazionano tra loro. Una linea tra due nodi significa che un output del nodo a sinistra è un input del nodo a destra, cioè, il nodo a destra dipende dal nodo a sinistra.

## Visualizzazione dei componenti del set di dati {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Fai clic con il pulsante destro del mouse all’interno della mappa di dipendenza e fai clic su **[!UICONTROL Display]**.
1. Scegli **[!UICONTROL Dataset]**. A sinistra di [!DNL Dataset].

Per ulteriori informazioni sulle altre opzioni di visualizzazione, consulta la sezione *Guida utente di Data Workbench*.

La figura seguente mostra una mappa di dipendenza i cui nodi rappresentano le origini di registro, i campi, le trasformazioni e le dimensioni estese di un set di dati.

![](assets/vis_DependencyMap.png)

* Un nodo giallo-verde rappresenta una o più origini di registro o un filtro definito nel set di dati. Un nodo per un&#39;origine di registro appare sempre più a sinistra nella mappa.
* Un nodo grigio rappresenta un campo elencato nel parametro Fields in un [!DNL Log Processing.cfg] o [!DNL Log Processing Include]file.

* Un nodo blu rappresenta una trasformazione.
* Un nodo verde rappresenta una dimensione estesa.

>[!NOTE]
>
>Se il set di dati ha una singola origine di registro, la mappa visualizza Origine registro: *nome origine registro*. Se il set di dati dispone di più origini di registro, viene visualizzata la mappa *numero* Origini del registro, dove numero è il conteggio delle origini del registro. Ad esempio, se nel set di dati sono presenti tre origini di registro, nella mappa vengono visualizzate 3 Origini di registro.

Se non riesci a visualizzare tutti i nodi della mappa, puoi spostare la mappa, ingrandire o ridurre la visualizzazione per visualizzare l’intera mappa o per concentrarti su una particolare sezione. Per ulteriori informazioni sullo zoom, consulta il capitolo Utilizzo delle visualizzazioni di *Guida utente di Data Workbench*.

Quando si fa clic su un nodo, vengono evidenziati tutti i nodi che dipendono da tale nodo e tutti i nodi da cui dipende tale nodo e visualizzati i relativi nomi.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Un percorso evidenziato in una mappa di dipendenza non costituisce una selezione.

Quando fai clic con il pulsante destro del mouse su un nodo, puoi vedere le informazioni di identificazione di ciascun componente visualizzato sulla mappa e scegliere le opzioni di menu che ti consentono di visualizzare più dettagli sul componente o di modificarlo. Inoltre, è possibile eseguire ricerche di testo e visualizzare informazioni sulle prestazioni per trasformazioni e dimensioni estese.

Per informazioni su queste funzioni per le mappe delle dipendenze, vedere il capitolo relativo alle interfacce amministrative *Guida utente di Data Workbench*.
