---
description: È possibile effettuare selezioni all'interno delle mappe di processo per creare filtri che includono o escludono dati associati a un particolare nodo.
solution: Analytics
title: Selezione da una mappa di processo
topic: Data workbench
uuid: 7fd00090-c9ab-4bb6-8584-7de7b6f4b68c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Selezione da una mappa di processo{#make-a-selection-from-a-process-map}

È possibile effettuare selezioni all&#39;interno delle mappe di processo per creare filtri che includono o escludono dati associati a un particolare nodo.

La selezione all&#39;interno di una mappa di processo implica la dimensione del gruppo della mappa, che determina il modo in cui gli elementi della dimensione di base (ovvero i nodi della mappa) vengono raggruppati per formare le connessioni tra i nodi.

>[!NOTE]
>
>È possibile modificare la dimensione di gruppo predefinita per una mappa di processo. Consultate [Configurazione delle mappe](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6)di processo.

Quando si effettua una selezione basata su un nodo all&#39;interno di una mappa di processo, si selezionano tutti gli elementi della dimensione del gruppo che hanno interessato tale nodo. Per comprendere meglio il ruolo della dimensione del gruppo, prendere in considerazione i seguenti esempi:

* I filmati possono essere raggruppati dagli utenti che li hanno valutati. Ogni visualizzatore è un elemento della dimensione Utente, quindi la dimensione Utente è la dimensione di gruppo per la mappa di processo. Quando si effettua una selezione da un nodo per un filmato particolare, si crea un filtro che mostra i dati per gli utenti che hanno eseguito o meno la valutazione del filmato.
* Le pagine del sito Web possono essere raggruppate in base alle sessioni in cui sono state visualizzate. Ogni sessione è un elemento della dimensione Sessione, quindi la dimensione Sessione è la dimensione del gruppo per la mappa del processo. Quando si effettua una selezione da un nodo per una particolare pagina, si crea un filtro che mostra i dati per le sessioni durante le quali la pagina è stata o non è stata visualizzata.

**Selezione**

1. Fare clic con il pulsante destro del mouse su un nodo di una mappa di processo.
1. Fai clic su una delle seguenti opzioni per effettuare una selezione in base al nodo:

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL through node name]**: Filtra i dati per includere tutti gli elementi della dimensione del gruppo passati attraverso il nodo filtrando tutte le sessioni che non sono passate attraverso il nodo.

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL NOT through node name]**: Filtra i dati per includere tutti gli elementi della dimensione del gruppo che non sono passati attraverso il nodo filtrando tutte le sessioni che hanno passato attraverso il nodo.

![](assets/vis_2DProcessMap_Selections_Movie.png)

![](assets/vis_2DProcessMap_Selections_Page.png)

Quando si effettua una selezione in una mappa di processo 3D, il nodo per il quale viene effettuata la selezione viene cerchiato. I benchmark sono visualizzati intorno a ciascuna barra e consentono di confrontare i valori delle metriche con e senza la selezione. Consultate [Benchmark](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).

![](assets/vis_3DProcessMap_Selection.png)

