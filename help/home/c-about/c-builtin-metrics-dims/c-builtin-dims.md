---
description: Data Workbench include dimensioni incorporate.
title: Dimensioni incorporate
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
exl-id: c08a487d-60b8-4db7-8776-7ae1b9f1f27c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 13%

---

# Dimensioni incorporate{#built-in-dimensions}

Data Workbench include dimensioni incorporate.

Nella tabella seguente sono elencate le dimensioni integrate disponibili per Data Workbench:

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
   <td colname="col1"> None </td> 
   <td colname="col2"> Derivato </td> 
   <td colname="col3"> N/D </td> 
   <td colname="col4">Ha un singolo elemento "" che si riferisce a tutti gli elementi di tutte le dimensioni. Valutare una metrica su Nessuna è come valutarla su nessuna dimensione. <p>Il <span class="filepath"> Filtro [None=""]</span> equivale a <span class="filepath"> [True]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uno (nascosto) </td> 
   <td colname="col2"> Numeriche </td> 
   <td colname="col3"> N/D </td> 
   <td colname="col4">L'elemento "1", che ha anche valore ordinale <span class="filepath"> = 1</span>, si riferisce a tutti gli elementi di tutte le dimensioni. La dimensione Una viene normalmente utilizzata per costruire i conteggi utilizzando questa sintassi: <p><span class="filepath"> sum(uno,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>
