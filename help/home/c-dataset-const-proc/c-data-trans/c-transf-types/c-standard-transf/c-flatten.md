---
description: La trasformazione Flatten prende un vettore di stringhe e mappa ogni valore nel proprio campo.
title: Appiattire
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
exl-id: 63f3e4bc-238f-4e15-8ae5-2f805bd080d3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Appiattire{#flatten}

{{eol}}

La trasformazione Flatten prende un vettore di stringhe e mappa ogni valore nel proprio campo.

| Parametro | Descrizione | Impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| Impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore specificato non è disponibile per la voce di registro. |  |
| Ingresso | Un vettore di valori stringa da associare ai nomi dei campi di output. |  |
| Uscite | Un insieme di nomi di campi di output. |  |

Considerazioni per [!DNL Flatten]

* Se il vettore di input contiene più valori rispetto ai campi di output definiti, i valori di input aggiuntivi vengono semplicemente eliminati.
* Se il vettore di input contiene meno valori rispetto ai campi di output definiti, ai campi di output aggiuntivi viene assegnato il valore predefinito (se definito) o una stringa vuota se non è definito alcun valore predefinito.

Qui, il [!DNL Flatten] La trasformazione viene utilizzata per prendere un vettore di prodotti (x-products) e separarli in quattro campi (x-product1, ..., x-product4).

![](assets/cfg_TransformationType_Flatten.png)

Se il valore di input conteneva le stringhe B57481, C46355 e Z97123, i campi di output avranno i valori indicati di seguito:

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 = Empty (Ci sono più input che output e non è specificato alcun valore predefinito).
