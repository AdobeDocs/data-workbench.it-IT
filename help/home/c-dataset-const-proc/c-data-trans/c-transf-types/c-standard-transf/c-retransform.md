---
description: La trasformazione RETransform (espressione regolare) è una trasformazione corrispondente a pattern che utilizza espressioni regolari per specificare un pattern da cercare e acquisire nell’input e memorizza la stringa acquisita in un campo di output designato.
title: RETransform
uuid: 60b5b60e-678a-416d-b5c3-57b1bbefce7d
exl-id: 2595f782-0efb-4a2a-84bd-fdb04baf0852
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 2%

---

# RETransform{#retransform}

La trasformazione RETransform (espressione regolare) è una trasformazione corrispondente a pattern che utilizza espressioni regolari per specificare un pattern da cercare e acquisire nell’input e memorizza la stringa acquisita in un campo di output designato.

Le espressioni regolari vengono valutate rispetto all&#39;intera stringa di input. Se l’input non corrisponde al pattern specificato nell’espressione regolare, non vengono acquisiti dati. Per una breve guida all&#39;utilizzo delle espressioni regolari, consulta [Espressioni regolari](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>La trasformazione [!DNL RETransform] opera in modo simile alla trasformazione [!DNL REMatch] (vedere [REMatch](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-rematch.md#concept-7f0b1caad1df46aabef4448f88261a8e)), che crea un campo di output per ogni sottopattern di acquisizione nell’espressione regolare. È possibile considerare [!DNL RETransform] come una combinazione di [!DNL REMatch] e [!DNL Format] trasformazioni. Se il parametro Azione (vedi Azione nella tabella seguente) è impostato su &quot;RESULTS&quot;, allora [!DNL RETransform] funziona come una combinazione di trasformazioni [!DNL REMatch] e [!DNL Union].

<table id="table_51B7342E6A5E4E31913BD0F6A6ACC424"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> impostazione predefinita </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commenti </td> 
   <td colname="col2"> Facoltativo. Note sulla trasformazione. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione </td> 
   <td colname="col2"> Le condizioni in cui viene applicata questa trasformazione. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> impostazione predefinita </td> 
   <td colname="col2"> Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore di input non è disponibile oppure se l’espressione regolare non corrisponde al valore di input. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Azione </td> 
   <td colname="col2"> <p>Specifica come viene trattato il risultato. L'impostazione predefinita di RESULTS prende semplicemente i pattern corrispondenti e crea un vettore di stringhe dai pattern estratti. </p> <p> In alternativa, l'azione può essere una stringa di formattazione per creare un output stringa semplice di un formato specifico. Con questa tecnica si specifica il numero corrispondente alla posizione di ogni pattern corrispondente tra i segni %. Ad esempio, il primo pattern corrispondente sarebbe %1% e il terzo pattern corrispondente sarebbe %3%. Nella stringa di formattazione verranno letteralmente specificati altri caratteri. </p> </td> 
   <td colname="col3"> RISULTATI </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Espressione </td> 
   <td colname="col2"> L'espressione regolare utilizzata per la corrispondenza. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresso </td> 
   <td colname="col2"> Campo in base al quale viene valutata l'espressione regolare. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uscita </td> 
   <td colname="col2"> Nome della stringa di output. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL RETransform] Le trasformazioni possono essere molto lente e possono rappresentare gran parte del tempo di elaborazione dei dati.

In questo esempio viene isolata la versione del sistema operativo Windows in uso da un visitatore del sito Web e viene creato un campo x-windows-version da tale valore. Il valore di output in questo caso è semplicemente il numero di versione.

![](assets/cfg_TransformationType_RegularExpression.png)

Se si desidera includere la stringa &quot;Versione&quot; davanti al numero di versione per la leggibilità, è necessario modificare il parametro Azione da &quot;RESULTS&quot; a &quot;Versione %1%&quot;. Per includere un segno di percentuale letterale (%) nell’output, eseguine il escape con un segno di seconda percentuale, come in &quot;%%&quot;.
