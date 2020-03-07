---
description: Come per altre trasformazioni, la trasformazione CrossRows viene applicata alle righe di dati (voci di registro) nelle origini di registro.
solution: Analytics
title: CrossRows
topic: Data workbench
uuid: 5910c150-6bec-4d98-b116-9b382fd54d3c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# CrossRows{#crossrows}

Come per altre trasformazioni, la trasformazione CrossRows viene applicata alle righe di dati (voci di registro) nelle origini di registro.

Per ogni riga di dati, la trasformazione prende il valore del campo di input specificato, esegue una serie di fasi di elaborazione e registra il risultato nel campo di output specificato. Tuttavia, quando la [!DNL CrossRows] trasformazione funziona su una riga di dati (questa riga è denominata riga di output), prende in considerazione la riga più una o più altre righe di dati (queste righe sono denominate righe di input) associate allo stesso ID di tracciamento. Pertanto, per un dato ID di tracciamento, il valore del campo di output per ciascuna riga di output è basato sui valori del campo di input per una o più righe di input.

La trasformazione fornisce più condizioni e vincoli che consentono di limitare le righe di input per la trasformazione. È possibile esprimere questi limiti in termini di condizioni del server workbench dati (vedere [Condizioni](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)), di un intervallo di righe di input relative alla riga di output o di un intervallo di volte rispetto al tempo della riga di output. Per le righe di input che soddisfano le condizioni e i vincoli della trasformazione, è possibile applicare un&#39;operazione (come SUM) che determina il valore del campo di output.

>[!NOTE]
>
>Per funzionare, la [!DNL CrossRows] trasformazione richiede che i dati siano ordinati nel tempo e raggruppati dall&#39;ID di tracciamento nei dati di origine. Pertanto, [!DNL CrossRows] funziona solo se definito nel [!DNL Transformation.cfg] file o in un [!DNL Transformation Dataset Include] file.

Durante la revisione delle descrizioni dei parametri nella tabella seguente, tenere presente quanto segue:

* La riga di output è la riga di dati su cui la trasformazione sta lavorando in un dato momento nel tempo.
* Le righe di input sono tutte le altre righe di dati (prima, dopo o inclusa la riga di output) i cui valori del campo di input fungono da input per la trasformazione. Le righe di input sono soggette ai parametri Condizione di input, Chiave, Inizio riga, Fine riga, Inizio ora e Fine ora.

