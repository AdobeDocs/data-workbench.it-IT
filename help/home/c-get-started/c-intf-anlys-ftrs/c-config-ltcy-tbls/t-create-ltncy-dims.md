---
description: Le dimensioni della latenza sono costituite da una dimensione contabile padre, come Sessioni, e da una dimensione temporale, come Giorno.
solution: Analytics
title: Creare una dimensione di latenza
topic: Data workbench
uuid: 531d8bf6-a66f-4b02-9d81-05664fb9c988
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creare una dimensione di latenza{#create-a-latency-dimension}

Le dimensioni della latenza sono costituite da una dimensione contabile padre, come Sessioni, e da una dimensione temporale, come Giorno.

Quando si crea una tabella di latenza in Workbench dati, si aggiunge automaticamente una dimensione di latenza al file di visualizzazione (.vw). Per modificare la dimensione della latenza di una tabella, procedere come segue.

**Per modificare una dimensione di latenza**

1. Aprite la tabella di latenza creata in un editor di testo come Blocco note. Si trova nella cartella Utente > `working profile name` > Lavoro all&#39;interno della directory di installazione di Workbench dati.

   La dimensione di latenza definita include i parametri mostrati nell&#39;esempio seguente. (la definizione della dimensione di latenza può includere parametri aggiuntivi). Indica [!DNL line entity = LatencyDim:] l’inizio della definizione della dimensione di latenza.

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

1. Modificare i valori per i parametri Nome, Livello, Clip, Ora, Formato, Ora prima o Ora dopo utilizzando come guida la tabella seguente:

   <table id="table_13DF30B8B7314F118D0ED5DF9EA70B9B"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Per questo parametro... </th> 
      <th colname="col2" class="entry"> Fornire queste informazioni... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Nome </p> </td> 
      <td colname="col2"> <p>Facoltativo. Nome della dimensione della latenza che viene visualizzata nel menu di scelta rapida quando si fa clic con il pulsante destro del mouse sull’etichetta o sugli elementi della dimensione. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Livello </p> </td> 
      <td colname="col2"> <p>Una dimensione numerabile che è l'elemento padre della dimensione latenza. Alcuni esempi includono Sessione, Visitatore e Visualizzazione pagina. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Clip </p> </td> 
      <td colname="col2"> <p>Una dimensione numerabile con una relazione uno-a-molti con il livello della dimensione della latenza. La latenza non viene calcolata oltre i limiti di questa dimensione. Ad esempio, se specificate un livello di visualizzazione pagina e un clip di sessione, le latenze vengono calcolate per le visualizzazioni di pagina che si sono verificate durante la stessa sessione dell'evento. </p> <p>Per informazioni sulle dimensioni uno-molti (semplici), consultate la Guida alla configurazione del <i>set di dati</i>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Tempo </p> </td> 
      <td colname="col2"> <p>Dimensione utilizzata per misurare il tempo trascorso per la dimensione di latenza. Questa dimensione può essere una dimensione temporale, ad esempio Giorno o Ora, o una dimensione numerabile, ad esempio Visitatore, Sessione o Visualizzazione pagina. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Formato </td> 
      <td colname="col2"> <p>Facoltativo. Specifica l'aspetto della visualizzazione della latenza in Workbench dati. Nel parametro Format, potete modificare i seguenti valori: 
      <ul id="ul_ABF4C17BDE2E4F6C9CBDD933674DE861"> 
         <li id="li_5ED6A7267C81444983AF8507ADC6A5AB">Stringa ora. Unità di tempo visualizzata nella visualizzazione della latenza, ad esempio giorno o settimana. Assicurarsi di modificare la stringa di ora quando si modifica la dimensione ora. </li> 
         <li id="li_E3B517ECE1494221AAE90455CC0AAB42">Offset. Un numero intero uguale al negativo del valore Tempo prima. Ad esempio, se Tempo prima è 7, l'offset deve essere -7. </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Ora prima </p> </td> 
      <td colname="col2"> <p>Il tempo massimo (espresso in unità della dimensione Tempo) prima dell'evento per il quale viene calcolata la latenza. Se questo valore è impostato su 0 o non è impostato, la latenza viene calcolata solo per la direzione in avanti. </p> <p>Se modificate questo valore, accertatevi di modificare il valore di offset nel parametro Format: L'offset è il negativo del valore Tempo prima. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Ora dopo </p> </td> 
      <td colname="col2"> <p>Il tempo massimo (espresso in unità della dimensione Tempo) dopo l’evento per il quale viene calcolata la latenza. </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Salvate il [!DNL .vw] file nella cartella Utente\*nome profilo di lavoro*\Work.

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

   Nella dimensione di latenza seguente, la latenza di ogni evento di sessione viene calcolata in ore e Tempo prima è impostata su zero. Pertanto, la latenza viene calcolata solo per le sessioni che si sono svolte entro 24 ore dall&#39;evento definito.

   ```
   entity = LatencyDim:
   Name = string:
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Hour
   Time Before = int: 0
   Time After = int: 24
   ```
