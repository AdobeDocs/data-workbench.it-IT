---
description: La trasformazione REMatch è una trasformazione corrispondente a pattern che utilizza espressioni regolari per specificare uno o più pattern da cercare e acquisire nell’input.
title: REMatch
uuid: 8ef80bfa-aea2-45a1-a7d9-38ad33043886
exl-id: 571e6f1c-f557-49c3-9e7c-c31f06132ec7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 3%

---

# REMatch{#rematch}

La trasformazione REMatch è una trasformazione corrispondente a pattern che utilizza espressioni regolari per specificare uno o più pattern da cercare e acquisire nell’input.

La trasformazione crea un campo di output per ogni sottopattern di acquisizione nell’espressione regolare. Se l’espressione regolare non corrisponde al campo di input, gli output sono vuoti e se il campo di output esiste già, i valori vengono sostituiti dai valori vuoti. Per una breve guida all&#39;utilizzo delle espressioni regolari, consulta [Espressioni regolari](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>La trasformazione [!DNL REMatch] funziona in modo simile alla trasformazione [!DNL RETransform] (vedi [RETransform](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-retransform.md#concept-23f80aa0bc204565b337e5c4931f6a74)), che utilizza espressioni regolari per acquisire una stringa e la memorizza in un singolo campo di output.

[!DNL REMatch] analizza una stringa in modo più efficiente rispetto a più  [!DNL RETransform] trasformazioni o a una singola  [!DNL RETransform] trasformazione seguita da una  [!DNL Flatten] trasformazione. Vedere [Flatten](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-flatten.md#concept-7acd351a6d2444bd960ca412ae3333ce).

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
   <td colname="col2"> Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Distintivo tra maiuscole e minuscole </td> 
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
   <td colname="col2"> Le condizioni in cui viene applicata questa trasformazione. </td> 
   <td colname="col3"></td> 
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
   <td colname="col1"> Uscite </td> 
   <td colname="col2"> <p>Nome della stringa o del vettore di output. Nel caso dei vettori stringa come input, gli output sono anche vettori stringa. </p> <p> Per ogni sottopattern di acquisizione nell’espressione deve esistere un campo di output. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL REMatch] Le trasformazioni possono essere molto lente e possono rappresentare gran parte del tempo di elaborazione dei dati.

In questo esempio, una trasformazione [!DNL REMatch] analizza una data del formato AAAA-MM-GG nei campi x-anno, x-mese e x-giorno. Per la data 2007-01-02, i valori di x-anno, x-mese e x-day saranno rispettivamente 2007, 01 e 02.

![](assets/cfg_TransformationType_REMatch.png)
