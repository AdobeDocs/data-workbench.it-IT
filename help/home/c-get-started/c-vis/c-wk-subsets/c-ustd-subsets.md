---
description: Informazioni concettuali sui sottoinsiemi.
title: Informazioni sui sottoinsiemi
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
exl-id: a75b36f9-d34d-4a4a-8a2c-15ae5461823c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# Informazioni sui sottoinsiemi{#understanding-subsets}

Informazioni concettuali sui sottoinsiemi.

Quando utilizzi un sottoinsieme, tieni presente quanto segue:

* Tutti i benchmark ora si riferiscono al tuo sottoinsieme e non all’intero set di dati, il che è molto più utile quando si analizza un sottoinsieme specifico. Consultare [Informazioni sui benchmark](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* L&#39;utilizzo di un sottoinsieme influisce su tutte le aree di lavoro perché il sottoinsieme viene applicato globalmente alla Data Workbench.
* I sottoinsiemi influiscono solo sulle metriche e sulle dimensioni normali, non sulle dimensioni normali.
* Quando si utilizza [!DNL Report], i sottoinsiemi non influiscono sui dati nei rapporti pubblicati affinché altri possano visualizzarli.
* Una volta applicato, il sottoinsieme è attivo per tutti i lavori successivi nel profilo, inclusa la successiva apertura di questa istanza di Data Workbench, fino a quando non la rimuoviate.
* L’unica posizione che indica che un sottoinsieme è stato applicato è il menu di scelta rapida accessibile facendo clic con il pulsante destro del mouse all’interno di un’area di lavoro.

   ![](assets/mnu_Subset.png)

* È necessario lavorare online per modificare o rimuovere un sottoinsieme. Se lavori offline e hai applicato un sottoinsieme, non puoi visualizzare i risultati dell’intero set di dati. Consulta [Funzionamento offline e online](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

   >[!NOTE]
   >
   >La dimensione del sottoinsieme è limitata alla quantità di dati presenti nel filtro che si trova su un singolo server di Data Workbench. Pertanto, se il set di dati si estende su un cluster di server Data Workbench, i dati per il sottoinsieme provengono da un solo server Data Workbench nel cluster.

Un utente di un grande rivenditore desidera creare un sottoinsieme (cache locale) di una particolare settimana lavorativa di dati e quindi eseguire query solo su quella settimana di dati. A questo scopo, l’utente crea un sottoinsieme per i giorni di interesse.

L’esempio seguente mostra un grafico a barre dei visitatori nel tempo e una legenda della metrica Traffico . La prima figura non contiene selezioni: tutti i dati nel set di dati sono rappresentati. La seconda figura mostra i dati per un sottoinsieme di Giorni = {...} per Visitatori, in cui Giorni si basa su una selezione degli elementi dal 1° aprile al 5 aprile nella dimensione Giorno.

![](assets/client-sub1.png)
