---
description: La trasformazione Hash crea una stringa quasi univoca che rappresenta un numero a 64 bit dai valori di input.
title: Hash
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
exl-id: 6912a1d2-9ae8-42ba-94bd-a7a28cbdfae6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 5%

---

# Hash{#hash}

{{eol}}

La trasformazione Hash crea una stringa quasi univoca che rappresenta un numero a 64 bit dai valori di input.

Questa trasformazione fornisce lo stesso valore hash quando vengono forniti gli stessi input.

>[!NOTE]
>
>Il valore risultante è quasi univoco perché la trasformazione utilizza un numero a 64 bit come spazio dei possibili valori hash. Per un milione di ingressi unici [!DNL hash] trasformazione, c&#39;è una probabilità su 38.000.000 di ottenere un valore hash duplicato.

| Parametro | Descrizione | Impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| Impostazione predefinita | Il valore predefinito da utilizzare se il valore specificato non è disponibile. |  |
| Ingressi | Set di input da utilizzare per creare il valore hash. |  |
| Output | Nome del campo per l&#39;output. |  |

In questo esempio, i valori dei campi c-ip e cs(user-agent) vengono utilizzati per creare un ID di tracciamento, memorizzato nel campo x-trackingid .

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>Questo esempio non rappresenta una soluzione ideale per la creazione di ID di tracciamento univoci. Tuttavia, in situazioni in cui vengono utilizzate informazioni di log di archiviazione, potrebbe essere il metodo migliore.
