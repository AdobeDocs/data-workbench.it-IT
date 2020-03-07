---
description: Il vettore del monitor delle risorse contiene il Monitor budget memoria e il Monitor numero di query.
solution: Analytics
title: Monitoraggio risorse coda query
topic: Data workbench
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Monitoraggio risorse coda query{#query-queue-resource-monitors}

Il vettore del monitor delle risorse contiene il Monitor budget memoria e il Monitor numero di query.

Nella tabella seguente sono descritti i campi del monitoraggio delle risorse utilizzati per la accodamento delle query.

<table id="table_9991EED2647A460FACA2DC80D4973A8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Monitor budget memoria </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Controlla la memoria della query utilizzata dal gruppo di utenti corrente. Se l'utilizzo corrente è compreso tra Soglia bassa e Soglia alta, non vengono pianificati nuovi batch fino a quando l'utilizzo della memoria non torna al di sotto del valore Soglia bassa, ad esempio, a seguito della chiusura delle aree di lavoro da parte degli utenti. I grappoli programmati possono crescere. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Soglia alta </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>La soglia elevata per l'utilizzo della memoria (byte). Se l'utilizzo della memoria è superiore a questo valore, non viene eseguita alcuna pianificazione e i batch con priorità più bassa non vengono pianificati uno alla volta, in un determinato periodo di tempo, finché l'utilizzo della memoria non viene portato al di sotto di questo valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Soglia bassa </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>La soglia minima per l'utilizzo della memoria (byte). Se il valore di <span class="wintitle"> Memory Budget Monitor</span> è inferiore a questo valore, è possibile pianificare nuovi batch e consentire la crescita dei batch pianificati. Ad esempio, i batch aumentano quando un utente aggiunge una visualizzazione a un’area di lavoro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo di reazione </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>La costante temporale per l'uniformità della stima dell'utilizzo della memoria. I valori di arrotondamento evitano la reazione ai picchi di utilizzo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Numero di query, monitor </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Controlla il numero totale di query attualmente pianificate per il profilo. Questo monitoraggio delle risorse consente di pianificare i batch se il numero totale di query rimane al di sotto del valore nel campo Soglia bassa. Questo monitor consente di aumentare i batch attualmente pianificati se il numero totale di query rimane al di sotto del valore nel campo Soglia alta. Inoltre, questo monitor rimuove i grappoli con priorità bassa per consentire la programmazione o l'espansione dei batch con priorità superiore. Tuttavia, questa impostazione non impedisce l'uso di batch con priorità maggiore di quella specificata nel campo Priorità non toccabile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Soglia alta </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>La soglia elevata per l'utilizzo della memoria (byte). Se l'utilizzo della memoria è superiore a questo valore, non viene eseguita alcuna pianificazione e i batch pianificati con priorità più bassa non vengono pianificati uno alla volta, in un determinato periodo di tempo, fino a quando l'utilizzo della memoria non viene portato al di sotto di questo valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Soglia bassa </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>La soglia minima per l'utilizzo della memoria (byte). Se il valore di <span class="wintitle"> Memory Budget Monitor</span> è inferiore a questo valore, è possibile pianificare nuovi batch e aumentare i batch programmati. </p> </td> 
  </tr> 
 </tbody> 
</table>

