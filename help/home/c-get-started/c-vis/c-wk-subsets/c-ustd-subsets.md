---
description: Informazioni concettuali sui sottoinsiemi.
solution: Analytics
title: Informazioni sui sottoinsiemi
topic: Data workbench
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informazioni sui sottoinsiemi{#understanding-subsets}

Informazioni concettuali sui sottoinsiemi.

Quando si utilizza un sottoinsieme, tenere a mente quanto segue:

* Tutti i benchmark sono ora correlati al vostro sottoinsieme, non all&#39;intero set di dati, il che è molto più utile quando si analizza un sottoinsieme specifico. Consultate [Benchmark](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* L&#39;utilizzo di un sottoinsieme interessa tutte le aree di lavoro, poiché il sottoinsieme viene applicato a livello globale a Workbench dati.
* I sottoinsiemi interessano solo le metriche e le dimensioni normali, non le dimensioni normali.
* Quando si utilizza [!DNL Report], i sottoinsiemi non influiscono sui dati nei rapporti pubblicati affinché altri possano visualizzarli.
* Una volta applicato, il sottoinsieme viene applicato a tutti i lavori successivi del profilo, inclusa la successiva apertura dell&#39;istanza di Workbench dati, fino alla sua rimozione.
* L’unica posizione che indica che è stato applicato un sottoinsieme è il menu di scelta rapida accessibile facendo clic con il pulsante destro del mouse all’interno di un’area di lavoro.

   ![](assets/mnu_Subset.png)

* Per modificare o rimuovere un sottoinsieme è necessario lavorare online. Se lavorate offline e avete applicato un sottoinsieme, non potete visualizzare i risultati dell&#39;intero set di dati. Consultate [Utilizzo offline e online](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

   >[!NOTE]
   >
   >Le dimensioni del sottoinsieme sono limitate alla quantità di dati contenuti nel filtro presente in un singolo server Workbench dati. Pertanto, se il dataset si estende su un cluster di server Workbench dati, i dati per il sottoinsieme provengono da un solo server Workbench dati del cluster.

Un utente di un grande retailer desidera creare un sottoinsieme (cache locale) di una particolare settimana lavorativa di dati e quindi eseguire query solo su quella settimana di dati. A questo scopo, l&#39;utente crea un sottoinsieme per i giorni di interesse.

L’esempio seguente mostra un grafico a barre dei visitatori nel tempo e una legenda della metrica Traffico. La prima figura non contiene selezioni: tutti i dati del set di dati sono rappresentati. La seconda figura mostra i dati per un sottoinsieme di Giorni = {...} per Visitatori, in cui Giorni si basa su una selezione degli elementi dal 1° al 5 aprile nella dimensione Giorno.

![](assets/client-sub1.png)

