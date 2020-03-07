---
description: La trasformazione Math consente l'uso di operazioni aritmetiche sui campi all'interno delle voci di registro.
solution: Analytics
title: Matematica
topic: Data workbench
uuid: 9e1a5950-8fb2-48e9-b9a1-82c5165fba10
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

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
   <td colname="col1"> Espressione </td> 
   <td colname="col2"> <p>Un'espressione aritmetica che descrive il calcolo da eseguire. </p> <p> È possibile utilizzare una qualsiasi delle operazioni e delle funzioni elencate di seguito, nonché includere i nomi dei campi nell'espressione: </p> <p> Operazioni 
     <ul id="ul_DB5915FADA0A41A3B11F1F48615F40A9">
      <li id="li_CA9EA97243F04760A81313C17EE057B3"> Aggiunta (+) </li>
      <li id="li_908A272EBA2340098C20F22AA8D9ED26"> Sottrazione (-) </li>
      <li id="li_C62257FF3AAB436D9148BBEA441621D7"> Moltiplicazione (*) </li>
      <li id="li_B5A9EAB3E49D4CB9A297172199F23542"> Divisione (/) </li>
      <li id="li_D2D2B51DB2C8412A9B6F9D5F3CC03F8A"> Resto (%) </li>
      <li id="li_07E7E368FFD2437A852B785E159848E5"> Esponenza (^) </li>
     </ul></p> <p>Funzioni 
     <ul id="ul_E335AE8D684340AA998C4A2633FFDEE1">
      <li id="li_E036FF0B5DF244DDBFEDA9BFEDC62251"> ssign(x). Restituisce 1 se x è positivo, 0 se x è zero, o -1 se x è negativo. </li>
      <li id="li_90CD8899DDC14778A95930C2768C82BC"> abs(x). Restituisce il valore assoluto di x. </li>
      <li id="li_F4AF23F343F74BD88B7166B1C2BB065E"> floor(x). Restituisce il numero intero maggiore minore o uguale a x. </li>
      <li id="li_A31379A3659240C3A629BFAF19A6DDF1"> round(x). Restituisce il numero intero più vicino a x. </li>
      <li id="li_9C0A0F3A4A304026B543F2A64B98B922"> log(b,x). Restituisce il logaritmo di x base b. </li>
      <li id="li_124D62C2CA5A42CBBCC5DB18FAA8920E"> min(x,y,...) Restituisce il più piccolo di tutti gli argomenti. </li>
      <li id="li_3B7B9FC1C0BF4E7688F9F49130B97B7F"> max(x,y,...) Restituisce il maggiore di tutti gli argomenti. </li>
     </ul></p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uscita </td> 
   <td colname="col2"> Nome del campo contenente il risultato dell'operazione aritmetica. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

In questo esempio, che utilizza i campi di dati raccolti dal traffico del sito Web, un nuovo campo denominato x-page-Duration viene calcolato sottraendo x-last-pv-timestamp da x-timestamp, quindi aggiungendo 1. L&#39;output è calcolato solo se il campo x-last-pv-timestamp definito dall&#39;utente (che rappresenta la marca temporale dell&#39;ultima visualizzazione pagina del visitatore), è popolato o &quot;non vuoto&quot;.

![](assets/cfg_TransformationType_Math.png)

Per informazioni sulla [!DNL Not Empty] condizione, vedere [Condizioni](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).