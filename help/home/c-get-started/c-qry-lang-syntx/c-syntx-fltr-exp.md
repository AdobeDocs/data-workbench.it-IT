---
description: Un filtro è un’espressione che definisce un sottoinsieme di dati in un set di dati.
title: Sintassi delle espressioni filtro
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
exl-id: 515c1645-69c8-4990-a913-d2d505c6fe51
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 1%

---

# Sintassi delle espressioni filtro{#syntax-for-filter-expressions}

Un filtro è un’espressione che definisce un sottoinsieme di dati in un set di dati.

Un filtro ammette o rifiuta ogni elemento di ciascuna dimensione in base alle relazioni tra le dimensioni.

I filtri possono essere modificati utilizzando [!DNL Filter Editor]. Consulta [Editor filtri](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

Nella tabella seguente, ogni descrizione della sintassi include un esempio di espressione metrica che utilizza tale filtro. Ad esempio, Sessions[True] è una metrica definita utilizzando il filtro &quot;True&quot;. La metrica Sessions[True] è la stessa della metrica Sessions, perché il filtro True ammette ogni elemento della dimensione Session.

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>Filtro costante. Ammette ogni elemento di ogni dimensione </p> <p>Esempio: Sessions[ True ] è uguale a Sessions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False </p> </td> 
   <td colname="col2"> <p>Filtro costante. Rifiuta ogni elemento di ogni dimensione. </p> <p>Esempio: Sessions[ False ] è sempre zero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>filtro non valido </p> </td> 
   <td colname="col2"> <p>Consente gli elementi rifiutati da Filter. </p> <p>Esempio: Sessions[ not Page="A" ] è il numero di sessioni che non hanno visitato la pagina A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FiltroA e FiltroB </p> </td> 
   <td colname="col2"> <p>Consente gli elementi ammessi da FilterA e FilterB. </p> <p>Esempio: Sessions[ Page="A" e Page="B" ] è il numero di sessioni che hanno visitato sia la pagina A che la pagina B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FiltroA o FiltroB </p> </td> 
   <td colname="col2"> <p>Consente gli elementi ammessi da FilterA o FilterB. </p> <p>Esempio: Sessions[ Page="A" o Page="B" ] è il numero di sessioni che hanno visitato la pagina A, la pagina B o entrambe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtra per attenuazione </p> </td> 
   <td colname="col2"> <p>Ammette l’insieme di elementi della dimensione Dim ammessi da Filtro. </p> <p>Esempio: Sessions[ Page="/home" by Visitor ] è il numero di sessioni appartenenti a un visitatore che ha visto la pagina "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identificatore </p> </td> 
   <td colname="col2"> <p>Filtri di riferimento definiti in altro modo nel profilo . </p> <p>Esempio: Sessions[ Broken_Session_Filter ] è il numero di sessioni ammesse dal filtro sessioni interrotte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Value" </p> </td> 
   <td colname="col2"> <p>Ammette l’elemento specificato della dimensione Dim. </p> <p>Esempio: Sessions[ Page="A" ] è il numero di sessioni che hanno visitato la pagina A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; "Value" </p> <p>Dim!= “Valore” </p> </td> 
   <td colname="col2"> <p>Ammette ogni altro elemento della dimensione Dim. </p> <p>Esempio: Sessions[ Page&lt;&gt;"A" ] è il numero di sessioni che hanno visitato una pagina diversa da A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim = #Ordinal </td> 
   <td colname="col2"> <p>Ammette l’elemento della dimensione Dim con il valore ordinale specificato. </p> <p>Esempio: Sessions[ Month=#0 ] è il numero di sessioni nel primo mese del set di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; #Ordinal </p> <p>Dim!= #Ordinal </p> </td> 
   <td colname="col2"> <p>Ammette ogni altro elemento della dimensione Dim. </p> <p>Esempio: Sessions[ Session_Value &lt;&gt; #0 ] è il numero di sessioni con un valore di sessione diverso da zero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim corrisponde a "Expr" </p> </td> 
   <td colname="col2"> <p>Ammette gli elementi della dimensione Dim che corrispondono all’espressione regolare specificata. L'attenuazione non deve essere una dimensione normale o conteggiata. </p> <p>Esempio: Sessions[ URI corrisponde a ".*/prodotto/.*" ] è il numero di sessioni che hanno visitato qualsiasi pagina in una directory di prodotto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim non corrisponde a "Expr" </p> </td> 
   <td colname="col2"> <p>Ammette gli elementi della dimensione Dim che non corrispondono all'espressione regolare specificata. L'attenuazione non deve essere una dimensione normale o conteggiata. </p> <p>Esempio: Sessions[ URI non corrisponde a ".*\.jsp" ] è il numero di sessioni che hanno visitato qualsiasi pagina che non era una pagina JSP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt; "Value" </p> </td> 
   <td colname="col2"> <p>Ammette gli elementi della dimensione Dim con valori ordinali inferiori al valore ordinale dell'elemento "Value". Se "Valore" non è un elemento di dimensione, si presume che sia maggiore di qualsiasi elemento corrente della dimensione. </p> <p>Esempio: Sessions[ Month &lt; "Jul ‘04" ] è il numero di sessioni precedenti al luglio 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &gt; "Value" </p> </td> 
   <td colname="col2"> <p>Ammette gli elementi della dimensione Dim con valori ordinali maggiori del valore ordinale dell'elemento "Value". Se "Valore" non è un elemento di dimensione, si presume che sia maggiore di qualsiasi elemento corrente della dimensione. </p> <p>Esempio: Sessions[ Month &gt; "Jul ‘04" ] è il numero di sessioni che hanno avuto luogo dopo il luglio 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>Ammette gli elementi della dimensione Dim con valori ordinali inferiori o uguali al valore ordinale dell'elemento "Value". Se "Valore" non è un elemento di dimensione, si presume che sia maggiore di qualsiasi elemento corrente della dimensione. </p> <p>Esempio: Sessions[ Session_Number &lt;= "2" ] è il numero di sessioni che sono state la prima o la seconda sessione di un visitatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= "Value" </td> 
   <td colname="col2"> <p>Ammette gli elementi della dimensione Dim con valori ordinali maggiori o uguali al valore ordinale dell'elemento "Value". Se "Valore" non è un elemento di dimensione, si presume che sia maggiore di qualsiasi elemento corrente della dimensione. </p> <p>Esempio: Sessions[ Session_Number &gt;= "5" ] è il numero di sessioni che erano la quinta o più sessione per un visitatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>qualsiasi attenuazione </p> </td> 
   <td colname="col2"> <p>Ammette tutti gli elementi della dimensione Dim. </p> <p>Esempio: Sessions[ any Page_View ] è il numero di sessioni con almeno una visualizzazione di pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>no Dim </p> </td> 
   <td colname="col2"> <p>Ammette elementi che qualsiasi Dim rifiuta. </p> <p>Esempio: Sessions[ no Page_View ] è il numero di sessioni senza una visualizzazione di pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(FILTRO) </p> </td> 
   <td colname="col2"> <p>come FILTRO; utilizzato per raggruppare una parte di un'espressione di filtro. </p> </td> 
  </tr> 
 </tbody> 
</table>
