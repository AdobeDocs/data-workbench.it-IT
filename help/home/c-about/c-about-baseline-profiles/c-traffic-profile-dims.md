---
description: Il profilo Traffico contiene le seguenti dimensioni per identificare le azioni dei visitatori.
title: Dimensioni del profilo di traffico
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
exl-id: 1e7d2904-aa5d-4848-a398-5d4669953be9
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 8%

---

# Dimensioni del profilo di traffico{#traffic-profile-dimensions}

{{eol}}

Il profilo Traffico contiene le seguenti dimensioni per identificare le azioni dei visitatori.

Le dimensioni nella tabella seguente sono definite nel set di dati di trasformazione includono file nella directory Traffic\Dataset\Transformation .

| Nome | Tipo | Livello | Descrizione |
|---|---|---|---|
| Giorno | Semplice | Sessione | Il giorno della prima voce di registro della sessione. |
| Giorno della settimana | Semplice | Sessione | Il giorno della settimana della prima voce di registro di una sessione. |
| Durata esatta della pagina (nascosta) | Numeriche | Visualizzazioni di pagina | La durata in millisecondi della visualizzazione della pagina misurata sottraendo il tempo della visualizzazione della pagina successiva dal momento in cui viene visualizzata la pagina. La durata esatta dell’ultima visualizzazione di pagina in una sessione è sempre 0. |
| Ora | Semplice | Sessione | Ora della prima voce di registro di una sessione. |
| Ora del giorno | Semplice | Sessione | Ora del giorno della prima voce di log di una sessione. |
| Mese | Semplice | Sessione | Mese della prima voce di registro di una sessione. |
| Visualizzazioni di pagina | Contabile | Sessione | Una voce di registro o &quot;Record dati evento&quot; che soddisfa la condizione di visualizzazione pagina. |
| Destinatario che inoltra | Semplice | Sessione | Il secondo dominio di livello del referente della prima voce di registro della sessione (o Nessuno se si tratta di un dominio di riferimento interno). |
| Sessione | Contabile | Visitatore | Un periodo di attività contigua correlata da un visitatore. È delimitato da un periodo di inattività di 30 minuti e da un dominio referente esterno o da una durata massima di sessione di 48 ore. È possibile configurare sia il timeout che il set di domini considerati interni nella variabile [!DNL Transformation.cfg] file. |
| URI | Semplice | Visualizzazioni di pagina | L’URI di una visualizzazione di pagina. La dimensione URI può essere ridefinita utilizzando le trasformazioni ReplaceURI, PrependURI e AppendURI. |
| Visitatore | Contabile | N/D | Un valore univoco di x-trackingid. Di solito corrisponde a un browser univoco se vengono utilizzati cookie persistenti. Il codice x-trackingid può essere altrimenti basato su un numero IP o su un altro identificatore univoco, ad esempio il nome comune x.509. |
| Settimana | Semplice | Sessione | La settimana della prima voce di registro di una sessione. |

Le dimensioni nella tabella seguente sono definite nella directory di Dimension del profilo Traffico:

