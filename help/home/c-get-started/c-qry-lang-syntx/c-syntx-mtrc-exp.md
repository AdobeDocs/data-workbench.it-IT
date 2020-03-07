---
description: Le metriche possono essere modificate utilizzando l'Editor metriche e salvate nella directory Metriche di un profilo.
solution: Analytics
title: Sintassi delle espressioni metriche
topic: Data workbench
uuid: 801e265d-d7e4-4f0f-9698-d0b50dd00995
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sintassi delle espressioni metriche{#syntax-for-metric-expressions}

Le metriche possono essere modificate utilizzando l&#39;Editor metriche e salvate nella directory Metriche di un profilo.

Per ulteriori informazioni, consultate [Creazione e modifica di metriche](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40)derivate. Le espressioni metriche possono essere utilizzate anche nei fogli di lavoro. For more information, see [Worksheets](../../../home/c-get-started/c-analysis-vis/c-wksts/c-wksts.md#concept-45b50aafc4d84709841f14aee8022581). La sintassi seguente viene utilizzata per definire le espressioni metriche.

Note:

1. Le parole sottolineate devono essere inserite letteralmente nel testo dell&#39;espressione.
1. Il modulo {TEXT}? rappresenta testo facoltativo.
1. Il modulo {TEXT}* rappresenta il testo che può ripetersi zero o più volte.
1. Modulo {A| B| C|..} rappresenta il testo che consiste esattamente in una delle opzioni specificate, come A, B o C....
1. Il modulo [A,B] rappresenta un intervallo di numeri, da A a B escluso.

<table id="table_A6CA9C9F396448209398AA2A369E63FA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identificatore </p> </td> 
   <td colname="col2"> <p>Un identificatore fa riferimento a una metrica con nome. Per le regole che disciplinano gli identificatori legali, vedere <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Sintassi per gli identificatori </a>. </p> <p>Esempio: Revenue = Total_Price </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Metrica) </p> </td> 
   <td colname="col2"> <p>Il risultato di (Metrica) è uguale al risultato di Metrica. Le parentesi specificano l'ordine delle operazioni in un'espressione. </p> <p>Esempio: Media = (A + B) / 2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A + B </p> </td> 
   <td colname="col2"> <p>Somma dei risultati della metrica A e della metrica B. </p> <p>Esempio: Valore = Entrate + Risparmio_Costo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A - B </p> </td> 
   <td colname="col2"> <p>Differenza dei risultati della metrica A e della metrica B. </p> <p>Esempio: Profitto = Ricavi - Costo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A * B </p> </td> 
   <td colname="col2"> <p>Prodotto dei risultati delle metriche A e B. </p> <p>Esempio: Dollari = centesimi * 0,01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A/B </p> </td> 
   <td colname="col2"> <p>Rapporto tra i risultati della metrica A e della metrica B. </p> <p>Esempio: Revenue_per_Session = Revenue/Sessions </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A ^ B </p> </td> 
   <td colname="col2"> <p>Risultato della metrica A elevato alla potenza del risultato della metrica B. </p> <p>Esempio: Area = Larghezza^2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trust(Metric) </p> </td> 
   <td colname="col2"> <p>Una stima della deviazione standard della metrica. Questo viene calcolato utilizzando una tecnica di campionamento nota come "jackknifing". </p> <p>Questa metrica richiede molta memoria e non deve essere utilizzata nelle tabelle di grandi dimensioni. </p> <p>Per utilizzare questa sintassi, è necessario avere una dimensione del coltello jackcoltello (denominato "coltello jackcoltello") con le proprietà appropriate. Per ulteriori informazioni, contattate i servizi di consulenza Adobe. </p> <p>Esempio: confidence(Average_Score) </p> <p> <p>Nota:  I tipi di metriche di confidenza, tra cui quelle relative a confidence(metriche) e confidence(metriche,jacknife), sono particolarmente utili quando si utilizza la funzionalità di sperimentazione controllata di Adobe. Se una metrica passasse dal 12% al 16% durante un esperimento controllato, potreste usare un callout di confidenza per calcolare le probabilità che il salto fosse dovuto a una variazione casuale. Questo può aiutare a evitare di trarre conclusioni sbagliate da prove limitate, e, al contrario, fornire la garanzia che un cambiamento discutibile è effettivamente reale. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trust(metrica, coltello a giacca) </p> </td> 
   <td colname="col2"> <p>Una stima della deviazione standard della metrica. Questo viene calcolato utilizzando una tecnica di campionamento nota come "jackknifing". Questa sintassi consente di determinare la confidenza di una metrica utilizzando una dimensione del coltello jackcoltello denominata qualcosa di diverso dal "coltello jackcoltello". </p> <p>Questa metrica richiede molta memoria e non deve essere utilizzata nelle tabelle di grandi dimensioni. </p> <p>Per utilizzare questa sintassi, è necessario avere una dimensione del coltello jackcoltello (denominata qualcosa di diverso da "coltello jackcoltello") con le proprietà appropriate. Per ulteriori informazioni, contattate i servizi di consulenza Adobe. </p> <p>Esempio: confidence(Average_Score,SubSamples) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eval(CellReference) </p> </td> 
   <td colname="col2"> <p>Tratta il contenuto della cella a cui si fa riferimento come espressione metrica. Questa sintassi può essere utilizzata solo nella visualizzazione di un foglio di lavoro. </p> <p>Esempio: eval(B1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>log (B, X) </p> </td> 
   <td colname="col2"> <p>La funzione logaritmica matematica: La metrica X è il parametro, mentre la metrica B è la base. </p> <p>Esempio: dB = 20*log(Ampiezza,10) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metric[Filter] </p> </td> 
   <td colname="col2"> <p>"Metric where Filter": Una nuova metrica filtrata dal filtro specificato. </p> <p>Esempio: Jan_Sessions = Sessioni[ Month="Jan" ] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrica per dimensione </p> </td> 
   <td colname="col2"> <p>Una metrica valutata al "livello" della dimensione. Il risultato di (M by X)[F] (il risultato della metrica "M by X" valutata con il filtro "F") è il risultato di M[F by X] (il risultato della metrica "M" valutata con il filtro "F per X"). </p> <p>Esempio: AB_Visitors = </p> <p>(Visitatori per sessione)[Page="A" e Page="B"] = </p> <p>Visitatori[(Page="A" e Page="B") per sessione] = </p> <p>Il numero di visitatori che hanno visitato la pagina A e la pagina B nella stessa sessione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>number </p> </td> 
   <td colname="col2"> <p>Una metrica con un valore fisso. </p> <p>Esempio: Pi = 3,1415 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(Metric) </p> </td> 
   <td colname="col2"> <p>Ignora qualsiasi dimensione su cui viene valutata la metrica. La metrica ha lo stesso valore per ogni elemento di tale dimensione. </p> <p>Esempio: Pct_of_Visitors = Visitatori / totale(Visitatori) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>all(Metric) </p> </td> 
   <td colname="col2"> <p>Ignora i filtri applicati alla metrica. La metrica non viene modificata da selezioni e altri filtri. </p> <p>Esempio: Benchmark_Sessions = all( Sessioni ) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(all(Metric) </p> </td> 
   <td colname="col2"> <p>Ignora tutti i filtri e le dimensioni. Ha lo stesso valore in un determinato profilo, indipendentemente dai filtri o dalle dimensioni applicati. </p> <p>Esempio: Dataset_Visitors = total(all(Visitors)) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(One,Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>Una metrica che fornisce il conteggio di una dimensione numerabile come Visitatore o Sessione. </p> <p>Esempio: Visitatori = sum(Uno,Visitatore) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(Numeric_ Dimension, Countable_ Dimension) </p> </td> 
   <td colname="col2"> <p>Una metrica che fornisce la somma di una dimensione numerica su una dimensione numerabile. Vengono utilizzati i valori ordinali (al contrario dei valori formattati) degli elementi della dimensione numerica, pertanto un fattore di scala spesso deve essere applicato al risultato. </p> <p>Esempio: Valore = sum(Session_Value, Session)*0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>min(A, B) </p> </td> 
   <td colname="col2"> <p>I risultati minori della metrica A e della metrica B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>max(A, B) </p> </td> 
   <td colname="col2"> <p>Maggiore tra i risultati delle metriche A e B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>format(A, B) </p> </td> 
   <td colname="col2"> <p>Una metrica identica alla metrica A, ma utilizza la funzione di formattazione della metrica B. </p> </td> 
  </tr> 
 </tbody> 
</table>

