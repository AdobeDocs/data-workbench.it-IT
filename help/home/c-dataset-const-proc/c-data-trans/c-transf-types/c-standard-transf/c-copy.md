---
description: La trasformazione Copia copia semplicemente il valore nel campo di input nel campo di output specificato. Se il campo di input può essere un vettore di stringhe, il campo di output deve iniziare con "x-".
title: Copy (Copia)
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
exl-id: 04e97006-1e8e-4123-bbbc-b90a5231170f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 6%

---

# Copy (Copia){#copy}

{{eol}}

La trasformazione Copia copia semplicemente il valore nel campo di input nel campo di output specificato. Se il campo di input può essere un vettore di stringhe, il campo di output deve iniziare con &quot;x-&quot;.

| Parametro | Descrizione | Impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| Impostazione predefinita | Utilizzato se il test della condizione è true e il valore di input non è disponibile nella voce di registro specificata. |  |
| Ingresso | Nome del campo da cui copiare il campo. |  |
| Output | Nome del campo di output. |  |

In questo esempio, che utilizza i campi di dati raccolti dal traffico del sito web, al campo di output x-purchase-success viene assegnato il valore letterale &quot;1&quot; ogni volta che si verificano corrispondenze cs-uri-stem [!DNL /checkout/confirmed.php]. Se la [!DNL Condition] non è soddisfatto (ovvero, cs-uri-stem non corrisponde [!DNL /checkout/confirmed.php]), x-purchase-success non viene modificato.

![](assets/cfg_TransformationType_Copy.png)
