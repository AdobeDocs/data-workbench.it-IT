---
description: Le legende di confidenza consentono di determinare la probabilità che i numeri che si vedono siano dovuti alla probabilità e di comprendere le possibili deviazioni nei dati.
solution: Analytics
title: Leggi sulla fiducia
topic: Data workbench
uuid: 2559ff7c-6060-4fee-b509-9ae0c3912016
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Leggi sulla fiducia{#confidence-legends}

Le legende di confidenza consentono di determinare la probabilità che i numeri che si vedono siano dovuti alla probabilità e di comprendere le possibili deviazioni nei dati.

Anche se non si tratta di dati di campionamento, non è possibile estrapolare i numeri da un periodo di tempo specifico o da un sottoinsieme ad altri periodi di tempo o sottoinsiemi con la massima affidabilità. La legenda della confidenza consente di verificare la probabilità che i numeri rientrino in un intervallo particolare.

Se pensate ai dati del mondo reale come a un grande esperimento, il mondo reale implica ancora il caso, anche quando si lavora con numeri esatti. Ad esempio, conoscere il numero di persone che hanno completato una transazione tra le 8 di mattina e le 12 di martedì non significa che lo stesso numero esatto lo farà il martedì successivo.

La seguente legenda di attendibilità mostra i dettagli di confidenza sulla metrica Conversion (Conversione), mentre la tabella seguente fornisce ulteriori informazioni sul significato di ogni data point.

![](assets/lgd_ConfidenceLegend.png)

<table id="table_387F22C7EF4E4DE9AD810D3D9204676F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Metrica o Formula </p> </td> 
   <td colname="col2"> <p>Nome o espressione metrica della metrica per la quale si desidera visualizzare le informazioni sulla confidenza. Le selezioni effettuate nell’area di lavoro vengono riportate nella legenda. In questo esempio vengono visualizzati i dettagli sulla metrica Conversion (Conversione). </p> <p>Per informazioni sulle regole di sintassi per l'immissione di un'espressione, vedere <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f"> Sintassi</a>della lingua query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valore misurato </p> </td> 
   <td colname="col2"> <p>Il valore dei dati effettivi raccolti. In questo esempio, il tasso di conversione per la selezione corrente è 2,3%. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Deviazione standard </p> </td> 
   <td colname="col2"> <p>La deviazione standard del valore misurato. In questo esempio, la deviazione standard del tasso di conversione per la selezione corrente è 0,1%. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Il valore "true" </p> </td> 
   <td colname="col2"> <p>La probabilità che il valore misurato rientri nell’intervallo elencato per ciascuna probabilità. In questo esempio, se questo "esperimento del mondo reale" fosse ripetuto più volte, potreste essere sicuri al 90% che il Valore misurato sarebbe compreso tra 2,1% e 2,4%. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Quando si analizzano i risultati di qualsiasi calcolo, è necessario tenere conto dei seguenti accorgimenti: >
>* I numeri sono stime. Se si ripetono gli stessi calcoli con un set di dati diverso, si ottiene un risultato diverso. È nota come variazione casuale.
>* Le estrapolazioni a probabilità più elevate dipendono da un presupposto di normalità non corretto per tutte le metriche. Pertanto, i valori per la probabilità del 99% sono meno affidabili dei valori per la probabilità del 90%.
>
>
Se avete bisogno di più numeri esatti, dovreste consultare un esperto in statistica.

## Modifica di metriche o formule {#section-7f09ff84c3514f26b78d29294e1f03d9}

* Nella legenda Confidence, fare clic nel **[!UICONTROL Metric or Formula]** campo e digitare la metrica o l&#39;espressione desiderata. Per le regole di sintassi delle espressioni, vedere Sintassi [della lingua](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)query.

## Esporta in Microsoft Excel {#section-f36e2db7273740b7af278f8a2b79d564}

Per informazioni sull&#39;esportazione delle finestre, vedere [Esportazione dei dati](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)delle finestre.
