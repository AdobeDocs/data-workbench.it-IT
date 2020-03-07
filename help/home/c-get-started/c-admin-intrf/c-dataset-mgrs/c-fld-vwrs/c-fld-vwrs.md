---
description: Un visualizzatore di campi è una tabella contenente i valori di uno o più campi di dati.
solution: Analytics
title: Visualizzatore di campi
topic: Data workbench
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualizzatore di campi{#field-viewer}

Un visualizzatore di campi è una tabella contenente i valori di uno o più campi di dati.

I campi i cui valori sono visualizzati sono input o output delle origini di registro di un dataset, trasformazioni o dimensioni estese. Il nome del campo è visualizzato nell&#39;intestazione della colonna e ogni riga contiene il valore del campo per una singola riga di dati di origine. Poiché i visualizzatori di campi consentono di visualizzare i valori di un campo, sono utili per scrivere e testare le espressioni [](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)regolari.

È possibile aprire un visualizzatore di campi come callout da una [!DNL Transformation Dependency] mappa o come visualizzazione autonoma dal [!DNL Admin] menu:

* Creazione di un visualizzatore di campi da una [!DNL Transformation Dependency] mappa. Quando aprite un visualizzatore di campi da una [!DNL Transformation Dependency] mappa, il visualizzatore viene popolato automaticamente in base all’origine del registro, alla trasformazione o alla dimensione su cui avete fatto clic con il pulsante destro del mouse. Per un’origine di registro o una trasformazione, i campi nel visualizzatore sono input o output dell’origine di registro o trasformazione. Per una dimensione, i campi sono input della dimensione. Potete aggiungere e rimuovere i campi come desiderate.

* Creazione di un visualizzatore di campi come visualizzazione indipendente. Quando si apre un visualizzatore di campi come visualizzazione indipendente, è possibile creare una [!DNL Log Processing Field Viewer] o una [!DNL Transformation Field Viewer]. Il visualizzatore è vuoto e dovete aggiungere i campi desiderati al visualizzatore. Per un [!DNL Log Processing Field Viewer], è possibile aggiungere campi dal [!DNL Log Processing.cfg] file o da qualsiasi [!DNL Log Processing Dataset Include] file. Per un [!DNL Transformation Field Viewer], è possibile aggiungere campi dal [!DNL Transformation.cfg] file o da qualsiasi [!DNL Transformation Dataset Include] file.

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>i visualizzatori di campo non sono visualizzazioni di tabella; pertanto, non hanno le proprietà associate alle tabelle.

Per informazioni sull&#39;aggiunta e la rimozione di campi e di filtri all&#39;interno di un visualizzatore di campi, consultate Interfacce [amministrative](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
