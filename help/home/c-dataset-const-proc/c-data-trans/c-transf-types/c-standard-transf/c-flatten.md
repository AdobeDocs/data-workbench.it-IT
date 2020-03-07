---
description: La trasformazione Appiattito prende un vettore di stringhe e mappa ogni valore nel relativo campo.
solution: Analytics
title: Appiattito
topic: Data workbench
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Appiattito{#flatten}

La trasformazione Appiattito prende un vettore di stringhe e mappa ogni valore nel relativo campo.

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Condizioni in cui viene applicata la trasformazione. |  |
| impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore di input non è disponibile per la voce di registro. |  |
| Ingresso | Un vettore di valori stringa da associare ai nomi dei campi di output. |  |
| Uscite | Un insieme di nomi di campi di output. |  |

Considerazioni [!DNL Flatten]

* Se il vettore di input contiene più valori di quelli definiti per i campi di output, i valori di input aggiuntivi vengono semplicemente ignorati.
* Se il vettore di input contiene meno valori rispetto ai campi di output definiti, ai campi di output aggiuntivi viene assegnato il valore predefinito (se definito) o una stringa vuota se non è definito alcun valore predefinito.

Qui, la [!DNL Flatten] trasformazione viene utilizzata per prendere un vettore di prodotti (x-products) e separarli in quattro campi (x-product1, ..., x-product4).

![](assets/cfg_TransformationType_Flatten.png)

Se il valore di input conteneva le stringhe B57481, C46355 e Z97123, i campi di output avrebbero i valori seguenti:

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 = Vuoto (sono presenti più input che output e non è stato specificato alcun valore predefinito).

