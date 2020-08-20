---
description: Le espressioni Dimension non vengono mai utilizzate da sole, ma possono essere utilizzate ovunque venga chiamata una dimensione in un'espressione metrica o filtro.
solution: Analytics
title: Sintassi delle espressioni dimensione
topic: Data workbench
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
translation-type: tm+mt
source-git-commit: a276b16565634fea9b693206c8a55b528fada977
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 0%

---


# Sintassi delle espressioni dimensione{#syntax-for-dimension-expressions}

Le espressioni Dimension non vengono mai utilizzate da sole, ma possono essere utilizzate ovunque venga chiamata una dimensione in un&#39;espressione metrica o filtro.

1. Le parole sottolineate devono essere inserite letteralmente nel testo dell&#39;espressione.
1. Il modulo `{TEXT}?` rappresenta il testo facoltativo.
1. Il modulo `{TEXT}*` rappresenta il testo che può ripetersi zero o più volte.
1. Il modulo `{A | B | C |...}` rappresenta il testo composto esattamente da una delle opzioni specificate, ad esempio A, B o C....
1. Il modulo `[A,B)` rappresenta un intervallo di numeri, da A a B escluso.

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identificatore </p> </td> 
   <td colname="col2"> <p>Un identificatore fa riferimento a una dimensione con nome. Per le regole che disciplinano gli identificatori legali, vedere <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Sintassi per gli identificatori </a>. </p> <p>Esempio: Sessioni[ Session_Number = "1" ] indica il numero di sessioni con numero di sessione "1". Numero sessione è una dimensione con nome a cui fa riferimento l'identificatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Dimensione) </p> </td> 
   <td colname="col2"> <p>Il risultato di (Dimension) è lo stesso del risultato del Dimension. Le parentesi specificano l'ordine delle operazioni in un'espressione. </p> <p>Esempio: Sessioni[ (Pagina) = "/home" ] indica il numero di sessioni in cui è possibile visitare la pagina "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim per livello </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione con gli stessi elementi della quota Dim, ma con altre dimensioni attraverso il livello della quota. </p> <p>Specificamente, un elemento della nuova dimensione si riferisce agli stessi elementi di livello dello stesso elemento di Dim, e si riferisce agli elementi di qualsiasi altra dimensione che si riferiscono a uno qualsiasi di questi elementi di livello. </p> <p>Esempio: Sessioni[ (Pagina per visitatore)="/home" ] indica il numero di sessioni di visitatori che hanno visitato la pagina "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Definisce una quota con gli stessi elementi della quota Dim. Il decimo elemento del livello di dimensione si riferisce allo stesso elemento della nuova dimensione dell’elemento Dim correlato all’elemento e+Nth del livello, a condizione che gli elementi eth e e+Nth del livello siano correlati allo stesso elemento del gruppo di dimensioni. </p> <p>Esempio: Page_Views[ shift(Page, Page_View, Session, 1)="/home" ] indica il numero di visualizzazioni di pagina per cui la pagina successiva visualizzata nella stessa sessione è "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Simile a shift(Dim,Level,Group,N), tranne per il fatto che se nella dimensione sono presenti valori vuoti, questi vengono ignorati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> Definisce una dimensione che classifica gli elementi di livello in base a un elenco di filtri. Gli elementi della nuova dimensione sono le stringhe date come argomenti. Ciascun elemento di Livello si riferisce al primo elemento della dimensione del segmento il cui filtro ammette l’elemento di Livello. È simile alla visualizzazione dei segmenti. </p> <p>Esempio: segment(Visitatore, "Visitatori una tantum" -&gt; Visitor_Sessions = 1, "Visitatori molto fedeli" -&gt; Visitor_Sessions &gt; 10, "Tutti gli altri" -&gt; True) crea una dimensione che classifica i Visitatori in tre gruppi — I Visitatori una tantum sono quelli con una sola sessione, quelli con più di dieci sessioni, e tutti gli altri visitatori hanno un valore di "Tutti gli altri". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Start {, Size}? }?) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione i cui elementi sono intervalli di numeri (di dimensione fissa, ad esempio [0-9], [10-19],...). Gli elementi di livello si riferiscono all'elemento del dim del bucket il cui intervallo contiene il valore di Metric per l'elemento di livello specificato. Format è la stringa in formato printf utilizzata per formattare gli elementi di Metric. </p> <p>Esempio: Se la dimensione Page_Duration_Minutes è una dimensione a livello di visualizzazione pagina che rappresenta il numero di minuti trascorsi su ciascuna pagina, bucket(Session, sum(Page_Duration_Minutes, Page_View), 100, "%0.0f Minutes", 0, 5) è una dimensione a livello di sessione che rappresenta il numero di minuti trascorsi in ciascuna sessione; gli elementi sono intervalli di 5 minuti <code>{[0-5), [5-10),...,[495-500)}</code>. </p> <p>Start è il valore iniziale del primo intervallo (impostazione predefinita: 0) e Dimensione è la dimensione dell'intervallo (impostazione predefinita: 1). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prefix(Level {,ElementName-&gt;(Prefix{,Prefix}* )}* ) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione i cui elementi sono le stringhe ElementName date e sono associati ai set corrispondenti di stringhe Prefix. Gli elementi di livello si riferiscono all’elemento del prefisso dim, associato al prefisso più lungo corrispondente al nome dell’elemento di livello specificato. I prefissi che terminano con il carattere speciale '$' devono corrispondere esattamente. </p> <p>Ad esempio, prefix(URI, "Products" -&gt; ("/products/"), "Services" -&gt; ("/services/", "/products/service/"), "Warranties" -&gt; ("/products/warranty.html$", "/services/warranty.html$", "All Else" -&gt; ("/") crea una dimensione che classifica gli URI nelle quattro categorie elencate. L’effetto sulle varie pagine è il seguente: </p> <p>/products/warranty.html Entra in garanzia, poiché corrisponde esattamente al prefisso /products/warranty.html$. </p> <p>/products/cars/specialcar.html va in Products (Prodotti), poiché corrisponde al prefisso /products/ e non ha più il prefisso </p> <p>/products/service/something.html Entra nei servizi, poiché corrisponde al prefisso /products/service/ che supera il prefisso /products/. </p> <p>/companyinfo/aboutus.html Entra nella categoria "Tutto il resto", poiché l'unico prefisso che corrisponde è "/". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>latency(Level, Clip, Dim, Filter, MaxBefore, MaxAfter, FormatString) </p> </td> 
   <td colname="col2"> <p>Consultate <a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a"> Creazione di Dimension di latenza </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cartesian_product(Separator {,Dim}*) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione i cui elementi sono tutte le combinazioni ("il prodotto cartesiano") degli elementi delle dimensioni date. Il nome di ciascun elemento è composto dalla concatenazione degli elementi corrispondenti nelle dimensioni di input, separati dalla stringa Separatore data. </p> <p>Ad esempio, se la dimensione D1 include gli elementi {"a", "b"} e la dimensione D2 ha gli elementi {"x", "y"}, quindi il prodotto cartesiano("-", D1, D2) ha gli elementi {"a-x", "a-y", "b-x", "b-y"}. </p> <p>Si noti che internamente, ciascuna delle dimensioni di input viene trattata come se il numero dei suoi elementi fosse la potenza successiva più alta di due. Questo si traduce nel prodotto cartesiano con alcuni elementi fittizi. Quando si utilizza l'API Data Workbench, a seconda del formato di output, questi elementi possono essere richiesti, oppure possono essere visualizzati come "#nnn", dove nnn è l'ordinale dell'elemento (e deve essere ignorato dal client). </p> <p>Ad esempio, nell'esempio precedente, se D2 contenesse i tre elementi {"x", "y", "z"}, verrebbe trattato come se avesse quattro elementi, e il prodotto cartesiano avrebbe gli elementi {"a-x", "a-y", "a-z", "#3", "b-x", "b-y", "b-z", "#7"}. </p> <p>Se non viene specificata alcuna dimensione, il risultato è una dimensione con un elemento, "#0", che equivale alla dimensione Nessuno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>near_countable(Dim) </p> </td> 
   <td colname="col2"> <p>Fa riferimento a una dimensione già esistente: l'antenato contabile più vicino di Dim nello schema. Ad esempio, l’URI (countable) più vicino è identico a Page_View. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>normalizzato(Dim,Count) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione normalizzata dalla dimensione standard Dim, con un massimo di elementi Count. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione con un sottoinsieme degli elementi della dimensione Dim, i cui elementi rappresentano sezioni di tempo, ad esempio giorni, settimane o anni. </p> <p>Il sottoinsieme è un intervallo che si estende intorno a un tempo specificato, il valore della metrica costante TimeMetric, che viene interpretata come un valore di tempo in secondi a partire dalla mezzanotte UTC del 1 gennaio 1970. L'intervallo contiene elementi Count, l'ultimo dei quali è costituito da elementi Offset dopo l'elemento Dim specificato il cui nome è il risultato della formattazione del valore della metrica con la stringa FormatString data. FormatString utilizza lo stesso valore % escape della funzione di libreria standard strftime. </p> <p>Se trimToData è true, vengono rimossi tutti gli elementi all’inizio della dimensione risultante, che si trova prima dell’inizio di Dim. Se è false, ci sarà sempre il numero esatto di elementi specificato da Count. Si noti che alla fine della dimensione risultante possono sempre essere presenti elementi che non sono effettivamente in Dim. </p> <p>L'facoltativo WeekStart, se specificato, deve essere uno dei { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" }. Modifica TimeMetric spostandolo all'indietro fino all'occorrenza più recente di quel giorno feriale. </p> <p>Esempio: Se la Settimana contiene gli elementi { "10/03/10", "10/10/10", ..., "12/12/10" } e la metrica incorporata Come di ha il valore 1292348109 (che rappresenta un'ora a metà del 14 dicembre 20 10), quindi last n(Week, As_Of, "%m/%d/%y", 4, 0, false, "Sun") definisce la dimensione con gli elementi { "12/12/10", "12/19/10", "12/23/10", "12/30/10" }. </p> <p>Esempio 2: Se la dimensione Settimana contiene solo elementi {"12/19/10", "12/26/10", ..., "01/30/11"}, e la metrica Come di è la precedente, l'ultima n(Settimana, Come_Di, "%m/%d/%y", 4, 0, vera, "Sole") fornisce una dimensione con elementi {"12/19/10", "12/23/10", "12/30/10"}. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Days_of_previous_month(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione con un sottoinsieme degli elementi di Dim, i cui elementi rappresentano i giorni. Il sottoinsieme è un intervallo che si estende intorno a un tempo specificato, il valore della metrica costante TimeMetric, che viene interpretata come un valore di tempo in secondi a partire dalla mezzanotte UTC del 1 gennaio 1970. L'intervallo includerà gli elementi corrispondenti a ogni giorno negli n mesi che precedono l'ora specificata. Se includeThisMonth è true, l'intervallo include anche ogni giorno del mese che contiene l'ora specificata. </p> <p>FormatString specifica la formattazione degli elementi di Dim, utilizzando "%" escape come nella funzione standard della libreria C strftime. </p> <p>Se trimToData è true, vengono rimossi tutti gli elementi all’inizio della dimensione risultante, che si trova prima dell’inizio di Dim. Se è false, ci sarà sempre il numero esatto di elementi specificato da Count. Si noti che alla fine della dimensione risultante possono sempre essere presenti elementi che non sono effettivamente in Dim. </p> <p>Esempio: Se Day include gli elementi { "01/01/10", "01/02/10", ..., "12/31/10" } e la metrica incorporata As Of ha il valore 1292348109 (che rappresenta un'ora a metà del 14 dicembre 20 10), quindi i giorni dei mesi precedenti (Giorno, Come_Di, "%m/%d/%y", 2, false, false) avranno gli elementi { "10/01/10", "10/02/10", ..., "11/30/10" }. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>Simili ai giorni dei mesi precedenti, tranne che gli elementi corrispondono solo a giorni dello stesso mese come specificato da TimeMetric. Se allMonth è true, ci sarà un elemento per ogni giorno del mese appropriato; altrimenti, solo i giorni dal primo del mese appropriato al giorno contenente l'ora specificata saranno parte della dimensione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Days_of_future_month(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Simili ai giorni dei mesi precedenti, fatta eccezione per il fatto che gli elementi corrispondono ai giorni dei mesi successivi, anziché precedenti, al mese contenente il tempo specificato da TimeMetric. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hours_of_day(Dim, Metric, TimeFormatString, nDaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione con un sottoinsieme degli elementi di Dim, i cui elementi rappresentano le ore. Il sottoinsieme è un intervallo che si estende intorno a un tempo specificato, il valore della metrica costante TimeMetric, che viene interpretata come un valore di tempo in secondi a partire dalla mezzanotte UTC del 1 gennaio 1970. L'intervallo include gli elementi corrispondenti a ogni ora del giorno nDaysForward dopo il giorno contenente l'ora specificata da TimeMetric. </p> <p>FormatString specifica la formattazione degli elementi di Dim, utilizzando "%" escape come nella funzione standard della libreria C strftime. La stringa di formato deve sempre restituire una stringa che rappresenta la mezzanotte all'inizio del giorno dell'ora passata. </p> <p>Se trimToData è true, vengono rimossi tutti gli elementi all’inizio della dimensione risultante, che si trova prima dell’inizio di Dim. Se è false, ci sarà sempre il numero esatto di elementi specificato da Count. Si noti che alla fine della dimensione risultante possono sempre essere presenti elementi che non sono effettivamente in Dim. </p> <p>Esempio: Se Hour ha gli elementi { "01/01/10 00:00", "01/01/10 01:00", ..., "12/31/10 23:00" }, e la metrica incorporata Come di ha il valore 1292348 109 (che rappresenta un'ora a metà del 14 dicembre 2010), quindi ore del giorno (ora, come_di, "%x 00:00", 0, false) contiene elementi { "12/12/10 00:00", "12/12/10 01:00" , ..., "12/12/10 23:00" }. </p> </td> 
  </tr> 
 </tbody> 
</table>

