---
description: Le espressioni di Dimension non vengono mai utilizzate da sole, ma possono essere utilizzate ovunque venga chiamata una dimensione in un’espressione metrica o filtro.
title: Sintassi delle espressioni dimensione
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
exl-id: 58609e31-8ad8-418b-9a9f-40462d6443f7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 0%

---

# Sintassi delle espressioni dimensione{#syntax-for-dimension-expressions}

Le espressioni di Dimension non vengono mai utilizzate da sole, ma possono essere utilizzate ovunque venga chiamata una dimensione in un’espressione metrica o filtro.

1. Le parole sottolineate devono essere inserite letteralmente nel testo dell’espressione.
1. Il modulo `{TEXT}?` rappresenta un testo facoltativo.
1. Il modulo `{TEXT}*` rappresenta il testo che può verificarsi zero o più volte.
1. Il modulo `{A | B | C |...}` rappresenta il testo costituito esattamente da una delle opzioni specificate, ad esempio A o B o C....
1. Il modulo `[A,B)` rappresenta un intervallo di numeri, da A a B escluso.

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identificatore </p> </td> 
   <td colname="col2"> <p>Un identificatore fa riferimento a una dimensione denominata. Per le regole che disciplinano gli identificatori legali, consulta <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Sintassi per gli identificatori </a>. </p> <p>Esempio: Sessions[ Session_Number = "1" ] è il numero di sessioni con un numero di sessione pari a "1". Numero sessione è una dimensione denominata a cui fa riferimento l’identificatore . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Dimensione) </p> </td> 
   <td colname="col2"> <p>Il risultato di (Dimension) è lo stesso del risultato del Dimension. Le parentesi specificano l’ordine delle operazioni in un’espressione. </p> <p>Esempio: Sessions[ (Pagina) = "/home" ] è il numero di sessioni che visitano la pagina "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Diminuisci per livello </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione con gli stessi elementi della quota Dim, ma relativa ad altre dimensioni attraverso il livello di dimensione. </p> <p>In particolare, un elemento della nuova dimensione si riferisce agli stessi elementi di livello dello stesso elemento di Dim e si riferisce agli elementi di qualsiasi altra dimensione che si riferiscono a uno qualsiasi di tali elementi di livello. </p> <p>Esempio: Sessions[ (Pagina per visitatore)="/home" ] è il numero di sessioni dei visitatori che hanno visitato la pagina "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione con gli stessi elementi della quota Dim. Il decimo elemento del livello di dimensione si riferisce allo stesso elemento della nuova dimensione dell’elemento di Dim correlato all’elemento e+Nth di Livello, a condizione che gli elementi eth ed e+Nth del livello si riferiscano allo stesso elemento del gruppo di dimensioni. </p> <p>Esempio: Page_Views[ shift(Page, Page_View, Session, 1)="/home" ] è il numero di visualizzazioni di pagina per le quali la pagina successiva visualizzata nella stessa sessione è "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Simile a Maiusc(Dim,Level,Group,N), tranne per il fatto che se nella dimensione sono presenti valori vuoti, questi vengono ignorati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> Definisce una dimensione che classifica gli elementi di Livello in base a un elenco di filtri. Gli elementi della nuova dimensione sono le stringhe date come argomenti. Ogni elemento di Livello si riferisce al primo elemento della dimensione del segmento il cui filtro ammette l’elemento di Livello. È simile alla visualizzazione dei segmenti. </p> <p>Esempio: segment(Visitatore, "Visitatori una tantum" -&gt; Visitor_Sessions = 1, "Visitatori molto fedeli" -&gt; Visitor_Sessions &gt; 10, "Tutti gli altri" -&gt; True) crea una dimensione che classifica i visitatori in tre gruppi - I visitatori una tantum sono quelli con una sola sessione, i visitatori molto fedeli sono quelli con più di dieci sessioni e tutti gli altri visitatori hanno un valore di "Tutti gli altri". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Start {, Size}? }?) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione i cui elementi sono intervalli di numeri (di dimensioni fisse, ad esempio [0-9], [10-19],...). Gli elementi di Livello si riferiscono all’elemento dell’attenuazione del bucket il cui intervallo contiene il valore di Metric per l’elemento di livello. Format è la stringa in formato printf utilizzata per formattare gli elementi di Metric. </p> <p>Esempio: Se Page_Duration_Minutes è una dimensione a livello di visualizzazione di pagina che rappresenta il numero di minuti trascorsi su ogni pagina, bucket(Session, sum(Page_Duration_Minutes, Page_View), 100, "%0.0f minutes", 0, 5) è una dimensione a livello di sessione che rappresenta il numero di minuti trascorsi in ogni sessione; gli elementi sono intervalli di 5 minuti <code>{[0-5), [5-10),...,[495-500)}</code>. </p> <p>Start è il valore iniziale del primo intervallo (impostazione predefinita: 0) e Dimensione è la dimensione dell'intervallo (impostazione predefinita: 1). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prefix(Livello {,Nome elemento-&gt;(Prefisso{,Prefix}* )}* ) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione i cui elementi sono le stringhe ElementName specificate e sono associati ai set corrispondenti di stringhe Prefix. Gli elementi di Livello si riferiscono all’elemento del prefisso dim, associato al prefisso più lungo corrispondente al nome dell’elemento di livello specificato. I prefissi che terminano con il carattere speciale '$' devono corrispondere esattamente. </p> <p>Ad esempio, prefisso(URI, "Products" -&gt; ("/products/"), "Services" -&gt; ("/services/", "/products/service/"), "Warranties" -&gt; ("/products/warranty.html$", "/services/warranty.html$", "Everything Else" -&gt; ("/")) crea una dimensione che classifica gli URI nelle quattro categorie elencate. L’effetto sulle varie pagine è il seguente: </p> <p>/products/warranty.html entra in garanzia, poiché corrisponde esattamente al prefisso /products/warranty.html$. </p> <p>/products/cars/specialcar.html Entra in Products, poiché corrisponde al prefisso /products/ e non utilizza più il prefisso . </p> <p>/products/service/something.html accede a Servizi, in quanto corrisponde al prefisso /products/service/ che è più lungo del prefisso /products/ . </p> <p>/companyinfo/aboutus.html Entra nella categoria "Tutto il resto", poiché l’unico prefisso che corrisponde è "/". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>latenza (Livello, Clip, Dim, Filtro, MaxBefore, MaxAfter, FormatString) </p> </td> 
   <td colname="col2"> <p>Consulta <a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a"> Creazione di Dimension di latenza </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cartesian_product(Separator {,Dim}*) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione i cui elementi sono tutte le combinazioni ("il prodotto cartesiano") degli elementi delle dimensioni date. Il nome di ciascun elemento è composto dalla concatenazione degli elementi corrispondenti nelle dimensioni di input, separati dalla stringa Separatore specificata. </p> <p>Ad esempio, se la dimensione D1 contiene elementi {"a", "b"} e la dimensione D2 ha gli elementi {"x", "y"}, allora il prodotto cartesiano("-", D1, D2) ha gli elementi {"a-x", "a-y", "b-x", "b-y"}. </p> <p>Tieni presente che internamente, ciascuna delle dimensioni di input viene trattata come se il numero dei suoi elementi fosse la potenza successiva più elevata di due. Questo fa sì che il prodotto cartesiano abbia alcuni elementi fittizi. Quando utilizzi l’API Data Workbench, a seconda del formato di output, questi elementi possono essere inviati o visualizzati come "#nnn", dove nnn è l’ordinale dell’elemento (e deve essere ignorato dal client). </p> <p>Ad esempio, nell'esempio precedente, se D2 avesse i tre elementi {"x", "y", "z"}, verrebbe trattato come se avesse quattro elementi, e il prodotto cartesiano avrebbe gli elementi {"a-x", "a-y", "a-z", "#3", "b-x", "b-y", "b-z", "#7"}. </p> <p>Se non vengono fornite dimensioni, il risultato è una dimensione con un elemento, "#0", che equivale alla dimensione None. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>più vicino_numerabile(Dim) </p> </td> 
   <td colname="col2"> <p>Fa riferimento a una dimensione già esistente: l'antenato contabile più vicino di Dim nello schema. Ad esempio, l’URI (Countable) più vicino è identico a Page_View. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>normalizzato(Dim,Count) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione normalizzata dalla dimensione standard Dim, con un massimo di elementi Count. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione che ha un sottoinsieme degli elementi della quota Dim, i cui elementi rappresentano sezioni di tempo, ad esempio giorni, settimane o anni. </p> <p>Il sottoinsieme è un intervallo che si estende intorno a un tempo specificato, il valore della metrica costante TimeMetric, che viene interpretato come valore del tempo in secondi dalla mezzanotte UTC del 1° gennaio 1970. L'intervallo include elementi Count, l'ultimo dei quali è costituito da elementi Offset dopo l'elemento Dim specificato il cui nome è il risultato della formattazione del valore della metrica con la stringa FormatString specificata. FormatString utilizza gli stessi escape % della funzione di stringa della libreria C standard. </p> <p>Se trimToData è true, tutti gli elementi all'inizio della dimensione risultante, che sarebbe prima dell'inizio di Dim, vengono rimossi. Quando è false, ci sarà sempre il numero esatto di elementi specificati da Count. Tieni presente che alla fine della dimensione risultante possono sempre essere presenti elementi che non sono effettivamente in Dim. </p> <p>L'facoltativo WeekStart, se specificato, deve essere uno dei seguenti valori: { "Sun", "Mon", "Tue", "Wed", "Thu", "Ven", "Sat" }. Modifica TimeMetric spostandolo indietro al più recente evento di quel giorno feriale. </p> <p>Esempio: Se la Settimana presenta gli elementi { "10/03/10", "10/10/10", ..., "12/12/10" } e la metrica incorporata A di ha il valore 1292348109 (che rappresenta un’ora a metà del 14 dicembre 20 10), quindi ultimo n(Week, As_Of, "%m/%d/%y", 4, 0, false, "Sun") definisce la dimensione con gli elementi { "12/12/10", "19/12/10", "23/12/10", "12/30/10" }. </p> <p>Esempio 2: Se la dimensione Settimana contiene solo elementi {"12/19/10", "26/12/10", ..., "01/30/11"} e la metrica A di è come sopra, l’ultima n(Settimana, Come_Di, "%m/%d/%y", 4, 0, true, "Sole") fornisce una dimensione con elementi {"19/12/10", "23/12/10", "30/12/10"}. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_previous_month(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione che ha un sottoinsieme degli elementi di Dim, i cui elementi rappresentano i giorni. Il sottoinsieme è un intervallo che si estende intorno a un tempo specificato, il valore della metrica costante TimeMetric, che viene interpretato come valore del tempo in secondi dalla mezzanotte UTC del 1° gennaio 1970. L’intervallo includerà gli elementi corrispondenti a ogni giorno nei n mesi che precedono l’ora specificata. Se includeThisMonth è true, l'intervallo include anche ogni giorno del mese che contiene l'ora specificata. </p> <p>FormatString specifica la formattazione degli elementi di Dim, utilizzando "%" escape come nella stringa della funzione di libreria C standard. </p> <p>Se trimToData è true, tutti gli elementi all'inizio della dimensione risultante, che sarebbe prima dell'inizio di Dim, vengono rimossi. Quando è false, ci sarà sempre il numero esatto di elementi specificati da Count. Tieni presente che alla fine della dimensione risultante possono sempre essere presenti elementi che non sono effettivamente in Dim. </p> <p>Esempio: Se Day ha gli elementi { "01/01/10", "01/02/10", ..., "12/31/10" } e la metrica A di integrata ha il valore 1292348109 (che rappresenta un’ora a metà del 14 dicembre 200 10), quindi i giorni dei mesi precedenti (Giorno, As_Of, "%m/%d/%y", 2, false, false) avranno gli elementi { "10/01/10", "10/02/10", ..., "11/30/10" }. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>Simile ai giorni dei mesi precedenti, ad eccezione degli elementi corrispondono solo ai giorni dello stesso mese del tempo specificato da TimeMetric. Se allMonth è true, ci sarà un elemento per ogni giorno del mese appropriato; in caso contrario, solo i giorni dal primo del mese appropriato al giorno contenente l’ora specificata saranno parte della dimensione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_future_month(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Simile ai giorni dei mesi precedenti, con la differenza che gli elementi corrispondono ai giorni dei mesi successivi, anziché precedenti, al mese contenente il tempo specificato da TimeMetric. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hours_of_day(Dim, Metric, TimeFormatString, nDaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>Definisce una dimensione che ha un sottoinsieme degli elementi di Dim, i cui elementi rappresentano le ore. Il sottoinsieme è un intervallo che si estende intorno a un tempo specificato, il valore della metrica costante TimeMetric, che viene interpretato come valore del tempo in secondi dalla mezzanotte UTC del 1° gennaio 1970. L'intervallo include gli elementi corrispondenti a ogni ora del giorno nDaysForward dopo il giorno contenente l'ora specificata da TimeMetric. </p> <p>FormatString specifica la formattazione degli elementi di Dim, utilizzando "%" escape come nella stringa della funzione di libreria C standard. La stringa di formato deve sempre restituire una stringa che rappresenta la mezzanotte all'inizio del giorno dell'ora passata. </p> <p>Se trimToData è true, tutti gli elementi all'inizio della dimensione risultante, che sarebbe prima dell'inizio di Dim, vengono rimossi. Quando è false, ci sarà sempre il numero esatto di elementi specificati da Count. Tieni presente che alla fine della dimensione risultante possono sempre essere presenti elementi che non sono effettivamente in Dim. </p> <p>Esempio: Se Hour ha gli elementi { "01/01/10 00:00", "01/01/10 01:00", ..., "12/31/10 23:00" }, e la metrica incorporata Come di ha il valore 1292348 109 (che rappresenta un’ora a metà dicembre 14, 2010), poi ore del giorno (ora, As_Of, "%x 00:00", 0, false) ha elementi { "12/12/10 00:00", "12/12/10 01:00" , ..., "12/12/10 23:00" }. </p> </td> 
  </tr> 
 </tbody> 
</table>
