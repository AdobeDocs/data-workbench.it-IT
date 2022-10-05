---
description: La trasformazione Tokenize applica iterativamente un'espressione regolare rispetto alla stringa di input.
title: Token
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
exl-id: c1f39b5b-4717-44f6-99c7-4e6a215f3542
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 4%

---

# Token{#tokenize}

{{eol}}

La trasformazione Tokenize applica iterativamente un&#39;espressione regolare rispetto alla stringa di input.

Tuttavia, a differenza di [!DNL RETransform], [!DNL Tokenize] non deve necessariamente corrispondere all&#39;intera stringa: l&#39;espressione regolare utilizzata per [!DNL Tokenize] La trasformazione può corrispondere a un sottoinsieme dell’input. Una volta trovata una corrispondenza, [!DNL Tokenize] applica nuovamente l&#39;espressione regolare, a partire dal carattere dopo la fine dell&#39;ultima corrispondenza.

| Parametro | Descrizione | Impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Distintivo tra maiuscole e minuscole | True o false. Specifica se la corrispondenza fa distinzione tra maiuscole e minuscole. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| Impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore di input non è disponibile oppure se l’espressione regolare non corrisponde al valore di input. |  |
| Espressione | L&#39;espressione regolare utilizzata per la corrispondenza. |  |
| Uscite | Nomi delle stringhe di output. Puoi avere più output per una determinata stringa di input. Il numero di output deve corrispondere al numero di sottopattern di acquisizione nell’espressione regolare. |  |

Nell&#39;esempio seguente, la [!DNL Tokenize] La trasformazione utilizza un&#39;espressione regolare per acquisire i nomi delle stringhe di query (in cs-uri-query) e generare il sottopattern acquisito (il nome della query) in x-pull-query-name.

![](assets/cfg_TransformationType_Tokenize.png)

Per la stringa query &quot;a=b&amp;c=d&quot;, l’output è un vettore contenente &quot;a&quot; e &quot;c&quot;.

Per informazioni sulle espressioni regolari, consulta [Espressioni regolari](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