<table id="table_152851484AFF4C50AF736DC62FAA43E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> impostazione predefinita </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commenti </td> 
   <td colname="col2"> Facoltativo. Note sulla trasformazione. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione </td> 
   <td colname="col2"> Limita l'output della trasformazione a determinate voci di registro. Se la condizione non è soddisfatta per una particolare voce di registro, il campo nel parametro Output viene lasciato invariato. L'input può ancora essere utilizzato per influenzare altre voci di registro. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresso </td> 
   <td colname="col2"> Nome del campo dalla riga di input da utilizzare come input. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione di ingresso </td> 
   <td colname="col2"> Accetta l'input per la trasformazione solo da determinate righe di input. Se la condizione di input non è soddisfatta per una particolare riga di input, il campo di input di tale riga viene ignorato e non influisce sulle altre righe di output. Tuttavia, il campo di output di tale riga viene ancora modificato in base alla condizione specificata. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chiave </td> 
   <td colname="col2"> <p>Facoltativo. Nome del campo da utilizzare come chiave. </p> <p> Se viene specificata una chiave, le righe di input per una data riga di output sono limitate al blocco contiguo di righe con lo stesso valore Key della riga di output. Questa restrizione è in aggiunta a tutte le altre limitazioni poste sulle righe di input da altri parametri della trasformazione <span class="wintitle"> CrossRows</span> . </p> <p> Ad esempio, se si lavora con dati Web e si imposta la chiave x-session del campo (con un valore univoco per ogni sessione), le righe di input per la trasformazione sono limitate alle righe con lo stesso valore x-session-key della riga di output. Pertanto, state considerando solo le righe di input che rappresentano le visualizzazioni di pagina che si verificano durante la stessa sessione della riga di output. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Funzionamento </td> 
   <td colname="col2"> <p>Operazione che, per ogni riga di output, viene applicata a tutte le righe di input che soddisfano tutte le condizioni definite dai parametri Condizione di input, Chiave, Inizio riga, Fine riga, Inizio ora e Fine ora per produrre un output: 
     <ul id="ul_C01CCF73A9544BCFB7B1105042FEF2DD"> 
      <li id="li_2D1A192970904499AB9F4431D51106D7"> ALL prende tutti i valori del campo di input dalle righe di input e li trasmette come vettore. </li> 
      <li id="li_B8863724AD924DE5BDBC987143548257"> SUM interpreta i valori del campo di input dalle righe di input come numeri e li somma. </li> 
      <li id="li_BF930069DCEA4E0B80893C3C06CAE100"> FIRST ROW produce il valore del campo di input dalla prima riga di input. </li> 
      <li id="li_04B9E2D88C0847E28101FC830C18D8E2"> LAST ROW produce il valore del campo di input dall'ultima riga di input. </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uscita </td> 
   <td colname="col2"> Nome del campo di output. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Inizio riga/Fine riga </td> 
   <td colname="col2"> <p>Facoltativo. Specifica un intervallo di righe di input relative alla riga di output. Ad esempio, il valore di Inizio riga "0" esclude tutte le righe prima della riga di output. Anche il valore iniziale di una riga pari a "1" esclude la riga di output. Gli intervalli comuni includono: 
     <ul id="ul_B030F32A5146430BA50DD4FAB4A527B0"> 
      <li id="li_30DFB8C0265349C295943A1CB8077B86"> Inizio 0: Questa riga e tutte le righe successive. </li> 
      <li id="li_9090C2E94E394351867BC5B78F27B41C"> Inizio 1: Tutte le righe successive. </li> 
      <li id="li_F870DC913E3F45BA94EE2EC04D344DE0"> Fine 0: Questa riga e tutte quelle precedenti. </li> 
      <li id="li_B8A576E419744D84AB1298E5155B583E"> Fine -1: Tutte le righe precedenti. </li> 
      <li id="li_CD2307A262D34542A2860FF07005CAD7"> Inizio -1, Fine -1: La riga precedente. </li> 
      <li id="li_6BF30B7BB7CC40A68B2332A3C11DD3B5"> Inizio 1, Fine 1: La riga successiva. </li> 
     </ul> </p> </td> 
   <td colname="col3"> Tutte le righe </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ora inizio/Ora fine </td> 
   <td colname="col2"> <p>Facoltativo. Specifica un intervallo di volte relativo al tempo della riga di output. Ad esempio, un Time End di 30 minuti include tutte le righe che si svolgono entro 30 minuti dopo la riga di output. Un'ora Inizio -30 minuti include tutte le righe che si svolgono entro 30 minuti prima della riga di output. </p> <p> Le unità di tempo disponibili sono giorni, settimane, ore, minuti, ms (millisecondi), ticks (100 nanosecondi) e ns (nanosecondi). </p> </td> 
   <td colname="col3"> Tutti i tempi </td> 
  </tr> 
 </tbody> 
</table>

La [!DNL CrossRows] trasformazione in questo esempio viene applicata alle righe di dati Web per cercare per ogni visualizzazione di pagina l’ora della visualizzazione di pagina successiva. Poiché sappiamo che [!DNL CrossRows] viene applicata solo durante la fase di trasformazione del processo di costruzione del set di dati, le righe di dati vengono ordinate dal visitatore (ogni visitatore ha un ID di tracciamento univoco) e dall&#39;ora.

Il campo di input, x-timestamp, è considerato solo per le righe di input in cui il campo x-is-page-view è popolato (il che indica che la riga di dati rappresenta una visualizzazione di pagina). Il campo x-session-key (con un valore univoco per ogni sessione) è specificato per il parametro Key. Pertanto, le righe di input (voci di registro) per la trasformazione sono limitate al blocco contiguo di righe con lo stesso valore di x-session-key della riga di output. In altre parole, per essere considerata per la trasformazione, una riga di input deve rappresentare una visualizzazione di pagina che si verifica durante la stessa sessione della visualizzazione di pagina nella riga di output. La prima operazione di riga prende il valore del campo di output dalla prima riga di input che soddisfa la [!DNL Input] condizione e ha lo stesso valore x-session-key della riga di output.

![](assets/cfg_TransformationType_CrossRows.png)

[!DNL CrossRows] viene eseguito in un periodo di tempo proporzionale alle dimensioni dei suoi input più le dimensioni dei suoi output. Ciò significa che per le operazioni SUM, FIRST ROW e LAST ROW, non è meno efficiente di altre trasformazioni. Per ALL, la situazione è più complessa perché è possibile configurare [!DNL CrossRows] l&#39;output di una quantità di dati per ogni riga di dati (voce di registro) proporzionale al numero totale di righe (voci di registro) per un dato ID di tracciamento.
