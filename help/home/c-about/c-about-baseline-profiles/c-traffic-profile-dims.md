---
description: Il profilo Traffico contiene le seguenti dimensioni per identificare le azioni dei visitatori.
solution: Analytics
title: Dimensioni del profilo di traffico
topic: Data workbench
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensioni del profilo di traffico{#traffic-profile-dimensions}

Il profilo Traffico contiene le seguenti dimensioni per identificare le azioni dei visitatori.

Le dimensioni nella tabella seguente sono definite nel set di dati per la trasformazione e includono i file nella cartella Traffic\Dataset\Transformation directory.

| Nome | Tipo | Livello | Descrizione |
|---|---|---|---|
| Day | Semplice | Sessione | Il giorno della prima voce di registro della sessione. |
| Giorno della settimana | Semplice | Sessione | Il giorno della settimana della prima voce di registro di una sessione. |
| Esatta durata pagina (nascosta) | Numeriche | Visualizzazioni di pagina | La durata in millisecondi della visualizzazione della pagina misurata sottraendo il tempo della visualizzazione della pagina successiva dal momento della visualizzazione della pagina. La durata esatta dell’ultima visualizzazione pagina in una sessione è sempre 0. |
| Ora | Semplice | Sessione | Ora della prima voce di registro di una sessione. |
| Ora del giorno | Semplice | Sessione | L’ora del giorno della prima voce di registro di una sessione. |
| Mese | Semplice | Sessione | Mese della prima voce di registro di una sessione. |
| Visualizzazioni di pagina | Contabile | Sessione | Una voce di registro o &quot;Record dati evento&quot; che soddisfa la condizione di visualizzazione pagina. |
| Referrer | Semplice | Sessione | Il secondo dominio di livello del referente della prima voce di registro della sessione (o Nessuno se si tratta di un dominio di riferimento interno). |
| Sessione | Contabile | Visitatore | Un periodo di attività contigua correlata da un visitatore. È delimitata da un periodo di inattività di 30 minuti e da un dominio di riferimento esterno o da una durata massima di 48 ore della sessione. Entrambi i timeout e il set di domini considerati interni possono essere configurati nel [!DNL Transformation.cfg] file. |
| URI | Semplice | Visualizzazioni di pagina | L’origine URI di una visualizzazione di pagina. La dimensione URI può essere ridefinita mediante le trasformazioni ReplaceURI, PrependURI e AppendURI. |
| Visitatore | Contabile | N/D | Un valore univoco di x-trackingid. Generalmente corrisponde a un browser univoco se vengono utilizzati cookie persistenti. Il codice x-trackingid può essere altrimenti basato su un numero IP o su un altro identificatore univoco, ad esempio x.509 common name. |
| Settimana | Semplice | Sessione | La settimana della prima voce di registro di una sessione. |

Le dimensioni nella tabella seguente sono definite nella directory Dimension del profilo Traffico:

<table id="table_02AC8DAD1B62443A96FABCB75C37F23A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensione </th> 
   <th colname="col2" class="entry"> Type (Tipo) </th> 
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
   <td colname="col3"> Il primo motore di ricerca in una sessione del visitatore quando un visitatore ha effettuato ricerche da un motore di ricerca denominato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI successivo </td> 
   <td colname="col2"> Derivato (ShiftDim basato sulla dimensione URI) </td> 
   <td colname="col03"> Visualizzazioni di pagina </td> 
   <td colname="col3"> URI dell’URI successivo dopo l’URI attualmente selezionato. Questa dimensione derivata viene utilizzata per eseguire un'analisi delle attività successive dei visitatori dopo un determinato URI. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Onetime/Repeat </td> 
   <td colname="col2"> Derivato (segmentoDim basato sulle metriche Visitatori ripetuti e Visitatori una tantum) </td> 
   <td colname="col03"> Visitatore </td> 
   <td colname="col3"> Il tipo di visitatore: una tantum o ripetizione. I visitatori unici hanno avuto una sola sessione sul sito, mentre i visitatori ripetuti hanno avuto più di una sessione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pagina </td> 
   <td colname="col2"> Derivato (RinominaDim in base alla dimensione URI) </td> 
   <td colname="col03"> Visualizzazioni di pagina </td> 
   <td colname="col3"> Nome di ciascuna pagina visitata durante una sessione. Inizialmente, il nome di ogni pagina è uguale all’URI ma può essere modificato per facilitarne l’interpretazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referrer </td> 
   <td colname="col2"> Ereditato dalla dimensione del referente incorporata </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Il nome di dominio di secondo livello del sito Web che per la prima volta ha fatto riferimento a una sessione al sito (come fornito dal browser del visitatore). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Frase di ricerca </td> 
   <td colname="col2"> Semplice </td> 
   <td colname="col03">Sessione <p>PRIMA RIGA </p></td> 
   <td colname="col3"> La prima frase di ricerca in una sessione del visitatore trasmessa da un motore di ricerca quando un visitatore ha effettuato ricerche da un motore di ricerca denominato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Termine di ricerca </td> 
   <td colname="col2"> Molti-a-molti </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Ogni termine di ricerca trasmesso da un motore di ricerca quando un visitatore dispone di un click-through di un referente di ricerca da un motore di ricerca denominato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durata sessione </td> 
   <td colname="col2"> Derivato (MetricDim basato sulla metrica Exact Page Duration) </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Durata di una sessione con incrementi di 30 secondi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numero sessione </td> 
   <td colname="col2"> Semplice </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Il numero di volte in cui un visitatore ha visitato il sito. Ad esempio, i visitatori che hanno effettuato la prima visita hanno un numero di sessione pari a "1", i visitatori che hanno effettuato la seconda visita hanno un numero di sessione pari a "2" e così via. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzazioni pagina sessione </td> 
   <td colname="col2"> Derivato (MetricDim basato sulla metrica Visualizzazioni di pagina) </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Numero di visualizzazioni di pagina in una sessione. Ad esempio, selezionando "3" nella dimensione Visualizzazioni pagina sessione si selezionano tutte le sessioni con esattamente 3 visualizzazioni di pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Motore di ricerca </td> 
   <td colname="col2"> Semplice </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Il nome di dominio di secondo livello del primo sito Web che è un motore di ricerca con nome e che ha fatto riferimento a un visitatore durante una sessione (come fornito dal browser del visitatore). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensioni tempo </td> 
   <td colname="col2"> Semplice </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Ora, giorno, ora del giorno, settimana, giorno della settimana, mese, trimestre o anno in cui ha avuto inizio una sessione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensioni report tempo </td> 
   <td colname="col2"> Derivato (Ultime N e Rinomina dimensioni in base a dimensioni temporali integrate) </td> 
   <td colname="col03"> Sessione </td> 
   <td colname="col3"> Dimensioni comprese Giorni fa, Giorni del mese scorso, Giorni della settimana scorsa, Giorni di questo mese, Giorni di questa settimana, Ore di oggi, Ore di ieri, Ultimi 12 mesi, Ultimi 2 mesi, Ultime 2 settimane, Ultime 24 ore, Ultimi 3 mesi, Ultime 4 settimane, Ultimi 6 mesi, Ultimi 7 giorni, Ultimi 7 giorni e Oggi, Ultime 8 settimane, Ultimi 9 mesi la settimana scorsa, mesi fa, questo mese, questa settimana, questo e gli ultimi 14 giorni, questo e ultimi 6 mesi, questa e le ultime 8 settimane, oggi, oggi e gli ultimi 30 giorni, settimane fa e ieri forniscono un modo conveniente per creare un'area di lavoro o un report che mostra sempre una parte dei dati nel dataset. Ciascuno è basato su quando è iniziata una sessione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> Ereditato dall’URI dimensione incorporato </td> 
   <td colname="col03"> Visualizzazioni di pagina </td> 
   <td colname="col3"> URI di ciascuna pagina visualizzata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzazioni pagina visitatori </td> 
   <td colname="col2"> Derivato (MetricDim basato sulla metrica Visualizzazioni di pagina) </td> 
   <td colname="col03"> Visitatore </td> 
   <td colname="col3"> Il numero di visualizzazioni di pagina fino alla data per un visitatore. Ad esempio, selezionando "3" nella dimensione Visualizzazioni pagina visitatori, tutti i visitatori con esattamente 3 visualizzazioni di pagina per tutte le sessioni. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referente </td> 
   <td colname="col2"> Ereditato dal riferimento dimensione incorporato </td> 
   <td colname="col03"> Visitatore </td> 
   <td colname="col3"> Il nome di dominio di secondo livello del sito Web che per la prima volta ha indirizzato un visitatore al sito per la prima sessione (come fornito dal browser del visitatore). </td> 
  </tr> 
 </tbody> 
</table>

