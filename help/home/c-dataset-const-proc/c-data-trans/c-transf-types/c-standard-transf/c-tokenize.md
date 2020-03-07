---
description: La trasformazione Tokenize applica iterativamente un'espressione regolare contro la stringa di input.
solution: Analytics
title: Token
topic: Data workbench
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Token{#tokenize}

La trasformazione Tokenize applica iterativamente un&#39;espressione regolare contro la stringa di input.

Tuttavia, a differenza [!DNL RETransform], [!DNL Tokenize] non deve necessariamente corrispondere all&#39;intera stringa: l&#39;espressione regolare utilizzata per la [!DNL Tokenize] trasformazione può corrispondere a un sottoinsieme dell&#39;input. Dopo aver trovato una corrispondenza, [!DNL Tokenize] applica di nuovo l&#39;espressione regolare, a partire dal carattere dopo la fine dell&#39;ultima corrispondenza.

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. |  |
| Distinzione tra maiuscole e minuscole | True o false. Specifica se la corrispondenza fa distinzione tra maiuscole e minuscole. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Condizioni in cui viene applicata la trasformazione. |  |
| impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore di input non è disponibile oppure se l&#39;espressione regolare non corrisponde al valore di input. |  |
| Espressione | L&#39;espressione regolare utilizzata per la corrispondenza. |  |
| Uscite | Nomi delle stringhe di output. È possibile disporre di più output per una determinata stringa di input. Il numero di output deve corrispondere al numero di sottopattern di cattura nell&#39;espressione regolare. |  |

Nell&#39;esempio seguente, la [!DNL Tokenize] trasformazione utilizza un&#39;espressione regolare per acquisire i nomi delle stringhe di query (nella query cs-uri) e restituire il pattern secondario acquisito (il nome della query) a x-pull-query-name.

![](assets/cfg_TransformationType_Tokenize.png)

Per la stringa di query &quot;a=b&amp;c=d&quot;, l’output sarà un vettore contenente &quot;a&quot; e &quot;c&quot;.

Per informazioni sulle espressioni regolari, consultate Espressioni [regolari](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
