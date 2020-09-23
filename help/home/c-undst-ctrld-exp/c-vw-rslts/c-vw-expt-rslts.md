---
description: Dopo aver aggiunto il nuovo campo a Log Processing.cfg e creato la nuova trasformazione Split e la dimensione estesa, è possibile visualizzare la nuova dimensione estesa creata non appena la fase di Fast Input della rielaborazione dei dati è terminata.
solution: Analytics,Analytics
title: Visualizzazione dei risultati dell’esperimento
topic: Data workbench
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---


# Visualizzazione dei risultati dell’esperimento{#viewing-the-experiment-results}

Dopo aver aggiunto il nuovo campo a Log Processing.cfg e creato la nuova trasformazione Split e la dimensione estesa, è possibile visualizzare la nuova dimensione estesa creata non appena la fase di Fast Input della rielaborazione dei dati è terminata.

Questa dimensione, per impostazione predefinita, mostra il numero di sessioni per ciascun gruppo di esperimenti.

**Per visualizzare la dimensione dell&#39;esperimento**

* In qualsiasi area di lavoro di [!DNL Insight], aprite una tabella con la dimensione dell&#39;esperimento creata.

   Gli elementi della dimensione dell&#39;esperimento, che rappresentano ciascun esperimento attualmente in esecuzione e ciascun gruppo all&#39;interno di ciascun esperimento, vengono visualizzati con il numero corrente di sessioni per ciascun gruppo. Ogni gruppo viene denominato nel seguente formato utilizzando il nome dell’esperimento seguito dal nome del gruppo:

   *Nome esperimento.Nome gruppo*

   Ad esempio: [!DNL New Homepage.Control]

La tabella seguente mostra la dimensione Gruppi di esperti controllati creata in [!DNL Transformation.cfg] e in ciascuno degli esperimenti e dei relativi gruppi.

L’esperimento New Homepage (Nuova homepage) è presentato in fondo alla tabella con i relativi due gruppi: Controllo e indice2.

![](assets/controlledexpgrps.png)

Ora potete utilizzare la dimensione dell&#39;esperimento e tutte le metriche pertinenti per esplorare e interpretare i risultati dell&#39;esperimento, nonché creare utili rapporti che descrivano tali risultati.
