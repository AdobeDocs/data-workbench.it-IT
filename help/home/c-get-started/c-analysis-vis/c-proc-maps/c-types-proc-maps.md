---
description: Informazioni sui diversi tipi di mappe del processo.
title: Tipi di mappe del processo
uuid: 19473b77-13c1-4829-b018-d3316e434ba4
exl-id: 8bac7036-c7fe-4566-8e59-08e1ddc7ddb7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 1%

---

# Tipi di mappe del processo{#types-of-process-maps}

Informazioni sui diversi tipi di mappe del processo.

## Mappe del processo 2D {#section-ea7fbdb80b1b44aebcd9e4090b6540bf}

Le mappe di processo bidimensionali forniscono una visualizzazione bidimensionale dell&#39;attività tra gli elementi dimensionali. La dimensione di un nodo in una mappa del processo 2D è proporzionale al valore della metrica associata a quel nodo. Inoltre, lo spessore e l’intensità di una freccia tra due nodi sono proporzionali alla media dei valori della metrica per tali nodi.

All&#39;interno di una mappa del processo 2D, è possibile eseguire una delle seguenti operazioni:

* Selezionare, spostare, rimuovere ed etichettare i nodi
* Effettuare le selezioni
* Salva dimensioni
* Creare altre visualizzazioni
* Attivare i collegamenti colore
* Visualizzazione delle quantità di metriche
* Aggiungi callout

La mappa del processo 2D nell&#39;esempio seguente mostra i nodi corrispondenti ai nomi dei filmati. Ogni nome del filmato è un elemento della dimensione Filmato, definita in un set di dati costituito da dati del filmato. La dimensione Filmato è la dimensione di base per questa mappa del processo.

![](assets/vis_2DProcessMap_MovieNodes.png)

Nell’esempio, le dimensioni di ciascun nodo e lo spessore e l’intensità di ciascuna freccia sono proporzionali alla metrica Valutazioni, che è un conteggio delle valutazioni ricevute da un filmato. Pertanto, un filmato con un nodo di grandi dimensioni, ad esempio *Giorno di indipendenza*, ha più valutazioni di un filmato con un nodo piccolo, ad esempio *Orizzonte evento*. È inoltre possibile vedere che più visualizzatori di film classificati *Giorno di indipendenza* prima *Montagna fredda* rispetto agli stessi film classificati nell&#39;ordine opposto. Le frecce non indicano che i visualizzatori hanno valutato *Giorno di indipendenza* e poi hanno valutato *Montagna fredda* immediatamente dopo, o viceversa. I visualizzatori potrebbero aver valutato altri film nel mezzo, ma questi film non vengono mostrati su questa mappa.

## Mappe della metrica 2D {#section-a9b846fc71224058918fbc378315effe}

Le mappe metriche bidimensionali sono un tipo di mappa del processo 2D che posiziona i nodi in base al valore di una particolare metrica. In molti casi, la metrica utilizzata con la mappa metrica 2D è Conversione o Mantenimento. Le mappe di conversione e fidelizzazione consentono di comprendere quali passaggi nei processi dei canali rivolti al cliente influenzano la conversione e la fidelizzazione dei clienti.

>[!NOTE]
>
>La metrica utilizzata con una mappa metrica 2D deve essere espressa come percentuale.

In una mappa metrica di conversione, i nodi con conversione dello 0% vengono tracciati a sinistra del grafico e le pagine con conversione del 100% vengono tracciate a destra. L’attività tra i nodi viene visualizzata, facilitando la visualizzazione dei passaggi di un processo che determinano una conversione maggiore o minore e dei passaggi che determinano l’abbandono. Un’analisi della conversione del processo è un modo efficace per confrontare processi o implementazioni diverse dello stesso processo.

![](assets/vis_2DMetricMap_Conversion.png)

Analogamente, le mappe di fidelizzazione mostrano gli elementi con una fidelizzazione dello 0% a sinistra del grafico e gli elementi con una fidelizzazione del 100% a destra. Puoi vedere il tasso di fidelizzazione per ogni nodo sulla mappa, che ti aiuta a determinare quali elementi influenzano i clienti da restituire.

![](assets/vis_2DMetricMap_Retention.png)

>[!NOTE]
>
>Non è possibile spostare i nodi in mappe metriche 2D orizzontalmente. Le mappe metriche sono progettate per posizionare i nodi da sinistra a destra in base ai loro valori metrici.

## Mappe del processo 3D {#section-80acb63ea0994af1af7faef3c6264e51}

Le mappe del processo tridimensionale forniscono una visualizzazione tridimensionale dell’attività tra gli elementi dimensionali. L&#39;altezza di una barra in una mappa del processo 3D è proporzionale al valore della metrica associata a quel nodo. Come per le mappe del processo 2D, lo spessore e l’intensità dei connettori tra due nodi sono proporzionali alla media dei valori della metrica per tali nodi. All&#39;interno di una mappa del processo 3D, puoi eseguire una delle seguenti operazioni:

* Selezionare, spostare, rimuovere ed etichettare i nodi
* Effettuare le selezioni
* Salva dimensioni
* Creare altre visualizzazioni
* Attivare i collegamenti colore

La mappa del processo 3D nell&#39;esempio seguente mostra i nodi corrispondenti alle pagine di un sito web. Ogni pagina è un elemento della dimensione Pagina, definita in un set di dati costituito da dati sul traffico web. La dimensione Pagina è la dimensione di base per questa mappa del processo.

![](assets/vis_3DProcessMap_PageNodes.png)

Nell’esempio, l’altezza di ciascuna barra e lo spessore e l’intensità di ciascun connettore sono proporzionali alla metrica Sessions, un conteggio delle sessioni in cui sono state visualizzate le pagine. Pertanto, una pagina con barra alta, come /faq/all/FAQ, è stata visualizzata durante più sessioni di una pagina con una barra breve, come /vs/demo. Le connessioni tra due pagine non indicano che una pagina è stata visualizzata immediatamente prima o dopo un’altra durante una determinata sessione. È possibile che altre pagine siano state visualizzate durante la stessa sessione, ma queste non vengono visualizzate su questa mappa.
