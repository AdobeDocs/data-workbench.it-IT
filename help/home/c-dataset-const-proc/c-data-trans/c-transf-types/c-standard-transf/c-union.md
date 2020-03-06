---
description: La trasformazione Union prende un set di input e crea un vettore di stringhe come output.
solution: Analytics
title: Union
topic: Data workbench
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Union{#union}

La trasformazione Union prende un set di input e crea un vettore di stringhe come output.

Se uno degli input è di per sé un vettore, ogni elemento nel vettore di input è associato a un elemento nel vettore di output (ovvero, la trasformazione non crea un vettore di vettori).

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Condizioni in cui viene applicata la trasformazione. |  |
| impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore immesso non è disponibile. |  |
| Ingressi | Uno o più valori di input. |  |
| Uscita | Nome del campo di output. |  |

In questo esempio vengono utilizzati campi di dati provenienti dal traffico del sito Web per creare un elenco dei codici postali associati ai visitatori del sito Web (ovvero, all’interno di ogni voce di registro). I dati forniscono due possibili origini per queste informazioni: uno in cs-uri-query e l&#39;altro in un [!DNL zipcode] campo del cookie. Se nessuno di questi campi contiene un codice postale, viene utilizzato il valore predefinito 00000.

![](assets/cfg_TransformationType_Union.png)

Anche se è possibile che entrambi questi valori siano disponibili in una singola voce di registro, è possibile selezionare il valore da utilizzare per creare una dimensione basata sull&#39;output della trasformazione. In un caso d’uso tipico, potete creare una dimensione semplice che prende il primo o l’ultimo dei valori rilevati. Per informazioni sulla creazione di dimensioni semplici, consultate Dimensioni [](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)estese.
