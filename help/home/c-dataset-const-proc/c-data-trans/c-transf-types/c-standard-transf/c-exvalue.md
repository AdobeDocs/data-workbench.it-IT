---
description: Se si lavora con dati Web, è possibile utilizzare la trasformazione ExtractValue per estrarre un valore da una stringa di query, un cookie o un campo con codifica simile nei dati del sito Web.
solution: Analytics
title: ExtractValue
topic: Data workbench
uuid: 305827a2-04e6-421f-82cb-923d62b02e70
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ExtractValue{#extractvalue}

Se si lavora con dati Web, è possibile utilizzare la trasformazione ExtractValue per estrarre un valore da una stringa di query, un cookie o un campo con codifica simile nei dati del sito Web.

I nomi corrispondenti al valore da estrarre possono essere diversi in ciascuna voce di registro.

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
   <td colname="col1"> Nome input </td> 
   <td colname="col2"> <p>I nomi dei campi da estrarre dalla query di input. </p> <p> <p>Nota:  Se il nome di input è un vettore (ovvero se sono presenti più nomi), viene estratto un solo valore. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Query di input </td> 
   <td colname="col2"> Mappatura codificata (stringa di query, cookie e così via) da cui estrarre il valore. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valore di output </td> 
   <td colname="col2"> Nome del campo utilizzato per acquisire il valore decodificato estratto. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

Se si desidera estrarre una frase di ricerca, è possibile estrarre l&#39;intera frase e, se lo si desidera, dividere la frase in termini di ricerca utilizzando una [!DNL Tokenize] trasformazione. Per informazioni sulla [!DNL Tokenize] trasformazione, vedere [Token](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-tokenize.md#concept-f460aa5df3a7476e971af29cf5d9b32c).

Questo esempio configura una [!DNL ExtractValue] trasformazione per estrarre i valori del campo x-v-search-querynames da cs(referrer-query) e memorizzarli nel campo x-search-phrase.

![](assets/cfg_TransformationType_ExtractValue.png)

