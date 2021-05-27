---
description: Puoi effettuare selezioni all’interno delle mappe del processo per creare filtri che includono o escludono i dati associati a un particolare nodo.
title: Selezione da una mappa del processo
uuid: 7fd00090-c9ab-4bb6-8584-7de7b6f4b68c
exl-id: 8ede395f-906a-49e0-8ff8-b43a326275e5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# Selezione da una mappa del processo{#make-a-selection-from-a-process-map}

Puoi effettuare selezioni all’interno delle mappe del processo per creare filtri che includono o escludono i dati associati a un particolare nodo.

La selezione all’interno di una mappa del processo comporta la dimensione del gruppo della mappa, che determina il modo in cui gli elementi della dimensione di base (ovvero i nodi della mappa) vengono raggruppati per formare le connessioni tra i nodi.

>[!NOTE]
>
>È possibile modificare la dimensione di gruppo predefinita per una mappa del processo. Consulta [Configurazione di Process Maps](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).

Quando effettui una selezione basata su un nodo all’interno di una mappa del processo, stai selezionando tutti gli elementi della dimensione del gruppo che coinvolgono quel nodo. Per comprendere meglio il ruolo della dimensione gruppo, considera gli esempi seguenti:

* I film possono essere raggruppati dai visualizzatori che li hanno valutati. Ciascun visualizzatore è un elemento della dimensione Utente, quindi la dimensione Utente è la dimensione di gruppo per la mappa del processo. Quando si effettua una selezione da un nodo per un filmato specifico, si crea un filtro che mostra i dati per gli utenti che hanno eseguito o meno la valutazione del filmato.
* Le pagine del sito web possono essere raggruppate in base alle sessioni in cui sono state visualizzate. Ogni sessione è un elemento della dimensione Sessione, quindi la dimensione Sessione è la dimensione di gruppo per la mappa del processo. Quando effettui una selezione da un nodo per una pagina particolare, crea un filtro che mostra i dati per le sessioni durante le quali la pagina è stata o non è stata visualizzata.

**Selezione**

1. Fai clic con il pulsante destro del mouse su un nodo di una mappa del processo.
1. Fai clic su una delle seguenti opzioni per effettuare una selezione in base al nodo:

   * **[!UICONTROL Select]***  **[!UICONTROL group dimension name +s]***  **[!UICONTROL through node name]**: Filtra i dati per includere tutti gli elementi della dimensione di gruppo che hanno passato attraverso il nodo filtrando tutte le sessioni che non sono passate attraverso il nodo.

   * **[!UICONTROL Select]***  **[!UICONTROL group dimension name +s]***  **[!UICONTROL NOT through node name]**: Filtra i dati per includere tutti gli elementi della dimensione gruppo che non sono passati attraverso il nodo filtrando tutte le sessioni passate attraverso il nodo.

![](assets/vis_2DProcessMap_Selections_Movie.png)

![](assets/vis_2DProcessMap_Selections_Page.png)

Quando si effettua una selezione in una mappa del processo 3D, il nodo per il quale viene effettuata la selezione viene cerchiato. I benchmark vengono visualizzati intorno a ogni barra e consentono di confrontare i valori delle metriche con e senza la selezione. Consultare [Informazioni sui benchmark](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).

![](assets/vis_3DProcessMap_Selection.png)
