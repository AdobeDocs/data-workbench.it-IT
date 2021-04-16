---
description: Le metriche possono essere modificate utilizzando l’Editor metriche e salvate nella directory Metriche di un profilo.
title: Sintassi delle espressioni metriche
uuid: 801e265d-d7e4-4f0f-9698-d0b50dd00995
exl-id: 27d86fea-6500-4608-aadb-f39058fd3a6e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---

# Sintassi delle espressioni metriche{#syntax-for-metric-expressions}

Le metriche possono essere modificate utilizzando l’Editor metriche e salvate nella directory Metriche di un profilo.

Per ulteriori informazioni, consulta [Creazione e modifica di metriche derivate](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40). Le espressioni metriche possono essere utilizzate anche nei fogli di lavoro. Per ulteriori informazioni, vedere [Fogli di lavoro](../../../home/c-get-started/c-analysis-vis/c-wksts/c-wksts.md#concept-45b50aafc4d84709841f14aee8022581). La sintassi seguente viene utilizzata per definire le espressioni metriche.

Note:

1. Le parole sottolineate devono essere inserite letteralmente nel testo dell’espressione.
1. Il modulo `{TEXT}?` rappresenta un testo facoltativo.
1. Il modulo `{TEXT}*` rappresenta il testo che può verificarsi zero o più volte.
1. Il modulo `{A | B | C |...}` rappresenta il testo costituito esattamente da una delle opzioni specificate, ad esempio A o B o C....
1. Il modulo `[A,B)` rappresenta un intervallo di numeri, da A a B escluso.

<table id="table_A6CA9C9F396448209398AA2A369E63FA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identificatore </p> </td> 
   <td colname="col2"> <p>Un identificatore fa riferimento a una metrica denominata. Per le regole che disciplinano gli identificatori legali, consulta <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Sintassi per gli identificatori </a>. </p> <p>Esempio: Entrate = Total_Price </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Metrica) </p> </td> 
   <td colname="col2"> <p>Il risultato di (Metrica) è lo stesso del risultato di Metrica. Le parentesi specificano l’ordine delle operazioni in un’espressione. </p> <p>Esempio: Media = (A + B) / 2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A + B </p> </td> 
   <td colname="col2"> <p>Somma dei risultati delle metriche A e B. </p> <p>Esempio: Valore = Ricavo + Costo_Risparmio </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A - B </p> </td> 
   <td colname="col2"> <p>Differenza tra i risultati della metrica A e della metrica B. </p> <p>Esempio: Profitto = Ricavo - Costo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A * B </p> </td> 
   <td colname="col2"> <p>Prodotto dei risultati delle metriche A e B. </p> <p>Esempio: Dollari = centesimi * 0,01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A/B </p> </td> 
   <td colname="col2"> <p>Rapporto dei risultati della metrica A e della metrica B. </p> <p>Esempio: Revenue_per_Session = Revenue/Sessions </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A ^ B </p> </td> 
   <td colname="col2"> <p>Risultato della metrica A elevato alla potenza del risultato della metrica B. </p> <p>Esempio: Area = Larghezza^2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>affidabilità (metrica) </p> </td> 
   <td colname="col2"> <p>Una stima della deviazione standard della metrica. Questo viene calcolato utilizzando una tecnica di campionamento nota come jackknifing. </p> <p>Questa metrica richiede un uso intensivo della memoria e non deve essere utilizzata in tabelle di grandi dimensioni. </p> <p>Per utilizzare questa sintassi, devi disporre di una dimensione del coltello a giacca (nome "coltello a giacca") con le proprietà appropriate. Per ulteriori informazioni, contattare Adobe Consulting Services. </p> <p>Esempio: trust(Average_Score) </p> <p> <p>Nota:  I tipi di metriche di affidabilità, tra cui affidabilità(metrica) e affidabilità(metrica,jacknife), sono particolarmente utili quando si utilizza la funzionalità di sperimentazione controllata di Adobe. Se una metrica salta dal 12% al 16% durante un esperimento controllato, puoi utilizzare un callout di affidabilità per calcolare le probabilità che il salto sia dovuto a una variazione casuale. Questo può aiutarti ad evitare di trarre conclusioni sbagliate da prove limitate e, al contrario, a garantire che un cambiamento discutibile sia effettivamente reale. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>affidabilità(metrica, coltello a giacca) </p> </td> 
   <td colname="col2"> <p>Una stima della deviazione standard della metrica. Questo viene calcolato utilizzando una tecnica di campionamento nota come jackknifing. Questa sintassi consente di determinare l’affidabilità di una metrica utilizzando una dimensione del coltello a forma di jackcoltello denominata un elemento diverso da "coltello a giacca". </p> <p>Questa metrica richiede un uso intensivo della memoria e non deve essere utilizzata in tabelle di grandi dimensioni. </p> <p>Per utilizzare questa sintassi, è necessario disporre di una dimensione del coltello a giacca (denominato qualcosa di diverso da "coltello a giacca") con le proprietà appropriate. Per ulteriori informazioni, contattare Adobe Consulting Services. </p> <p>Esempio: trust(Average_Score,SubSamples) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eval(CellReference) </p> </td> 
   <td colname="col2"> <p>Tratta il contenuto della cella a cui si fa riferimento come espressione metrica. Questa sintassi può essere utilizzata solo nella visualizzazione di un foglio di lavoro. </p> <p>Esempio: eval(B1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>log (B, X) </p> </td> 
   <td colname="col2"> <p>La funzione logaritmo matematico: La metrica X è il parametro e la metrica B è la base. </p> <p>Esempio: dB = 20*log(Ampiezza, 10) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metric[Filter] </p> </td> 
   <td colname="col2"> <p>"Metrica con filtro": Una nuova metrica filtrata dal filtro specificato. </p> <p>Esempio: Jan_Sessions = Sessions[ Month="Jan" ] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrica per Dimension </p> </td> 
   <td colname="col2"> <p>Una metrica valutata al "livello" della dimensione. Il risultato di (M per X)[F] (il risultato della metrica "M per X" valutata con il filtro "F") è il risultato di M[F per X] (il risultato della metrica "M" valutata con il filtro "F per X"). </p> <p>Esempio: AB_Visitors = </p> <p>(Visitatori per sessione)[Page="A" e Page="B"] = </p> <p>Visitatori[(Page="A" e Page="B") per sessione] = </p> <p>Il numero di visitatori che hanno visitato la pagina A e la pagina B nella stessa sessione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>numero </p> </td> 
   <td colname="col2"> <p>Una metrica con un valore fisso. </p> <p>Esempio: Pi = 3,1415 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(Metric) </p> </td> 
   <td colname="col2"> <p>Ignora qualsiasi dimensione su cui viene valutata la metrica. La metrica ha lo stesso valore per ogni elemento di quella dimensione. </p> <p>Esempio: Pct_of_Visitors = Visitatori / totale(Visitatori) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>all(Metric) </p> </td> 
   <td colname="col2"> <p>Ignora i filtri applicati alla metrica. Le selezioni e gli altri filtri non influiscono sulla metrica. </p> <p>Esempio: Benchmark_Sessions = all( Sessions ) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(all(Metric)) </p> </td> 
   <td colname="col2"> <p>Ignora tutti i filtri e le dimensioni. Ha lo stesso valore in un dato profilo, indipendentemente da quali filtri o dimensioni vengono applicati. </p> <p>Esempio: Dataset_Visitors = total(all(Visitors)) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(One,Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>Una metrica che fornisce il conteggio di una dimensione numerabile, ad esempio Visitatore o Sessione. </p> <p>Esempio: Visitatori = sum(Uno,Visitatore) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(Numeric_ Dimension, Countable_ Dimension) </p> </td> 
   <td colname="col2"> <p>Una metrica che fornisce la somma di una dimensione numerica su una dimensione conteggiata. Vengono utilizzati i valori ordinali (anziché i valori formattati) degli elementi della dimensione numerica, pertanto è spesso necessario applicare un fattore di scala al risultato. </p> <p>Esempio: Valore = sum(Session_Value, Session)*0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>min(A, B) </p> </td> 
   <td colname="col2"> <p>I risultati minori delle metriche A e B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>max(A, B) </p> </td> 
   <td colname="col2"> <p>Maggiore è il risultato delle metriche A e B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>format(A, B) </p> </td> 
   <td colname="col2"> <p>Una metrica identica alla metrica A, ma utilizza la funzione di formattazione della metrica B. </p> </td> 
  </tr> 
 </tbody> 
</table>
