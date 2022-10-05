---
description: Dopo aver aggiunto il nuovo campo a Log Processing.cfg e creato la nuova trasformazione Split e la dimensione estesa, puoi visualizzare la nuova dimensione estesa creata non appena la fase Fast Input della rielaborazione dei dati è terminata.
solution: Analytics
title: Visualizzazione dei risultati dell’esperimento
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
exl-id: cada693c-79cb-4f49-a2f0-6ff60425be1c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---

# Visualizzazione dei risultati dell’esperimento{#viewing-the-experiment-results}

{{eol}}

Dopo aver aggiunto il nuovo campo a Log Processing.cfg e creato la nuova trasformazione Split e la dimensione estesa, puoi visualizzare la nuova dimensione estesa creata non appena la fase Fast Input della rielaborazione dei dati è terminata.

Questa dimensione, per impostazione predefinita, visualizza il numero di sessioni per ciascuno dei gruppi di esperimenti.

**Per visualizzare la dimensione dell’esperimento**

* In qualsiasi area di lavoro in [!DNL Insight], apri una tabella con la dimensione dell’esperimento creata.

   Gli elementi dimensionali dell&#39;esperimento, che rappresentano ogni esperimento in esecuzione e ogni gruppo all&#39;interno di ogni esperimento, vengono visualizzati con il numero corrente di sessioni per ogni gruppo. Ogni gruppo viene denominato nel formato seguente utilizzando il nome dell&#39;esperimento seguito dal nome del gruppo:

   *Nome esperimento.Nome gruppo*

   Ad esempio: [!DNL New Homepage.Control]

La tabella seguente mostra la dimensione Gruppi di esperimenti controllati creata in [!DNL Transformation.cfg] e ciascuno degli esperimenti e dei loro gruppi.

L’esperimento New Homepage viene mostrato nella parte inferiore della tabella con i relativi due gruppi: Controllo e indice2.

![](assets/controlledexpgrps.png)

Ora puoi utilizzare la dimensione dell’esperimento e tutte le metriche pertinenti per esplorare e interpretare i risultati dell’esperimento, nonché creare utili rapporti che ne descrivono i risultati.
