---
description: La trasformazione URI Unescape consente di rimuovere tutti i caratteri di una stringa con escape.
solution: Analytics
title: UnescapeURI
topic: Data workbench
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# UnescapeURI{#unescapeuri}

La trasformazione URI Unescape consente di rimuovere tutti i caratteri di una stringa con escape.

>[!NOTE]
>
>I caratteri di escape sostituiscono i caratteri non sicuri in una stringa URI. Sono rappresentati da un triplo costituito da un segno di percentuale seguito da due cifre esadecimali (ad esempio, %20).

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Condizioni in cui viene applicata la trasformazione. |  |
| impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore immesso non è disponibile. |  |
| Ingresso | Stringa URI da non utilizzare come carattere di escape. |  |
| Uscita | Nome del campo in cui deve essere memorizzata la stringa non preceduta da escape. |  |

La seguente trasformazione elimina il valore docname in un campo di intestazione HTTP e memorizza l’output nel campo x-docname-unescape:

![](assets/cfg_TransformationType_UnescapeURI.png)

Se il valore docname è

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

quindi il valore di x-docname-unescape sarà

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]

