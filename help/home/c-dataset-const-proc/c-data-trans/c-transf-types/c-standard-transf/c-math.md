---
description: La trasformazione Math consente l'uso di operazioni aritmetiche sui campi all'interno delle voci di registro.
title: Matematica
uuid: 9e1a5950-8fb2-48e9-b9a1-82c5165fba10
exl-id: d8b9cacd-67d1-447c-94dd-7028aa371dfa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 4%

---

# Matematica{#math}

La trasformazione Math consente l&#39;uso di operazioni aritmetiche sui campi all&#39;interno delle voci di registro.

Le operazioni possono includere numeri interi decimali e costanti a virgola mobile.

<table id="table_FDF3DDF1960E43E391A67C9DC2A0E302"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
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
   <td colname="col1"> Espressione </td> 
   <td colname="col2"> <p>Espressione aritmetica che descrive il calcolo da eseguire. </p> <p> È possibile utilizzare una qualsiasi delle operazioni e delle funzioni elencate di seguito e incorporare i nomi dei campi nell'espressione: </p> <p> Operazioni 
     <ul id="ul_DB5915FADA0A41A3B11F1F48615F40A9">
      <li id="li_CA9EA97243F04760A81313C17EE057B3"> Aggiunta (+) </li>
      <li id="li_908A272EBA2340098C20F22AA8D9ED26"> Sottrazione (-) </li>
      <li id="li_C62257FF3AAB436D9148BBEA441621D7"> Moltiplicazione (*) </li>
      <li id="li_B5A9EAB3E49D4CB9A297172199F23542"> Divisione (/) </li>
      <li id="li_D2D2B51DB2C8412A9B6F9D5F3CC03F8A"> Resto (%) </li>
      <li id="li_07E7E368FFD2437A852B785E159848E5"> Esponenziazione (^) </li>
     </ul></p> <p>Funzioni 
     <ul id="ul_E335AE8D684340AA998C4A2633FFDEE1">
      <li id="li_E036FF0B5DF244DDBFEDA9BFEDC62251"> sign(x). Restituisce 1 se x è positivo, 0 se x è zero o -1 se x è negativo. </li>
      <li id="li_90CD8899DDC14778A95930C2768C82BC"> abs(x). Restituisce il valore assoluto di x. </li>
      <li id="li_F4AF23F343F74BD88B7166B1C2BB065E"> pavimento(x). Restituisce il numero intero più grande minore o uguale a x. </li>
      <li id="li_A31379A3659240C3A629BFAF19A6DDF1"> round(x). Restituisce il numero intero più vicino a x. </li>
      <li id="li_9C0A0F3A4A304026B543F2A64B98B922"> log(b,x). Restituisce il logaritmo di x base b. </li>
      <li id="li_124D62C2CA5A42CBBCC5DB18FAA8920E"> min(x,y,..). Restituisce il minore tra tutti gli argomenti. </li>
      <li id="li_3B7B9FC1C0BF4E7688F9F49130B97B7F"> max(x,y,..) Restituisce il più grande di tutti i relativi argomenti. </li>
     </ul></p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uscita </td> 
   <td colname="col2"> Nome del campo contenente il risultato dell’operazione aritmetica. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

In questo esempio, che utilizza i campi di dati raccolti dal traffico del sito web, un nuovo campo denominato x-page-duration viene calcolato sottraendo la marca temporale x-last-pv-dalla marca temporale x-timestamp, quindi aggiungendo 1. L&#39;output viene calcolato solo se il campo x-last-pv-timestamp definito dall&#39;utente (che rappresenta la marca temporale dell&#39;ultima visualizzazione di pagina di un visitatore), è popolato o &quot;non vuoto&quot;.

![](assets/cfg_TransformationType_Math.png)

Per informazioni sulla condizione [!DNL Not Empty], consulta [Condizioni](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).
