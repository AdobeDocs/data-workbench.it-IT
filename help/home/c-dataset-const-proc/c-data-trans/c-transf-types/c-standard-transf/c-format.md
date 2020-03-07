---
description: La trasformazione Format richiede un set di input e li formatta per creare un output corrispondente alla struttura specificata.
solution: Analytics
title: Formato
topic: Data workbench
uuid: c596902e-21bc-4ce6-9ca4-7ca86dfc0a6c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Formato{#format}

La trasformazione Format richiede un set di input e li formatta per creare un output corrispondente alla struttura specificata.

La trasformazione funziona su stringhe semplici o vettori di stringhe e produce l&#39;output applicando il formato specificato a ciascun valore di input fino alla trasformazione di tutti i valori di input.

<table id="table_3953C993167248AA9A47964A51C4AB5D"> 
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
   <td colname="col1"> Formato </td> 
   <td colname="col2"> <p>Stringa di formattazione utilizzata per specificare l'aspetto dell'output. </p> <p> %1% fa riferimento a un valore del primo vettore di input, %2% fa riferimento a un valore del secondo vettore di input e così via. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingressi </td> 
   <td colname="col2"> <p>Campi contenenti stringhe semplici o vettori di stringhe. Nel caso di vettori di stringa come input, l'output sarà anche un vettore di stringa derivante dall'applicazione del parametro <span class="wintitle"> Format</span> a ciascun set di valori di input. </p> <p> <p>Nota:  La numerazione degli input inizia da 0, ma la numerazione dei valori di sostituzione del formato inizia da %1%. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uscita </td> 
   <td colname="col2"> Nome del campo creato per contenere i risultati della trasformazione. Se gli input sono vettori di stringa, la lunghezza del vettore di output sarà la lunghezza del vettore di input più lungo. Se alcuni vettori della stringa di input hanno una lunghezza inferiore, per la loro posizione nella stringa di formato vengono utilizzate stringhe vuote fino al raggiungimento della lunghezza del vettore di output. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

In questo esempio, due vettori, uno un vettore di stringhe che rappresenta le categorie di prodotti e l&#39;altro un vettore di stringa corrispondente che rappresenta la quantità di ciascun prodotto acquistato, vengono trasformati in un singolo vettore di lunghezza equivalente che assume la forma: Prodotto %1%, Quantità %2%.

![](assets/cfg_TransformationType_Format.png)

Se i vettori di input contenessero categorie di prodotti (683, 918) e quantità di (10, 4), il risultato sarebbe un vettore di output finale contenente le due stringhe seguenti: (&quot;Prodotto 683, Quantità 10&quot;, &quot;Prodotto 918, Quantità 4&quot;).
