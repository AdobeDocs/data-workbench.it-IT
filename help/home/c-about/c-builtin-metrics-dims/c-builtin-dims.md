---
description: Il workbench dati include dimensioni integrate.
solution: Analytics
title: Dimensioni integrate
topic: Data workbench
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensioni integrate{#built-in-dimensions}

Il workbench dati include dimensioni integrate.

Nella tabella seguente sono elencate le dimensioni integrate disponibili per il workbench dati:

<table id="table_40796088B3484F98889859C59D525AD7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome </th> 
   <th colname="col2" class="entry"> Dettagli </th> 
   <th colname="col3" class="entry"> Livello </th> 
   <th colname="col4" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nessuno </td> 
   <td colname="col2"> Derivato </td> 
   <td colname="col3"> N/D </td> 
   <td colname="col4">Ha un singolo elemento "" che si riferisce a tutti gli elementi di tutte le dimensioni. Valutare una metrica su Nessuna è come valutarla su nessuna dimensione. <p>Il <span class="filepath"> filtro [None=""]</span> è equivalente a <span class="filepath"> [True]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uno (nascosto) </td> 
   <td colname="col2"> Numeriche </td> 
   <td colname="col3"> N/D </td> 
   <td colname="col4">L'elemento "1", che ha anche valore ordinale <span class="filepath"> = 1</span>, si riferisce a tutti gli elementi di tutte le dimensioni. La dimensione Uno viene normalmente utilizzata per creare i conteggi utilizzando la sintassi seguente: <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>

