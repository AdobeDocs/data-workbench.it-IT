---
description: Se lavori con dati web, puoi utilizzare la trasformazione ExtractValue per estrarre un valore da una stringa di query, un cookie o un campo codificato in modo simile nei dati del tuo sito web.
title: ExtractValue
uuid: 305827a2-04e6-421f-82cb-923d62b02e70
exl-id: 5bafe64f-081a-49ec-997e-68e8f6915a71
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# ExtractValue{#extractvalue}

Se lavori con dati web, puoi utilizzare la trasformazione ExtractValue per estrarre un valore da una stringa di query, un cookie o un campo codificato in modo simile nei dati del tuo sito web.

In ogni voce di registro, i nomi corrispondenti al valore da estrarre possono essere diversi.

<table id="table_D16A39BE035043628A4D6F7452952304"> 
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
   <td colname="col1"> Nome ingresso </td> 
   <td colname="col2"> <p>Nome o nomi dei campi da estrarre dalla query di input. </p> <p> <p>Nota:  Se il Nome input è un vettore (ovvero sono presenti più nomi), viene estratto un solo valore. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Query di input </td> 
   <td colname="col2"> La mappatura codificata (stringa di query, cookie e così via) da cui deve essere estratto il valore. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valore output </td> 
   <td colname="col2"> Nome del campo utilizzato per acquisire il valore decodificato estratto. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

Se si desidera estrarre una frase di ricerca, è possibile estrarre l&#39;intera frase e, se lo si desidera, suddividerla in termini di ricerca utilizzando una trasformazione [!DNL Tokenize]. Per informazioni sulla trasformazione [!DNL Tokenize], consulta [Token](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-tokenize.md#concept-f460aa5df3a7476e971af29cf5d9b32c).

Questo esempio configura una trasformazione [!DNL ExtractValue] per estrarre i valori del campo x-v-search-querynames da cs(referrer-query) e memorizzarli nel campo x-search-phrase.

![](assets/cfg_TransformationType_ExtractValue.png)
