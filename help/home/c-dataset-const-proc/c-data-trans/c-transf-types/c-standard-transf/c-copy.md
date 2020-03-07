---
description: La trasformazione Copia semplicemente copia il valore nel campo di input nel campo di output specificato. Se il campo di input può essere un vettore di stringhe, il campo di output deve iniziare con "x-".
solution: Analytics
title: Copia
topic: Data workbench
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Copia{#copy}

La trasformazione Copia semplicemente copia il valore nel campo di input nel campo di output specificato. Se il campo di input può essere un vettore di stringhe, il campo di output deve iniziare con &quot;x-&quot;.

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Condizioni in cui viene applicata la trasformazione. |  |
| impostazione predefinita | Utilizzato se il test di condizione è true e il valore di input non è disponibile nella voce di registro specificata. |  |
| Ingresso | Nome del campo da cui copiare il testo. |  |
| Uscita | Nome del campo di output. |  |

In questo esempio, che utilizza i campi di dati raccolti dal traffico del sito Web, al campo di output, x-purchase-success, viene assegnato il valore letterale &quot;1&quot; ogni volta che si verificano delle corrispondenze [!DNL /checkout/confirmed.php]con il sistema cs-uri-stem. Se il [!DNL Condition] risultato non è soddisfatto (ovvero, cs-uri-stem non corrisponde [!DNL /checkout/confirmed.php]), x-purchase-success non viene modificato.

![](assets/cfg_TransformationType_Copy.png)

