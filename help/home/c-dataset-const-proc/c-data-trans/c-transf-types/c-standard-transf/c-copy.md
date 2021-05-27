---
description: La trasformazione Copia copia semplicemente il valore nel campo di input nel campo di output specificato. Se il campo di input può essere un vettore di stringhe, il campo di output deve iniziare con "x-".
title: Copia
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
exl-id: 04e97006-1e8e-4123-bbbc-b90a5231170f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 5%

---

# Copia{#copy}

La trasformazione Copia copia semplicemente il valore nel campo di input nel campo di output specificato. Se il campo di input può essere un vettore di stringhe, il campo di output deve iniziare con &quot;x-&quot;.

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| impostazione predefinita | Utilizzato se il test della condizione è true e il valore di input non è disponibile nella voce di registro specificata. |  |
| Ingresso | Nome del campo da cui copiare il campo. |  |
| Uscita | Nome del campo di output. |  |

In questo esempio, che utilizza i campi di dati raccolti dal traffico del sito web, al campo di output x-purchase-success viene assegnato il valore letterale &quot;1&quot; ogni volta che cs-uri-stem corrisponde a [!DNL /checkout/confirmed.php]. Se il [!DNL Condition] non è soddisfatto (ovvero, cs-uri-stem non corrisponde a [!DNL /checkout/confirmed.php]), x-purchase-success non viene modificato.

![](assets/cfg_TransformationType_Copy.png)
