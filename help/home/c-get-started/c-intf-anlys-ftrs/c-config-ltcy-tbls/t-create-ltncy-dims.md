---
description: Le dimensioni di latenza sono create da una dimensione conteggiata padre, ad esempio Sessions, e una dimensione temporale, ad esempio Day.
title: Creare una dimensione di latenza
uuid: 531d8bf6-a66f-4b02-9d81-05664fb9c988
exl-id: 38b470ef-9409-455b-b2b8-b0391f80b800
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 2%

---

# Creare una dimensione di latenza{#create-a-latency-dimension}

Le dimensioni di latenza sono create da una dimensione conteggiata padre, ad esempio Sessions, e una dimensione temporale, ad esempio Day.

Quando crei una tabella di latenza in Data Workbench, aggiungi automaticamente una dimensione di latenza al file di visualizzazione (.vw). Puoi modificare la dimensione di latenza di una tabella seguendo la procedura seguente.

**Per modificare una dimensione di latenza**

1. Apri la tabella di latenza creata in un editor di testo come Blocco note. Si trova nella cartella User > `working profile name` > Work all&#39;interno della directory di installazione Data Workbench.

   La dimensione di latenza definita include i parametri mostrati nell’esempio seguente. La definizione della dimensione di latenza può includere parametri aggiuntivi. Il valore [!DNL line entity = LatencyDim:] indica l’inizio della definizione della dimensione di latenza.

   ```
   entity = LatencyDim:
   Name = string: dimension name
   Level = ref: wdata/model/dim/level
   Clip = ref: wdata/model/dim/clip
   Time = ref: wdata/model/dim/time dimension
   Format = printf_format: 
   format = string: %+0.0f time string
   offset = double: offset
   Time Before = int: time before
   Time After = int: time after
   ```

1. Modificare i valori per i parametri Nome, Livello, Clip, Ora, Formato, Tempo prima o Tempo dopo utilizzando la tabella seguente come guida:

   <table id="table_13DF30B8B7314F118D0ED5DF9EA70B9B"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Per questo parametro.. </th> 
      <th colname="col2" class="entry"> Fornisci queste informazioni.. </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Nome </p> </td> 
      <td colname="col2"> <p>Facoltativo. Nome della dimensione di latenza visualizzata nel menu di scelta rapida quando fai clic con il pulsante destro del mouse sull’etichetta o sugli elementi della dimensione. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Livello </p> </td> 
      <td colname="col2"> <p>Una dimensione numerabile che è l’elemento padre della dimensione di latenza. Gli esempi includono Sessione, Visitatore e Visualizzazione pagina. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Clip </p> </td> 
      <td colname="col2"> <p>Una dimensione numerabile con una relazione uno-a-molti con il livello della dimensione di latenza. La latenza non viene calcolata oltre i limiti di questa dimensione. Ad esempio, se specifichi un livello di visualizzazione pagina e un clip di sessione, le latenze vengono calcolate per le visualizzazioni di pagina che si sono verificate durante la stessa sessione dell’evento. </p> <p>Per informazioni sulle dimensioni uno-a-molti (semplici), consulta la <i>Guida alla configurazione del set di dati</i>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Tempo </p> </td> 
      <td colname="col2"> <p>Dimensione utilizzata per misurare il tempo trascorso per la dimensione di latenza. Questa dimensione può essere una dimensione temporale, ad esempio Giorno o Ora, o una dimensione numerabile, ad esempio Visitatore, Sessione o Visualizzazione pagina. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Formato </td> 
      <td colname="col2"> <p>Facoltativo. Specifica l’aspetto della visualizzazione della latenza nella Data Workbench. Nel parametro Format è possibile modificare i seguenti valori: 
      <ul id="ul_ABF4C17BDE2E4F6C9CBDD933674DE861"> 
         <li id="li_5ED6A7267C81444983AF8507ADC6A5AB">Stringa di ora. L’unità di tempo visualizzata nella visualizzazione della latenza, ad esempio giorno o settimana. Assicurati di modificare la stringa temporale quando modifichi la dimensione temporale. </li> 
         <li id="li_E3B517ECE1494221AAE90455CC0AAB42">Offset. Un numero intero uguale al negativo del valore Tempo precedente. Ad esempio, se Tempo precedente è 7, l'offset deve essere -7. </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Tempo precedente </p> </td> 
      <td colname="col2"> <p>La quantità massima di tempo (espressa in unità della dimensione Tempo) prima dell’evento per il quale viene calcolata la latenza. Se questo valore è impostato su 0 o non è impostato affatto, la latenza viene calcolata solo per la direzione in avanti. </p> <p>Se modificate questo valore, accertatevi di modificare il valore di offset nel parametro Format: L'offset è il negativo del valore Tempo prima. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Tempo dopo </p> </td> 
      <td colname="col2"> <p>La quantità massima di tempo (espressa in unità della dimensione Tempo) dopo l’evento per il quale viene calcolata la latenza. </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Salvare il file [!DNL .vw] nella cartella User\*working profile name*\Work .

   Di seguito sono riportate le impostazioni per la dimensione di latenza predefinita:

   ```
   entity = LatencyDim:
   Name = string: 
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Day
   Time Before = int: 7
   Time After = int: 7
   ```

   Nella dimensione di latenza seguente, la latenza di ogni evento di sessione viene calcolata in ore e Tempo prima è impostata su zero. Pertanto, la latenza viene calcolata solo per le sessioni che si sono verificate entro 24 ore dall’evento definito.

   ```
   entity = LatencyDim:
   Name = string:
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Hour
   Time Before = int: 0
   Time After = int: 24
   ```
