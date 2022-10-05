---
description: La trasformazione URI Unescape rimuove qualsiasi carattere in una stringa che è stata preceduta da escape.
title: UnescapeURI
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
exl-id: abf20906-5052-4bbe-9ffb-522b850669a6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 6%

---

# UnescapeURI{#unescapeuri}

{{eol}}

La trasformazione URI Unescape rimuove qualsiasi carattere in una stringa che è stata preceduta da escape.

>[!NOTE]
>
>I caratteri escape sostituiscono i caratteri non sicuri in una stringa URI. Sono rappresentati da un triplet costituito da un segno di percentuale seguito da due cifre esadecimali (ad esempio, %20).

| Parametro | Descrizione | Impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| Impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore specificato non è disponibile. |  |
| Ingresso | Stringa URI di cui annullare l’escape. |  |
| Output | Nome del campo in cui deve essere memorizzata la stringa non preceduta da escape. |  |

La seguente trasformazione esegue l’escape del valore docname in un campo di intestazione HTTP e memorizza l’output nel campo x-docname-unescape:

![](assets/cfg_TransformationType_UnescapeURI.png)

Se il valore del docname è

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

allora il valore di x-docname-unescape sarà

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]
