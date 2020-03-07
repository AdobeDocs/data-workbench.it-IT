---
description: Quando visualizzate i componenti del set di dati su una mappa di dipendenza, potete attivare l’opzione di visualizzazione Includi blocchi di file.
solution: Analytics
title: Blocchi di file
topic: Data workbench
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Blocchi di file{#file-blocks}

Quando visualizzate i componenti del set di dati su una mappa di dipendenza, potete attivare l’opzione di visualizzazione Includi blocchi di file.

Quando questa opzione è attivata, la mappa visualizza un singolo nodo blu per tutte le trasformazioni definite in un file di configurazione del set di dati e un singolo nodo verde per tutte le dimensioni estese definite in un file di configurazione del set di dati. Ad esempio, se un [!DNL log processing dataset include] file include le definizioni di tre trasformazioni, la mappa visualizza un nodo blu che rappresenta le tre trasformazioni. Analogamente, se un [!DNL transformation dataset include] file include le definizioni di due dimensioni estese, la mappa visualizza un nodo verde che rappresenta le due dimensioni estese.

## Blocchi di trasformazione {#section-c442730394264a0b850792a32eaaa2da}

Ogni nodo blu è un blocco di trasformazione e presenta le seguenti opzioni:

* Per visualizzare i campi di input del blocco di trasformazione, fare clic con il pulsante destro del mouse sul nodo del blocco e fare clic **[!UICONTROL Inputs]**.
* Per visualizzare i campi di output del blocco di trasformazione, fare clic con il pulsante destro del mouse sul nodo del blocco e fare clic **[!UICONTROL Outputs]**.
* Per modificare una qualsiasi delle trasformazioni nel blocco, fare clic con il pulsante destro del mouse sul nodo del blocco e fare clic **[!UICONTROL Edit Configuration]**. Il callout visualizzato contiene l&#39;intero file di configurazione in cui sono definite tutte le trasformazioni. Potete quindi modificare i parametri come desiderate. Per ulteriori informazioni su questi parametri, vedere la Guida alla configurazione del *set di dati*.

* Per visualizzare tutte le trasformazioni nel blocco, fare clic con il pulsante destro del mouse sul nodo del blocco di trasformazione e quindi fare clic **[!UICONTROL Show Details]**. Il callout visualizzato contiene un&#39;altra mappa delle dipendenze che mostra i nodi per tutte le trasformazioni del blocco.

## Blocchi dimensione {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

Ogni nodo verde è un blocco dimensione e presenta le seguenti opzioni:

* Per visualizzare i campi di input o la dimensione padre del blocco dimensione, fare clic con il pulsante destro del mouse sul nodo del blocco e fare clic **[!UICONTROL Inputs]**.
* Per visualizzare le dimensioni di output del blocco di dimensioni, fare clic con il pulsante destro del mouse sul nodo del blocco e fare clic **[!UICONTROL Outputs]**.

