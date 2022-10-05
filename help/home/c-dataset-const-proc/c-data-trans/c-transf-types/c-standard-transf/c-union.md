---
description: La trasformazione Union prende un insieme di input e crea un vettore di stringhe come output.
title: Unione
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
exl-id: 841b5133-d587-409c-b39e-47169beb2ddf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# Unione{#union}

{{eol}}

La trasformazione Union prende un insieme di input e crea un vettore di stringhe come output.

Se uno degli input è di per sé un vettore, ogni elemento nel vettore di input è associato a un elemento nel vettore di output (cioè, la trasformazione non crea un vettore di vettori).

| Parametro | Descrizione | Impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| Impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore specificato non è disponibile. |  |
| Ingressi | Uno o più valori di input. |  |
| Output | Nome del campo di output. |  |

Questo esempio utilizza i campi di dati del traffico del sito web per creare un elenco dei codici postali associati ai visitatori del sito web (ovvero all’interno di ogni voce di registro). I dati forniscono due possibili fonti per queste informazioni: uno in cs-uri-query e l&#39;altro in un [!DNL zipcode] campo del cookie. Se nessuno di questi campi contiene un codice postale, viene utilizzato il valore predefinito 0000.

![](assets/cfg_TransformationType_Union.png)

Anche se è possibile che entrambi questi valori siano disponibili in una singola voce di registro, è possibile selezionare il valore da utilizzare quando si crea una dimensione in base all’output della trasformazione. In un caso d’uso tipico, puoi creare una dimensione semplice che prende il primo o l’ultimo dei valori rilevati. Per informazioni sulla creazione di dimensioni semplici, consulta [Dimension estesi](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).
