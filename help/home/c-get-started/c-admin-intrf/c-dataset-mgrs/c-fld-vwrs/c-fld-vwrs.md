---
description: Un visualizzatore di campi è una tabella contenente i valori di uno o più campi di dati.
title: Visualizzatore di campi
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# Visualizzatore di campi{#field-viewer}

Un visualizzatore di campi è una tabella contenente i valori di uno o più campi di dati.

I campi i cui valori vengono visualizzati sono input o output delle origini di registro di un set di dati, trasformazioni o dimensioni estese. Il nome del campo viene visualizzato nell’intestazione della colonna e ogni riga contiene il valore del campo per una singola riga di dati di origine. Poiché i visualizzatori di campi consentono di visualizzare i valori di un campo, sono utili per scrivere e testare [espressioni regolari](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

È possibile aprire un visualizzatore di campi come callout da una mappa [!DNL Transformation Dependency] o come visualizzazione autonoma dal menu [!DNL Admin]:

* Creazione di un visualizzatore di campi da una mappa [!DNL Transformation Dependency]. Quando apri un visualizzatore di campi da una mappa [!DNL Transformation Dependency], il visualizzatore viene compilato automaticamente in base all’origine del registro, alla trasformazione o alla dimensione su cui fai clic con il pulsante destro del mouse. Per un’origine di registro o una trasformazione, i campi nel visualizzatore sono input o output dell’origine di registro o della trasformazione. Per una dimensione, i campi sono input della dimensione. Puoi aggiungere e rimuovere i campi desiderati.

* Creazione di un visualizzatore di campi come visualizzazione autonoma. Quando apri un visualizzatore di campi come visualizzazione indipendente, puoi creare un [!DNL Log Processing Field Viewer] o un [!DNL Transformation Field Viewer]. Il visualizzatore è vuoto e devi aggiungere i campi desiderati al visualizzatore. Per un file [!DNL Log Processing Field Viewer], è possibile aggiungere campi dal file [!DNL Log Processing.cfg] o da qualsiasi file [!DNL Log Processing Dataset Include]. Per un file [!DNL Transformation Field Viewer], è possibile aggiungere campi dal file [!DNL Transformation.cfg] o da qualsiasi file [!DNL Transformation Dataset Include].

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>I visualizzatori di campi non sono visualizzazioni di tabelle; pertanto, non hanno le proprietà associate alle tabelle.

Per informazioni sull’aggiunta e la rimozione di campi e filtri all’interno di un visualizzatore di campi, consulta [Interfacce amministrative](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
