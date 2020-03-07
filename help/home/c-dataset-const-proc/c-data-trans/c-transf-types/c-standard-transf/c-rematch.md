---
description: La trasformazione REMatch è una trasformazione di corrispondenza del pattern che utilizza espressioni regolari per specificare uno o più pattern da cercare e acquisire nell'input.
solution: Analytics
title: REMatch
topic: Data workbench
uuid: 8ef80bfa-aea2-45a1-a7d9-38ad33043886
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# REMatch{#rematch}

La trasformazione REMatch è una trasformazione di corrispondenza del pattern che utilizza espressioni regolari per specificare uno o più pattern da cercare e acquisire nell&#39;input.

La trasformazione crea un campo di output per ciascun sottopattern di cattura nell&#39;espressione regolare. Se l&#39;espressione regolare non corrisponde al campo di input, gli output sono vuoti e se il campo di output esiste già, i valori vengono sostituiti dai valori vuoti. Per una breve guida all&#39;uso delle espressioni regolari, consultate Espressioni [regolari](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>La [!DNL REMatch] trasformazione opera in modo simile alla [!DNL RETransform] trasformazione (vedere [RETransform](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-retransform.md#concept-23f80aa0bc204565b337e5c4931f6a74)), che utilizza espressioni regolari per acquisire una stringa e la memorizza in un singolo campo di output.

[!DNL REMatch] analizza una stringa in modo più efficiente rispetto a più [!DNL RETransform] trasformazioni o a una singola [!DNL RETransform] trasformazione seguita da una [!DNL Flatten] trasformazione. Consultate [Appiattito](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-flatten.md#concept-7acd351a6d2444bd960ca412ae3333ce).

<table id="table_7077578512B249E986BC79AE770CBD9A"> 
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
   <td colname="col1"> Distinzione tra maiuscole e minuscole </td> 
   <td colname="col2"> True o false. Specifica se la corrispondenza fa distinzione tra maiuscole e minuscole. </td> 
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
   <td colname="col1"> Uscite </td> 
   <td colname="col2"> <p>Il nome della stringa o del vettore di output. Nel caso dei vettori stringa come input, gli output sono anche vettori stringa. </p> <p> È necessario che esista un campo di output per ciascun pattern secondario di cattura nell'espressione. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL REMatch] Le trasformazioni possono essere molto lente e possono rappresentare gran parte del tempo di elaborazione dei dati.

In questo esempio, una [!DNL REMatch] trasformazione analizza la data del formato AAAA-MM-GG nei campi x-anno, x-mese e x-giorno. Per la data 2007-01-02, i valori di x-year, x-month e x-day saranno rispettivamente 2007, 01 e 02.

![](assets/cfg_TransformationType_REMatch.png)

