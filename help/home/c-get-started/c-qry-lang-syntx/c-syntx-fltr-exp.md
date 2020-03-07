---
description: Un filtro è un'espressione che definisce un sottoinsieme di dati in un dataset.
solution: Analytics
title: Sintassi delle espressioni filtro
topic: Data workbench
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sintassi delle espressioni filtro{#syntax-for-filter-expressions}

Un filtro è un&#39;espressione che definisce un sottoinsieme di dati in un dataset.

Un filtro ammette o rifiuta ogni elemento di ciascuna dimensione in base alle relazioni tra le dimensioni.

I filtri possono essere modificati mediante l’ [!DNL Filter Editor]. Consultate [Filtra editor](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

Nella tabella seguente, ogni descrizione della sintassi include un esempio di espressione metrica che utilizza tale filtro. Ad esempio,[SessionsTrue] è una metrica definita utilizzando il filtro &quot;True&quot;. La metrica[SessionsTrue] è la stessa della metrica Sessions, perché il filtro True ammette ogni elemento della dimensione Session.

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>Filtro costante. Ammette ogni elemento di ogni dimensione </p> <p>Esempio: Sessioni[ True ] è uguale a Sessioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False </p> </td> 
   <td colname="col2"> <p>Filtro costante. Rifiuta ogni elemento di ogni dimensione. </p> <p>Esempio: Sessions[ False ] è sempre zero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>not Filter </p> </td> 
   <td colname="col2"> <p>Visualizza gli elementi rifiutati da Filter. </p> <p>Esempio: Sessioni[ not Page="A" ] indica il numero di sessioni che non hanno visitato la pagina A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA e FilterB </p> </td> 
   <td colname="col2"> <p>Ammette gli elementi consentiti da FilterA e FilterB. </p> <p>Esempio: Sessioni[ Page="A" e Page="B" ] indica il numero di sessioni che hanno visitato sia la pagina A che la pagina B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FiltroA o FiltroB </p> </td> 
   <td colname="col2"> <p>Ammette gli elementi consentiti da FilterA o FilterB. </p> <p>Esempio: Sessioni[ Page="A" o Page="B" ] indica il numero di sessioni che hanno visitato la pagina A, la pagina B o entrambi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtra per riduzione </p> </td> 
   <td colname="col2"> <p>Ammette l'insieme di elementi della dimensione Dim consentiti da Filter (Filtro). </p> <p>Esempio: Sessioni[ Page="/home" del visitatore ] indica il numero di sessioni appartenenti a un visitatore che ha visto la pagina "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identificatore </p> </td> 
   <td colname="col2"> <p>Filtri di riferimento altrimenti definiti nel profilo. </p> <p>Esempio: Sessioni[ Broken_Session_Filter ] indica il numero di sessioni ammesse dal filtro di sessione interrotta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Value" </p> </td> 
   <td colname="col2"> <p>Ammette l'elemento specificato della dimensione Dim. </p> <p>Esempio: Sessioni[ Page="A" ] indica il numero di sessioni che hanno visitato la pagina A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; "Value" </p> <p>Dim!= “Valore” </p> </td> 
   <td colname="col2"> <p>Consente di visualizzare ogni altro elemento della dimensione Dim. </p> <p>Esempio: Sessioni[ Pagina&lt;&gt;"A" ] indica il numero di sessioni che hanno visitato qualsiasi pagina diversa da A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim = #Ordinal </td> 
   <td colname="col2"> <p>Ammette l'elemento della dimensione Dim con il valore ordinale specificato. </p> <p>Esempio: Sessioni[ Mese=#0 ] indica il numero di sessioni nel primo mese del set di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; #Ordinal </p> <p>Dim!= #Ordinal </p> </td> 
   <td colname="col2"> <p>Consente di visualizzare ogni altro elemento della dimensione Dim. </p> <p>Esempio: Sessions[ Session_Value &lt;&gt; #0 ] indica il numero di sessioni con un valore di sessione diverso da zero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim corrisponde a "Expr" </p> </td> 
   <td colname="col2"> <p>Ammette gli elementi della dimensione Dim che corrispondono all'espressione regolare specificata. La fiamma non deve essere una dimensione normale o numerabile. </p> <p>Esempio: Sessions[ URI corrisponde a ".*/prodotto/.*" ] è il numero di sessioni che hanno visitato qualsiasi pagina in una directory di prodotto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim non corrisponde a "Expr" </p> </td> 
   <td colname="col2"> <p>Ammette gli elementi della dimensione Dim che non corrispondono all'espressione regolare specificata. La fiamma non deve essere una dimensione normale o numerabile. </p> <p>Esempio: Sessions[ URI non corrisponde a ".*\.jsp" ] è il numero di sessioni che hanno visitato qualsiasi pagina che non fosse una pagina JSP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt; "Value" </p> </td> 
   <td colname="col2"> <p>Ammette gli elementi della dimensione Dim con valori ordinali inferiori al valore ordinale dell'elemento "Value". Se "Valore" non è un elemento di dimensione, si presume che sia maggiore di qualsiasi elemento corrente della dimensione. </p> <p>Esempio: Sessioni[ Mese &lt; "Lug ‘04" ] indica il numero di sessioni che hanno avuto luogo prima di luglio 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &gt; "Value" </p> </td> 
   <td colname="col2"> <p>Ammette gli elementi della dimensione Dim con valori ordinali maggiori del valore ordinale dell'elemento "Value". Se "Valore" non è un elemento di dimensione, si presume che sia maggiore di qualsiasi elemento corrente della dimensione. </p> <p>Esempio: Sessioni[ Mese &gt; "Lug ‘04" ] indica il numero di sessioni che hanno avuto luogo dopo il luglio 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>Ammette gli elementi della dimensione Dim con valori ordinali inferiori o uguali al valore ordinale dell'elemento "Value". Se "Valore" non è un elemento di dimensione, si presume che sia maggiore di qualsiasi elemento corrente della dimensione. </p> <p>Esempio: Sessions[ Session_Number &lt;= "2" ] indica il numero di Sessioni che sono state la prima o la seconda sessione di un visitatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= "Value" </td> 
   <td colname="col2"> <p>Ammette gli elementi della dimensione Dim con valori ordinali superiori o uguali al valore ordinale dell'elemento "Value". Se "Valore" non è un elemento di dimensione, si presume che sia maggiore di qualsiasi elemento corrente della dimensione. </p> <p>Esempio: Sessions[ Session_Number &gt;= "5" ] indica il numero di sessioni che rappresentavano la quinta o più sessione per un visitatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>qualsiasi punto debole </p> </td> 
   <td colname="col2"> <p>Consente di visualizzare tutti gli elementi della dimensione Dim. </p> <p>Esempio: Sessions[ any Page_View ] indica il numero di sessioni con almeno una visualizzazione di pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>no Dim </p> </td> 
   <td colname="col2"> <p>Ammette gli elementi che qualsiasi elemento Dim rifiuta. </p> <p>Esempio: Sessioni[ no Page_View ] indica il numero di sessioni senza una visualizzazione pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(FILTRO) </p> </td> 
   <td colname="col2"> <p>come FILTER; utilizzato per raggruppare una parte di un'espressione di filtro. </p> </td> 
  </tr> 
 </tbody> 
</table>

