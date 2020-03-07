---
description: Nel server workbench dati sono disponibili diversi tipi di dimensioni. È quindi importante conoscere il tipo di dimensione quando si utilizza una dimensione per creare metriche, filtri o dimensioni derivate.
solution: Analytics
title: Tipi di dimensioni
topic: Data workbench
uuid: 07659373-8d9b-473d-8daa-ca8e7ac4afe8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tipi di dimensioni{#dimension-types}

Nel server workbench dati sono disponibili diversi tipi di dimensioni. È quindi importante conoscere il tipo di dimensione quando si utilizza una dimensione per creare metriche, filtri o dimensioni derivate.

Insight Server può creare e mantenere i seguenti tipi di dimensioni:

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
   <td colname="col2">Tipo di dimensione in cui il numero di elementi nella dimensione può essere conteggiato dal sistema. Le dimensioni contabili devono essere derivate da altre dimensioni Contabili. Le dimensioni contabili possono essere elementi padre di altre dimensioni o elementi secondari di altre dimensioni computabili. <p>Esempi: Visitatore, Sessione, Visualizzazione pagina, Prenotazione e Ordine. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Semplice </td> 
   <td colname="col2">Una dimensione con una relazione uno-a-molti con una dimensione contabile padre. Una dimensione semplice può essere considerata come una proprietà di elementi della sua dimensione padre. <p>Esempio: Il referente visitatore è una dimensione semplice con un elemento padre della dimensione Visitatore. Ciascun visitatore può avere un solo visitatore Referente (il primo referente HTTP), ma molti di essi potrebbero avere lo stesso visitatore Referente. Pertanto, il referente visitatore è "uno-molti" con la dimensione Visitatore. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numeriche </td> 
   <td colname="col2">Una dimensione con valori ordinati, numerici e una relazione uno-a-molti con una dimensione numerabile padre. Una dimensione numerica può essere considerata come una proprietà numerica di elementi della dimensione padre. Le dimensioni numeriche vengono spesso utilizzate per definire le metriche "sum". <p>Esempio: La dimensione numerica Entrate sessione definisce le entrate, in dollari, per ogni sessione. Ogni sessione dispone di un singolo importo di entrate, ma un numero qualsiasi di sessioni potrebbe avere le stesse entrate, quindi le entrate di sessione sono "uno a molti" con la sessione. Una metrica "Revenue" potrebbe essere definita come <span class="filepath"> sum(Session_Revenue, Session)</span>, che indica l'importo totale delle entrate per le sessioni selezionate. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Molti-a-molti </td> 
   <td colname="col2">Una dimensione che ha una relazione molti-a-molti con una dimensione contabile padre. Una dimensione molti-a-molti può essere considerata come una "serie" di valori per ogni elemento della sua dimensione padre. Una dimensione "molti-a-molti" equivale a una dimensione numerabile (anonima) con il suo elemento padre e una dimensione semplice con un elemento padre della dimensione anonima calcolabile. <p>Esempio: La frase di ricerca di molte dimensioni ha un elemento padre di Session. Ogni sessione può utilizzare zero o più frasi di ricerca, e una frase di ricerca può essere utilizzata in un numero qualsiasi di sessioni. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormale </td> 
   <td colname="col2">Una dimensione con una relazione uno-a-uno con una dimensione Contabile padre. I nomi degli elementi della dimensione standard possono contenere informazioni sugli elementi corrispondenti della dimensione padre. Una dimensione standard può essere considerata come memorizzazione di un valore di stringa arbitrario per ciascun elemento dell'elemento padre. Le dimensioni standard possono essere utilizzate con la funzionalità di esportazione dei segmenti di Insight Server per fornire dettagli su un sottoinsieme o un "segmento" di una dimensione numerabile. Inoltre, è possibile fare riferimento alle dimensioni standard nelle formule delle metriche e nelle visualizzazioni del foglio di lavoro e utilizzare (con determinate limitazioni) per definire i filtri. <p>Esempio: La dimensione standard Indirizzo e-mail ha un elemento padre di Visitor. Ogni visitatore dispone di un indirizzo e-mail e ogni elemento della dimensione Indirizzo e-mail è associato a un singolo visitatore. Anche se due visitatori hanno lo stesso indirizzo e-mail, i loro indirizzi saranno elementi diversi della dimensione Indirizzo e-mail. Un'esportazione di segmenti può fare riferimento alla dimensione Indirizzo eMail per restituire l'indirizzo e-mail di ogni visitatore in un segmento. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo </td> 
   <td colname="col2">Dimensione che consente di creare un set di dimensioni temporali locali periodiche o assolute (come Giorno, Giorno della settimana, Ora, Ora del giorno e così via) in base a un campo di marca temporale specificato. Quando definite le dimensioni dell’ora, potete anche scegliere un giorno diverso dal lunedì da usare come inizio di una settimana specificando il parametro Giorno inizio settimana. <p>Esempio: La dimensione temporale Durata sessione è padre della sessione. Pertanto, la dimensione definisce un insieme di dimensioni temporali (Giorno, Giorno della settimana, Ora, Ora del giorno, Mese e Settimana) i cui elementi corrispondono agli orari in cui sono iniziate le sessioni dei visitatori sul sito. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivato </td> 
   <td colname="col2">Le dimensioni derivate, anziché essere definite nella configurazione del dataset in base ai dati in elaborazione, sono definite nel profilo in base ad altre dimensioni o metriche. Molte dimensioni derivate vengono create automaticamente per determinare diversi tipi di visualizzazioni. <p>Ad esempio, quando un utente crea una mappa del sito o del processo, Insight Server crea automaticamente una dimensione "Prefix". Altri, come le dimensioni dell'ora di reporting, sono definiti dai file nella directory Dimensions di un profilo. </p></td> 
  </tr> 
 </tbody> 
</table>

