---
description: Gli elementi di una dimensione numerabile possono essere conteggiati dal sistema.
title: Dimensioni conteggiate
uuid: 3312f5eb-69b9-43af-b32a-5c40e3050b29
exl-id: c607c15d-de85-4daf-af76-79b460f51b38
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 2%

---

# Dimensioni conteggiate{#countable-dimensions}

Gli elementi di una dimensione numerabile possono essere conteggiati dal sistema.

Le dimensioni conteggiate vengono generalmente utilizzate per creare metriche di somma che restituiscono il conteggio o la somma di tutti gli elementi della dimensione. È possibile definire dimensioni numerabili per conteggiare le istanze, ad esempio prenotazioni o ordini di prodotti. Ad esempio, puoi definire la dimensione numerabile Ordini i cui elementi (voci di registro corrispondenti agli ordini del tuo negozio online) possono essere conteggiati. Per visualizzare un conteggio degli ordini all’interno di una visualizzazione, definisci la metrica di somma Ordini che può essere valutata su una dimensione o a cui sono applicati filtri.

Le dimensioni conteggiate possono essere genitori di altre dimensioni o figli di altre dimensioni conteggiate.

>[!NOTE]
>
>Se hai bisogno di una dimensione che fornisca solo un conteggio di qualcosa, devi utilizzare una dimensione numerica con un’operazione COUNT. Vedere [Dimension numerici](../../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed).

Le dimensioni conteggiate sono definite dai seguenti parametri:

<table id="table_9F3F093F5B074EA68CA4DCE731161F6C"> 
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
   <td colname="col2"> Nome descrittivo della dimensione visualizzato all’utente all’interno di Data Workbench. Il nome della dimensione non può includere un trattino (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commenti </td> 
   <td colname="col2"> Facoltativo. Note sulla dimensione estesa. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione </td> 
   <td colname="col2"> Le condizioni alle quali il campo di immissione contribuisce alla creazione della dimensione numerabile. Se specificata, una condizione limita il set di voci di registro visibili alla dimensione e a tutti i relativi elementi secondari nello schema del set di dati. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nascosto </td> 
   <td colname="col2"> Determina se la dimensione viene visualizzata nell’interfaccia di Data Workbench. Per impostazione predefinita, questo parametro è impostato su false. Se, ad esempio, la dimensione deve essere utilizzata solo come base di una metrica, puoi impostare questo parametro su true per nascondere la dimensione dalla visualizzazione di Data Workbench. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chiave </td> 
   <td colname="col2"> <p>Facoltativo. Nome del campo da utilizzare come chiave. Se definisci questo parametro, esiste un elemento della dimensione numerabile per ogni combinazione di un elemento dell'elemento padre della dimensione numerabile e un valore distinto del campo specificato come chiave. </p> <p> Ogni elemento della dimensione numerabile è necessario per riferirsi a un insieme contiguo di voci di registro. Pertanto, se le voci di registro non sono ordinate dalla chiave, viene creato un elemento della dimensione numerabile ogni volta che il campo chiave cambia. Per evitare questa situazione, l’Adobe consiglia di utilizzare una chiave univoca contigua in ordine temporale. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elemento padre </td> 
   <td colname="col2"> <p>Nome della dimensione padre. Qualsiasi dimensione conteggiata può essere una dimensione superiore. Per fare di una dimensione la dimensione di primo livello nello schema del set di dati, imposta il parametro su "root". La dimensione definita diventa la dimensione contabile principale del set di dati. Ad esempio, se lavori con il sito, la dimensione Visitatore è la dimensione conteggiata principale del set di dati. </p> <p> <p>Nota:  Anche se la dimensione conteggiata principale non deve essere associata agli ID di tracciamento nei dati, Adobe consiglia di configurare la dimensione conteggiata principale del set di dati per utilizzare il campo ID di tracciamento (x-trackingid) come chiave. Di conseguenza, ogni elemento della tabella contabile principale è associato a un valore univoco di x-trackingid e tutti i dati relativi a ciascun elemento sono raggruppati insieme. Se desideri configurare il set di dati in modo diverso, contatta l’Adobe . </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Questo esempio illustra la definizione di una dimensione numerabile utilizzando i dati evento raccolti dal traffico del sito web. La dimensione numerabile conta gli eventi della campagna web all’interno di una determinata sessione. Il presupposto è che tutte le risorse della campagna e-mail siano richieste dal server web con &quot;email=&quot; come parte di cs-uri-query. Nell’esempio, il numero di volte in cui il visitatore risponde a una campagna e-mail durante una determinata sessione è di interesse e non il valore effettivo del campo cs-uri-query(email) .

![](assets/cfg_Transformation_Dim_Countable.png)

Questo esempio illustra anche la definizione di una dimensione numerabile utilizzando i dati evento raccolti dal traffico del sito web, ma dispone di un parametro Key definito. La dimensione numerabile della sessione utilizza il campo chiave x come chiave. (Il campo x-session-key è l’output della trasformazione [!DNL Sessionize] e ha un valore univoco per ogni sessione.) Ogni combinazione unica di un elemento della dimensione Visitatore (l’elemento padre) e del campo chiave x-session è un elemento della dimensione Sessione.

![](assets/cfg_Transformation_Dim_Countable2.png)
