---
description: Nel server di Data Workbench sono disponibili diversi tipi di dimensioni. È quindi importante conoscere il tipo di dimensione quando si utilizza una dimensione per creare metriche, filtri o dimensioni derivate.
title: Tipi di dimensioni
uuid: 07659373-8d9b-473d-8daa-ca8e7ac4afe8
exl-id: cbc25504-2c1c-4622-adc1-c9bbac8e12fb
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 2%

---

# Tipi di dimensioni{#dimension-types}

Nel server di Data Workbench sono disponibili diversi tipi di dimensioni. È quindi importante conoscere il tipo di dimensione quando si utilizza una dimensione per creare metriche, filtri o dimensioni derivate.

Insight Server può creare e gestire i seguenti tipi di dimensioni:

<table id="table_1A79B6C57ED145B6AA3BB05DD37AAD1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipi di dimensioni </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Contabile </td> 
   <td colname="col2">Tipo di dimensione in cui il numero di elementi nella dimensione può essere conteggiato dal sistema. Le dimensioni conteggiate devono essere derivate da altre dimensioni conteggiate. Le dimensioni conteggiate possono essere genitori di altre dimensioni o figli di altre dimensioni conteggiate. <p>Esempi: Visitatore, sessione, visualizzazione pagina, prenotazione e ordine. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Semplice </td> 
   <td colname="col2">Una dimensione con una relazione uno-a-molti con una dimensione conteggiata superiore. Una dimensione semplice può essere pensata come rappresentativa di una proprietà di elementi della sua dimensione padre. <p>Esempio: Il referente visitatore è una dimensione semplice con un elemento padre della dimensione Visitatore. Ogni visitatore può avere un solo referente visitatore (il suo primo referente HTTP), ma molti visitatori potrebbero avere lo stesso referente visitatore. Pertanto, il referente visitatore è "uno-a-molti" con la dimensione Visitatore. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numeriche </td> 
   <td colname="col2">Una dimensione con valori numerici ordinati e una relazione uno-a-molti con una dimensione conteggiata superiore. Una dimensione numerica può essere considerata come rappresentativa di una proprietà numerica di elementi della dimensione padre. Le dimensioni numeriche vengono spesso utilizzate per definire le metriche “sum” (somma). <p>Esempio: La dimensione numerica Entrate sessione definisce i ricavi, in dollari, per ogni sessione. Ogni sessione dispone di una singola quantità di ricavi, ma qualsiasi numero di sessioni potrebbe avere gli stessi ricavi, quindi i ricavi della sessione sono "uno-a-molti" con la sessione. Una metrica "Ricavi" può essere definita come <span class="filepath"> sum(Session_Revenue, Session)</span>, indicando la quantità totale di ricavi per le sessioni selezionate. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Many-to-Many (Da molti-a-molti) </td> 
   <td colname="col2">Una dimensione con una relazione molti-a-molti con una dimensione conteggiata superiore. Una dimensione da molti-a-molti può essere considerata come rappresentativa di un "set" di valori per ogni elemento della sua dimensione padre. Una dimensione molti-a-molti equivale a una dimensione numerabile (anonima) con il suo elemento padre e una dimensione semplice con un elemento padre della dimensione numerabile anonima. <p>Esempio: La frase di ricerca a molte dimensioni ha un elemento padre di Session. Ogni sessione può utilizzare zero o più frasi di ricerca e una frase di ricerca può essere utilizzata in qualsiasi numero di sessioni. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormale </td> 
   <td colname="col2">Una dimensione con una relazione uno-a-uno con una dimensione conteggiata superiore. I nomi degli elementi della dimensione standard possono contenere informazioni sugli elementi corrispondenti della dimensione padre. Una dimensione standard può essere considerata come l'archiviazione di un valore di stringa arbitrario per ciascun elemento dell'elemento padre. Le dimensioni standard possono essere utilizzate con la funzionalità di esportazione del segmento di Insight Server per ottenere dettagli su un sottoinsieme o su un "segmento" di una dimensione numerabile. Inoltre, è possibile fare riferimento alle dimensioni comuni nelle formule metriche e nelle visualizzazioni del foglio di lavoro e utilizzarle (con determinate restrizioni) per definire i filtri. <p>Esempio: L’indirizzo e-mail della dimensione standard ha un elemento padre di Visitor. Ogni visitatore ha un indirizzo e-mail e ogni elemento della dimensione Indirizzo e-mail è associato a un singolo visitatore. Anche se due visitatori hanno lo stesso indirizzo e-mail, i loro indirizzi saranno elementi diversi della dimensione Indirizzo e-mail. Un’esportazione di segmenti può fare riferimento alla dimensione Indirizzo e-mail per restituire l’indirizzo e-mail di ogni visitatore in un segmento. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo </td> 
   <td colname="col2">Una dimensione che consente di creare un set di dimensioni locali periodiche o assolute (come Giorno, Giorno della settimana, Ora, Ora del giorno e così via) in base a un campo di marca temporale specificato. Quando definisci le dimensioni dell’ora, puoi anche scegliere un giorno diverso da Lunedì da utilizzare come inizio di una settimana specificando il parametro Giorno inizio settimana . <p>Esempio: La dimensione temporale Tempo sessione è padre della sessione. Pertanto, la dimensione definisce un set di dimensioni temporali (Giorno, Giorno della settimana, Ora, Ora del giorno, Mese e Settimana) i cui elementi corrispondono ai momenti in cui sono iniziate le sessioni dei visitatori sul sito. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivato </td> 
   <td colname="col2">Le dimensioni derivate, anziché essere definite nella configurazione del set di dati in base ai dati in fase di elaborazione, sono definite nel profilo in base ad altre dimensioni o metriche. Molte dimensioni derivate vengono create automaticamente per determinare diversi tipi di visualizzazioni. <p>Ad esempio, quando un utente crea una mappa del sito o del processo, Insight Server crea automaticamente una dimensione "Prefix". Altri, come le dimensioni dell’ora di reporting, sono definiti dai file nella directory dei Dimension di un profilo. </p></td> 
  </tr> 
 </tbody> 
</table>
