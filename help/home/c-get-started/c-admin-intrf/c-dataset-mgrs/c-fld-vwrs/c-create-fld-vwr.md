---
description: È possibile aprire un visualizzatore di campi come callout da una mappa di dipendenze o come visualizzazione autonoma dal menu Admin.
solution: Analytics
title: Creare un visualizzatore di campi
topic: Data workbench
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creare un visualizzatore di campi{#create-a-field-viewer}

È possibile aprire un visualizzatore di campi come callout da una mappa di dipendenze o come visualizzazione autonoma dal menu Admin.

## Creazione di un visualizzatore di campi da una mappa di dipendenza {#section-040cb83c902b49c48b841d35abc127e5}

Quando aprite un visualizzatore di campi da una mappa di dipendenze (come mostrato in Visualizzatori [di campi di](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)apertura), il visualizzatore viene popolato automaticamente in base all’origine del registro, alla trasformazione o alla dimensione su cui avete fatto clic con il pulsante destro del mouse. Per un’origine di registro o una trasformazione, i campi nel visualizzatore sono input o output dell’origine di registro o trasformazione. Per una dimensione, i campi sono input della dimensione. Potete aggiungere e rimuovere i campi come desiderate.

## Creare un visualizzatore di campo come visualizzazione indipendente {#section-11d10e46631d4fdca45d7534336e1e80}

Quando si apre un visualizzatore di campi come visualizzazione indipendente, è possibile creare una [!DNL Log Processing Field Viewer] o una [!DNL Transformation Field Viewer]. Il visualizzatore è vuoto e dovete aggiungere i campi desiderati al visualizzatore. Per un [!DNL Log Processing Field Viewer], è possibile aggiungere campi dal [!DNL Log Processing.cfg] file o da qualsiasi [!DNL Log Processing dataset include] file. Per un [!DNL Transformation Field Viewer], è possibile aggiungere campi dal [!DNL Transformation.cfg] file o da qualsiasi [!DNL Transformation dataset include] file.

Per ulteriori informazioni sulla configurazione e l&#39;inclusione di file, vedere la Guida alla configurazione del *set di dati*.

## Aggiunta e rimozione di un campo {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**Aggiunta di un campo a un visualizzatore di campi**

* Fare clic con il pulsante destro del mouse all&#39;interno del visualizzatore dei campi e scegliere **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

   -or-

* Fare clic con il pulsante destro del mouse all&#39;interno di una colonna esistente nel visualizzatore dei campi e scegliere **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

Il nome del campo fa riferimento al nome del campo e l’istanza fa riferimento a dove viene utilizzato il campo nella configurazione del set di dati, ad esempio una fase di elaborazione del set di dati o una trasformazione. Alcuni campi vengono utilizzati in più posizioni all&#39;interno della configurazione del set di dati (ad esempio, un campo può essere modificato da più trasformazioni), pertanto è necessario selezionare l&#39;istanza del campo da aggiungere al visualizzatore del campo.

Nell’elenco dei campi disponibili, viene visualizzata una X a sinistra di qualsiasi campo già visualizzato nel visualizzatore.

**Rimozione di un campo da un visualizzatore di campi**

* Fare clic con il pulsante destro del mouse all&#39;interno della colonna relativa al campo da rimuovere e fare clic **[!UICONTROL Remove Field]**.

