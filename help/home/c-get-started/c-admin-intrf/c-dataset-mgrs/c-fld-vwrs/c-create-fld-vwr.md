---
description: È possibile aprire un visualizzatore di campi come callout da una mappa di dipendenza o come visualizzazione autonoma dal menu Amministrazione.
title: Creare un visualizzatore di campi
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
exl-id: a2563dbb-1d1f-4ed8-b73b-6ac7a2687405
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 2%

---

# Creare un visualizzatore di campi{#create-a-field-viewer}

È possibile aprire un visualizzatore di campi come callout da una mappa di dipendenza o come visualizzazione autonoma dal menu Amministrazione.

## Creare un visualizzatore di campi da una mappa di dipendenza {#section-040cb83c902b49c48b841d35abc127e5}

Quando si apre un visualizzatore di campi da una mappa di dipendenza (come mostrato in [Visualizzatori di campi di apertura](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)), il visualizzatore viene compilato automaticamente in base all&#39;origine del registro, alla trasformazione o alla dimensione su cui si fa clic con il pulsante destro del mouse. Per un’origine di registro o una trasformazione, i campi nel visualizzatore sono input o output dell’origine di registro o della trasformazione. Per una dimensione, i campi sono input della dimensione. Puoi aggiungere e rimuovere i campi desiderati.

## Creare un visualizzatore di campi come visualizzazione autonoma {#section-11d10e46631d4fdca45d7534336e1e80}

Quando apri un visualizzatore di campi come visualizzazione indipendente, puoi creare un [!DNL Log Processing Field Viewer] o un [!DNL Transformation Field Viewer]. Il visualizzatore è vuoto e devi aggiungere i campi desiderati al visualizzatore. Per un file [!DNL Log Processing Field Viewer], è possibile aggiungere campi dal file [!DNL Log Processing.cfg] o da qualsiasi file [!DNL Log Processing dataset include]. Per un file [!DNL Transformation Field Viewer], è possibile aggiungere campi dal file [!DNL Transformation.cfg] o da qualsiasi file [!DNL Transformation dataset include].

Per ulteriori informazioni sulla configurazione e sull&#39;inclusione dei file, vedere la *Guida alla configurazione del set di dati*.

## Aggiungi e rimuovi un campo {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**Aggiunta di un campo a un visualizzatore di campi**

* Fai clic con il pulsante destro del mouse all’interno del visualizzatore di campi e fai clic su **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]***.

   -oppure-

* Fai clic con il pulsante destro del mouse all’interno di una colonna esistente nel visualizzatore di campi e fai clic su **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

Il nome del campo fa riferimento al nome del campo e l’istanza fa riferimento a dove nella configurazione del set di dati viene utilizzato il campo, ad esempio una fase di elaborazione del set di dati o una trasformazione. Alcuni campi vengono utilizzati in più posizioni all’interno della configurazione del set di dati (ad esempio, un campo può essere modificato da più trasformazioni), pertanto devi selezionare l’istanza del campo da aggiungere al visualizzatore di campi.

Nell’elenco dei campi disponibili, a sinistra di qualsiasi campo già visualizzato nel visualizzatore viene visualizzata una X.

**Rimozione di un campo da un visualizzatore di campi**

* Fare clic con il pulsante destro del mouse all&#39;interno della colonna relativa al campo da rimuovere e fare clic su **[!UICONTROL Remove Field]**.
