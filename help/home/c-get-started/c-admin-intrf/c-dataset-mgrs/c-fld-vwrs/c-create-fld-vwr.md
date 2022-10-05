---
description: È possibile aprire un visualizzatore di campi come callout da una mappa di dipendenza o come visualizzazione autonoma dal menu Amministrazione.
title: Creare un visualizzatore di campi
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
exl-id: a2563dbb-1d1f-4ed8-b73b-6ac7a2687405
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 2%

---

# Creare un visualizzatore di campi{#create-a-field-viewer}

{{eol}}

È possibile aprire un visualizzatore di campi come callout da una mappa di dipendenza o come visualizzazione autonoma dal menu Amministrazione.

## Creare un visualizzatore di campi da una mappa di dipendenza {#section-040cb83c902b49c48b841d35abc127e5}

Quando si apre un visualizzatore di campi da una mappa di dipendenza (come mostrato in [Apertura dei visualizzatori di campi](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)), il visualizzatore viene compilato automaticamente in base all’origine del registro, alla trasformazione o alla dimensione su cui fai clic con il pulsante destro del mouse. Per un’origine di registro o una trasformazione, i campi nel visualizzatore sono input o output dell’origine di registro o della trasformazione. Per una dimensione, i campi sono input della dimensione. Puoi aggiungere e rimuovere i campi desiderati.

## Creare un visualizzatore di campi come visualizzazione autonoma {#section-11d10e46631d4fdca45d7534336e1e80}

Quando apri un visualizzatore di campi come visualizzazione autonoma, puoi creare una [!DNL Log Processing Field Viewer] o [!DNL Transformation Field Viewer]. Il visualizzatore è vuoto e devi aggiungere i campi desiderati al visualizzatore. Per [!DNL Log Processing Field Viewer], puoi aggiungere campi dalla sezione [!DNL Log Processing.cfg] o qualsiasi [!DNL Log Processing dataset include] file. Per [!DNL Transformation Field Viewer], puoi aggiungere campi dalla sezione [!DNL Transformation.cfg] o qualsiasi [!DNL Transformation dataset include] file.

Per ulteriori informazioni sulla configurazione e sull’inclusione dei file, consulta la sezione *Guida alla configurazione del set di dati*.

## Aggiungere e rimuovere un campo {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**Aggiunta di un campo a un visualizzatore di campi**

* Fai clic con il pulsante destro del mouse nel visualizzatore di campi e fai clic su **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

   -oppure-

* Fai clic con il pulsante destro del mouse all’interno di una colonna esistente nel visualizzatore di campi e fai clic su **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

Il nome del campo fa riferimento al nome del campo e l’istanza fa riferimento a dove nella configurazione del set di dati viene utilizzato il campo, ad esempio una fase di elaborazione del set di dati o una trasformazione. Alcuni campi vengono utilizzati in più posizioni all’interno della configurazione del set di dati (ad esempio, un campo può essere modificato da più trasformazioni), pertanto devi selezionare l’istanza del campo da aggiungere al visualizzatore di campi.

Nell’elenco dei campi disponibili, a sinistra di qualsiasi campo già visualizzato nel visualizzatore viene visualizzata una X.

**Rimozione di un campo da un visualizzatore di campi**

* Fare clic con il pulsante destro del mouse nella colonna relativa al campo da rimuovere e fare clic su **[!UICONTROL Remove Field]**.
