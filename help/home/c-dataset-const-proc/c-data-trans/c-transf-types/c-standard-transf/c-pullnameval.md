---
description: La trasformazione PullNameValues è un'operazione speciale che prende i valori nel campo cs-uri-query e separa ciascuna delle coppie nome-valore in una stringa separata.
title: PullNameValues
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
exl-id: 3660ff6e-87dc-42cf-a897-0e2e0e021c07
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 4%

---

# PullNameValues{#pullnamevalues}

La trasformazione PullNameValues è un&#39;operazione speciale che prende i valori nel campo cs-uri-query e separa ciascuna delle coppie nome-valore in una stringa separata.

L’intero insieme di stringhe di coppie nome-valore viene restituito nel campo di output specificato come vettore di stringhe.

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore specificato non è disponibile nella voce di registro specificata. |  |
| Uscita | Nome della stringa di output. |  |

La trasformazione [!DNL PullNameValues] viene utilizzata in questo esempio per acquisire l’utilizzo del modulo di ricerca da parte dei visitatori: quali pulsanti sono stati selezionati, quali valori sono stati digitati nel modulo e così via. L&#39;esempio utilizza una condizione [!DNL String Match] (vedere [Condizioni](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) per isolare l&#39;utilizzo di questa trasformazione solo nella pagina [!DNL /search.php]. Il vettore delle coppie nome-valore viene inviato nel campo x-search-namvalue.

![](assets/cfg_TransformationType_PullNameValues.png)

Utilizzando la trasformazione come sopra definito, se il campo cs-uri-stem corrisponde alla pagina [!DNL /search.php] e cs-uri-query contiene quanto segue:

* Ricerca=Bob&amp;State=Virginia&amp;isMale=true

i valori dei nomi di ricerca x contengono un vettore contenente le tre stringhe seguenti:

* Ricerca=Bob
* Stato=Virginia
* isMale=true
