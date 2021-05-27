---
description: Quando visualizzi i componenti del set di dati su una mappa di dipendenza, puoi abilitare l’opzione di visualizzazione Includi blocchi di file .
title: Blocchi di file
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
exl-id: 04b0faf1-a16d-4e46-b790-5fe2023f2ba1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 1%

---

# Blocchi di file{#file-blocks}

Quando visualizzi i componenti del set di dati su una mappa di dipendenza, puoi abilitare l’opzione di visualizzazione Includi blocchi di file .

Quando questa opzione è abilitata, la mappa visualizza un singolo nodo blu per tutte le trasformazioni definite in un file di configurazione del set di dati e un singolo nodo verde per tutte le dimensioni estese definite in un file di configurazione del set di dati. Ad esempio, se un file [!DNL log processing dataset include] include le definizioni di tre trasformazioni, la mappa visualizza un nodo blu che rappresenta le tre trasformazioni. Analogamente, se un file [!DNL transformation dataset include] include le definizioni di due dimensioni estese, la mappa visualizza un nodo verde che rappresenta le due dimensioni estese.

## Blocchi di trasformazione {#section-c442730394264a0b850792a32eaaa2da}

Ogni nodo blu è un blocco di trasformazione e dispone delle seguenti opzioni:

* Per visualizzare i campi di input del blocco di trasformazione, fare clic con il pulsante destro del mouse sul nodo del blocco e fare clic su **[!UICONTROL Inputs]**.
* Per visualizzare i campi di output del blocco di trasformazione, fare clic con il pulsante destro del mouse sul nodo del blocco e fare clic su **[!UICONTROL Outputs]**.
* Per modificare una delle trasformazioni nel blocco , fai clic con il pulsante destro del mouse sul nodo del blocco e fai clic su **[!UICONTROL Edit Configuration]**. Il callout visualizzato contiene l&#39;intero file di configurazione in cui sono definite tutte le trasformazioni. Puoi quindi modificare i parametri come desiderato. Per ulteriori informazioni su questi parametri, consulta la *Guida alla configurazione del set di dati*.

* Per visualizzare tutte le trasformazioni nel blocco , fai clic con il pulsante destro del mouse sul nodo del blocco di trasformazione e fai clic su **[!UICONTROL Show Details]**. Il callout visualizzato contiene un&#39;altra mappa di dipendenza che mostra i nodi di tutte le trasformazioni nel blocco.

## Blocchi di Dimension {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

Ogni nodo verde è un blocco di dimensione e dispone delle seguenti opzioni:

* Per visualizzare i campi di input o la dimensione padre del blocco di dimensione, fai clic con il pulsante destro del mouse sul nodo del blocco e fai clic su **[!UICONTROL Inputs]**.
* Per visualizzare le dimensioni di output del blocco di dimensione, fai clic con il pulsante destro del mouse sul nodo del blocco e fai clic su **[!UICONTROL Outputs]**.
