---
description: Il vettore del monitoraggio delle risorse contiene il Monitor del budget della memoria e il Monitor del numero di query.
title: Monitoraggio risorse coda query
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
exl-id: 6d445a4d-a415-41ce-9d45-1bdd0e726edd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 2%

---

# Monitoraggio risorse coda query{#query-queue-resource-monitors}

{{eol}}

Il vettore del monitoraggio delle risorse contiene il Monitor del budget della memoria e il Monitor del numero di query.

Nella tabella seguente sono descritti i campi di monitoraggio delle risorse utilizzati per la coda delle query.

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
   <td colname="col1"> <p>Monitor a budget ridotto </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Controlla la memoria della query utilizzata dal gruppo di utenti corrente. Se l’utilizzo corrente è compreso tra la soglia minima e la soglia massima, non vengono pianificati nuovi bundle fino a quando l’utilizzo della memoria non torna al di sotto del valore della soglia minima, ad esempio a causa della chiusura delle aree di lavoro da parte degli utenti. I grappoli programmati possono crescere. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Soglia alta </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Soglia elevata per l'utilizzo della memoria (byte). Se l’utilizzo della memoria è superiore a questo valore, non si verifica alcuna pianificazione e i bundle con priorità più bassa vengono annullati una alla volta, in un periodo di tempo, fino a quando l’utilizzo della memoria non viene portato al di sotto di questo valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Soglia bassa </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Soglia bassa per l'utilizzo della memoria (byte). Se <span class="wintitle"> Monitor a budget ridotto</span> Il valore è inferiore a questo valore, è consentito pianificare nuovi bundle e consentire l'aumento dei bundle pianificati. Ad esempio, quando un utente aggiunge una visualizzazione a un’area di lavoro i bundle aumentano. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo di reazione </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>La costante di tempo per l'uniformità della stima di utilizzo della memoria. I valori uniformi evitano reazioni ai picchi di utilizzo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Monitor numero di query </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Controlla il numero totale di query attualmente pianificate per il profilo. Questo monitoraggio delle risorse consente di pianificare i bundle se il numero totale di query rimane al di sotto del valore nel campo Soglia bassa . Questo monitoraggio consente l’aumento dei bundle attualmente pianificati se il numero totale di query rimane al di sotto del valore nel campo High Threshold (Soglia elevata). Inoltre, questo monitor rimuove i bundle a bassa priorità per consentire la pianificazione o la crescita dei bundle a priorità più alta. Tuttavia, questa impostazione non previene i bundle con una priorità maggiore di quella specificata nel campo Priorità non toccabile . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Soglia alta </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Soglia elevata per l'utilizzo della memoria (byte). Se l’utilizzo della memoria è superiore a questo valore, non si verifica alcuna pianificazione e i bundle con priorità più bassa vengono annullati una alla volta, in un periodo di tempo, fino a quando l’utilizzo della memoria non viene portato al di sotto di questo valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Soglia bassa </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Soglia bassa per l'utilizzo della memoria (byte). Se <span class="wintitle"> Monitor a budget ridotto</span> Il valore è inferiore a questo valore, è possibile pianificare nuovi bundle e i bundle pianificati possono crescere. </p> </td> 
  </tr> 
 </tbody> 
</table>
