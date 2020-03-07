---
description: La trasformazione RETransform (espressione regolare) è una trasformazione di corrispondenza del pattern che utilizza espressioni regolari per specificare un pattern da cercare e acquisire nell'input e memorizza la stringa acquisita in un campo di output designato.
solution: Analytics
title: RETransform
topic: Data workbench
uuid: 60b5b60e-678a-416d-b5c3-57b1bbefce7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# RETransform{#retransform}

La trasformazione RETransform (espressione regolare) è una trasformazione di corrispondenza del pattern che utilizza espressioni regolari per specificare un pattern da cercare e acquisire nell&#39;input e memorizza la stringa acquisita in un campo di output designato.

Le espressioni regolari vengono valutate rispetto all&#39;intera stringa di input. Se l&#39;input non corrisponde al pattern specificato nell&#39;espressione regolare, non vengono acquisiti dati. Per una breve guida all&#39;uso delle espressioni regolari, consultate Espressioni [regolari](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>La [!DNL RETransform] trasformazione opera in modo simile alla [!DNL REMatch] trasformazione (vedere [REMatch](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-rematch.md#concept-7f0b1caad1df46aabef4448f88261a8e)), che crea un campo di output per ogni sottopattern di cattura nell&#39;espressione regolare. Si può pensare [!DNL RETransform] a una combinazione di [!DNL REMatch] e [!DNL Format] trasformazioni. Se il parametro Action (vedere Azione nella tabella seguente) è impostato su &quot;RESULTS&quot;, [!DNL RETransform] funziona come una combinazione di [!DNL REMatch] e [!DNL Union] trasformazioni.

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
   <td colname="col2"> Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commenti </td> 
   <td colname="col2"> Facoltativo. Note sulla trasformazione. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione </td> 
   <td colname="col2"> Condizioni in cui viene applicata la trasformazione. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> impostazione predefinita </td> 
   <td colname="col2"> Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore di input non è disponibile oppure se l'espressione regolare non corrisponde al valore di input. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Azione </td> 
   <td colname="col2"> <p>Specifica come viene gestito il risultato. L'impostazione predefinita di RESULTS prende semplicemente i pattern associati e crea un vettore di stringhe dai pattern estratti. </p> <p> In alternativa, l'azione può essere una stringa di formattazione per creare un output di stringa semplice con un particolare formato. Con questa tecnica, si specifica il numero corrispondente alla posizione di ogni pattern corrispondente tra i segni %. Ad esempio, il primo pattern di corrispondenza sarebbe %1% e il terzo pattern di corrispondenza sarebbe %3%. È possibile specificare letteralmente altri caratteri nella stringa di formattazione. </p> </td> 
   <td colname="col3"> RISULTATI </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Espressione </td> 
   <td colname="col2"> L'espressione regolare utilizzata per la corrispondenza. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresso </td> 
   <td colname="col2"> Campo rispetto al quale viene valutata l'espressione regolare. </td> 
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

In questo esempio viene isolata la versione del sistema operativo Windows utilizzata da un visitatore del sito Web e da tale valore viene creata una versione x-windows del campo. In questo caso, il valore di output corrisponde semplicemente al numero di versione.

![](assets/cfg_TransformationType_RegularExpression.png)

Se si desidera includere la stringa &quot;Versione&quot; davanti al numero di versione per la leggibilità, è necessario modificare il parametro Action da &quot;RESULTS&quot; a &quot;Versione %1%&quot;. Per includere un segno percentuale letterale (%) nell&#39;output, esegui l&#39;escape con un secondo segno di percentuale, come in &quot;%%&quot;.
