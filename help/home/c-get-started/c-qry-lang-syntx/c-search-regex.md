---
description: Data Workbench utilizza espressioni regolari (regex) per le operazioni di ricerca e ordinamento.
solution: Analytics
title: Espressioni regolari
topic: Data workbench
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Espressioni regolari{#regular-expressions}

Data Workbench utilizza espressioni regolari (regex) per le operazioni di ricerca e ordinamento.

All&#39;interno del **[!UICONTROL Search]** campo è possibile eseguire una ricerca dopo l&#39;istruzione &quot;re:&quot; utilizzando espressioni comuni, ad esempio:

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> metacarattero </th> 
   <th colname="col2" class="entry"> description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>. (punto) </p> </td> 
   <td colname="col2"> <p>Corrisponde a un singolo carattere, ad esempio: <span class="filepath"> re:x.z </span> corrisponde a "xyz" o "xxz". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>* (stella) </p> </td> 
   <td colname="col2"> <p>Corrisponde a uno o più caratteri, ad esempio: <span class="filepath"> re:Z* </span> corrisponde a "ZZZ". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? (carattere jolly) </p> </td> 
   <td colname="col2"> <p>Corrisponde a 0 o 1 dell'espressione precedente per imporre una corrispondenza minima, ad esempio: <span class="filepath"> xy?z </span> corrisponde a "xy" e "xyz". </p> </td> 
  </tr> 
 </tbody> 
</table>

È inoltre possibile utilizzare espressioni regolari comuni aggiuntive per creare stringhe di ricerca più complesse. Sono utilizzate espressioni regolari in tutti i campi di ricerca di Workbench dati, compresi i pannelli delle entità query.

Consultate le informazioni dettagliate sulle espressioni [](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions)regolari.