<table id="table_02AC8DAD1B62443A96FABCB75C37F23A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensione </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col03" class="entry"> Livello </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Browser </td> 
   <td colname="col2"> Semplice </td> 
   <td colname="col03"> Visitatore </td> 
   <td colname="col3"> Il tipo di agente utente utilizzato dal visitatore, incluso il numero di versione (ad esempio, MSIE 6.0). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tipo di browser </td> 
   <td colname="col2"> Semplice </td> 
   <td colname="col03"> Visitatore </td> 
   <td colname="col3"> Il tipo di agente utente utilizzato dal visitatore (ad esempio, MSIE). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Motore di ricerca </td> 
   <td colname="col2"> Semplice </td> 
   <td colname="col03">Sessione <p>PRIMA RIGA </p></td> 
   <td colname="col3"> Il primo motore di ricerca nella sessione di un visitatore quando ha eseguito la ricerca da un motore di ricerca denominato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI successivo </td> 
   <td colname="col2"> Derivato (ShiftDim basato su dimensione URI) </td> 
   <td colname="col03"> Visualizzazioni di pagina </td> 
   <td colname="col3"> URI dell’URI successivo dopo l’URI attualmente selezionato. Questa dimensione derivata viene utilizzata per eseguire un’analisi delle operazioni successive dei visitatori dopo un determinato URI. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Onetime e ripetizione </td> 
   <td colname="col2"> Derivato (SegmentDim basato sulle metriche Visitatori ripetuti e Visitatori una tantum) </td> 
   <td colname="col03"> Visitatore </td> 
   <td colname="col3"> Il tipo di visitatore: una tantum o ripetuta. I visitatori occasionali hanno avuto una sola sessione sul sito, mentre i visitatori ripetuti hanno avuto più di una sessione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pagina </td> 
   <td colname="col2"> Derivato (RenameDim basato su dimensione URI) </td> 
   <td colname="col03"> Visualizzazioni di pagina </td> 
   <td colname="col3"> Nome di ogni pagina visitata durante una sessione. Inizialmente, il nome di ogni pagina è lo stesso dell’URI, ma può essere modificato per facilitarne l’interpretazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Destinatario che inoltra </td> 
   <td colname="col2"> Ereditato dalla dimensione referente incorporata </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Il nome di dominio di secondo livello del sito web che per la prima volta ha fatto riferimento a una sessione del sito (come fornito dal browser del visitatore). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Frase di ricerca </td> 
   <td colname="col2"> Semplice </td> 
   <td colname="col03">Sessione <p>PRIMA RIGA </p></td> 
   <td colname="col3"> La prima frase di ricerca nella sessione di un visitatore trasmessa da un motore di ricerca quando un visitatore ha effettuato una ricerca da un motore di ricerca denominato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Termine di ricerca </td> 
   <td colname="col2"> Many-to-Many (Da molti-a-molti) </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Ogni termine di ricerca trasmesso da un motore di ricerca quando un visitatore dispone di un click-through di riferimento di ricerca da un motore di ricerca denominato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durata sessione </td> 
   <td colname="col2"> Derivato (MetricDim basato sulla metrica Exact Page Duration) </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Durata di una sessione con incrementi di 30 secondi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numero di sessioni </td> 
   <td colname="col2"> Semplice </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Il numero di volte in cui un visitatore ha visitato il sito. Ad esempio, per i nuovi visitatori è disponibile il numero di sessione "1", per i visitatori di seconda visita il numero di sessione "2", ecc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzazioni della pagina della sessione </td> 
   <td colname="col2"> Derivato (MetricDim basato sulla metrica Visualizzazioni di pagina) </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Il numero di visualizzazioni di pagina in una sessione. Ad esempio, selezionando "3" nella dimensione Visualizzazioni pagina sessione, verranno selezionate tutte le sessioni con esattamente 3 visualizzazioni di pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Motore di ricerca </td> 
   <td colname="col2"> Semplice </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Il nome di dominio di secondo livello del primo sito Web denominato motore di ricerca che ha fatto riferimento a un visitatore del sito durante una sessione (come specificato dal browser del visitatore). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensioni temporali </td> 
   <td colname="col2"> Semplice </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Ora, giorno, ora del giorno, settimana, giorno della settimana, mese, trimestre o anno in cui è iniziata una sessione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimension di reporting per ora </td> 
   <td colname="col2"> Dimensioni derivate (LastN e Rinomina in base a dimensioni temporali integrate) </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Dimension compresi Giorni fa, Giorni del mese scorso, Giorni della settimana scorsa, Giorni di questo mese, Giorni di questa settimana, Ore di oggi, Ore di ieri, Ultimi 12 mesi, Ultimi 2 mesi, Ultime 2 settimane, Ultime 24 ore, Ultimi 3 mesi, Ultimi 4 settimane, Ultimi 6 mesi, Ultimi 7 giorni, Ultimi 7 giorni e Oggi, Ultimi 8 settimane, 9 mesi, Ultimi Mese, Settimana scorsa, Mesi fa, Questo mese, Questa settimana, Questo e Ultimi 14 Giorni, Questo e Ultimi 6 Mesi, Questa e Ultime 8 Settimane, Oggi, Reporting, Oggi e Ultimi 30 Giorni, Settimane fa e Ieri forniscono un modo conveniente per creare un Workspace o Report che mostra sempre una parte dei dati nel set di dati. Ognuno di essi si basa su quando è iniziata una sessione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> Ereditato dall’URI di Dimension integrato </td> 
   <td colname="col03"> Visualizzazioni di pagina </td> 
   <td colname="col3"> URI di ogni pagina visualizzata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzazioni pagina del visitatore </td> 
   <td colname="col2"> Derivato (MetricDim basato sulla metrica Visualizzazioni di pagina) </td> 
   <td colname="col03"> Visitatore </td> 
   <td colname="col3"> Il numero di visualizzazioni di pagina fino a oggi per un visitatore. Ad esempio, selezionando "3" nella dimensione Visualizzazioni pagina visitatore, tutti i visitatori con esattamente 3 visualizzazioni di pagina in tutte le sessioni. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitor Referrer (Referente visitatore) </td> 
   <td colname="col2"> Ereditato dal referente dimensione incorporato </td> 
   <td colname="col03"> Visitatore </td> 
   <td colname="col3"> Il nome di dominio di secondo livello del sito web che per la prima volta ha fatto riferimento a un visitatore per la prima sessione (come specificato dal browser del visitatore). </td> 
  </tr> 
 </tbody> 
</table>
