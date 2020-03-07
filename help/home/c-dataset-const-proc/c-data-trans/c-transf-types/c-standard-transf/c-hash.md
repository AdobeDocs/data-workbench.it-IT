---
description: La trasformazione Hash crea una stringa quasi univoca che rappresenta un numero a 64 bit dai valori di input.
solution: Analytics
title: Hash
topic: Data workbench
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hash{#hash}

La trasformazione Hash crea una stringa quasi univoca che rappresenta un numero a 64 bit dai valori di input.

Questa trasformazione fornisce lo stesso valore hash se gli stessi input vengono forniti.

>[!NOTE]
>
>Il valore risultante è quasi univoco perché la trasformazione utilizza un numero a 64 bit come spazio dei possibili valori hash. Per un milione di input unici alla [!DNL hash] trasformazione, esiste una probabilità di 1 su 38.000.000 di ottenere un valore hash duplicato.

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Condizioni in cui viene applicata la trasformazione. |  |
| impostazione predefinita | Il valore predefinito da utilizzare se il valore immesso non è disponibile. |  |
| Ingressi | Set di input da utilizzare per creare il valore hash. |  |
| Uscita | Nome del campo per l&#39;output. |  |

In questo esempio, i valori dei campi c-ip e cs(user-agent) vengono utilizzati per creare un ID di tracciamento, memorizzato nel campo x-trackingid.

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>Questo esempio non rappresenta una soluzione ideale per la creazione di ID di tracciamento univoci. Tuttavia, nelle situazioni in cui vengono utilizzate le informazioni del registro di archiviazione, potrebbe essere il metodo migliore.

