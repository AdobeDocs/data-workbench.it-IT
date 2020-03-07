---
description: La trasformazione PullNameValues è un'operazione speciale che prende i valori nel campo cs-uri-query e separa ciascuna delle coppie nome-valore in una stringa separata.
solution: Analytics
title: PullNameValues
topic: Data workbench
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# PullNameValues{#pullnamevalues}

La trasformazione PullNameValues è un&#39;operazione speciale che prende i valori nel campo cs-uri-query e separa ciascuna delle coppie nome-valore in una stringa separata.

L&#39;intera raccolta di stringhe di coppie nome-valore viene restituita nel campo di output specificato come vettore di stringhe.

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Condizioni in cui viene applicata la trasformazione. |  |
| impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore di input non è disponibile nella voce di registro specificata. |  |
| Uscita | Nome della stringa di output. |  |

La [!DNL PullNameValues] trasformazione viene utilizzata in questo esempio per acquisire l&#39;utilizzo da parte dei visitatori del modulo di ricerca: quali pulsanti sono stati selezionati, quali valori sono stati digitati nel modulo e così via. Nell&#39;esempio viene utilizzata una [!DNL String Match] condizione (vedere [Condizioni](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) per isolare l&#39;utilizzo di questa trasformazione solo alla pagina [!DNL /search.php]. Il vettore delle coppie nome-valore viene inviato nei valori x-search-name del campo.

![](assets/cfg_TransformationType_PullNameValues.png)

Utilizzando la trasformazione come definito sopra, se il campo cs-uri-stem corrispondeva alla pagina [!DNL /search.php] e alla query cs-uri conteneva quanto segue:

* Ricerca=Bob&amp;State=Virginia&amp;isMale=true

quindi i valori x-search-name contengono un vettore contenente le tre stringhe seguenti:

* Ricerca=Bob
* Stato=Virginia
* isMale=true

