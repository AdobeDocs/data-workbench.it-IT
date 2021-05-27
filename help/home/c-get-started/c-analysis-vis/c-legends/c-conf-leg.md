---
description: Le legende di affidabilità consentono di determinare la probabilità che i numeri visualizzati siano dovuti a una probabilità e di comprendere le possibili deviazioni nei dati.
title: Legende di affidabilità
uuid: 2559ff7c-6060-4fee-b509-9ae0c3912016
exl-id: 9aab169a-98b8-4e71-b74d-28e385c5c424
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 2%

---

# Legende di affidabilità{#confidence-legends}

Le legende di affidabilità consentono di determinare la probabilità che i numeri visualizzati siano dovuti a una probabilità e di comprendere le possibili deviazioni nei dati.

Anche se non si esegue il campionamento dei dati, non è possibile estrapolare i numeri da un periodo di tempo o un sottoinsieme specifico ad altri periodi o sottoinsiemi con piena affidabilità. La legenda di affidabilità consente di esplorare la probabilità che i numeri rientrino in un intervallo specifico.

Se pensate ai dati del mondo reale come a un grande esperimento, il mondo reale implica ancora il caso, anche quando si lavora con numeri esatti. Ad esempio, conoscere il numero di persone che hanno completato una transazione tra le 8.00 e le 12.00 di un martedì non significa che lo stesso numero esatto lo farà il martedì successivo.

La seguente legenda dell’affidabilità mostra i dettagli dell’affidabilità sulla metrica di conversione, mentre la tabella seguente fornisce ulteriori informazioni sul significato di ciascun punto dati.

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
   <td colname="col1"> <p>Metrica o formula </p> </td> 
   <td colname="col2"> <p>Nome della metrica o espressione metrica per la quale visualizzare le informazioni sull’affidabilità. Tutte le selezioni effettuate nell’area di lavoro vengono riportate nella legenda. In questo esempio vengono visualizzati i dettagli della metrica di conversione. </p> <p>Per informazioni sulle regole di sintassi per l'immissione di un'espressione, vedere <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f"> Sintassi della lingua della query</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valore misurato </p> </td> 
   <td colname="col2"> <p>Valore dei dati effettivi raccolti. In questo esempio, il tasso di conversione per la selezione corrente è del 2,3%. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Deviazione standard </p> </td> 
   <td colname="col2"> <p>La deviazione standard del valore misurato. In questo esempio, la deviazione standard del tasso di conversione per la selezione corrente è 0,1%. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Il valore "true" </p> </td> 
   <td colname="col2"> <p>La probabilità che il valore misurato rientri nell’intervallo elencato per ogni probabilità. In questo esempio, se questo "esperimento reale" fosse ripetuto più volte, si potrebbe essere sicuri al 90% che il Valore misurato sarebbe compreso tra 2,1% e 2,4%. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Quando si analizzano i risultati di qualsiasi calcolo, è necessario tenere conto delle seguenti avvertenze:
>* I numeri sono stime. Se ripeti gli stessi calcoli con un set di dati diverso, ottieni un risultato diverso. È nota come variazione casuale.
>* Le estrapolazioni a probabilità più elevate dipendono da un presupposto di normalità che non è corretto per tutte le metriche. Pertanto, i valori per la probabilità del 99% sono meno affidabili dei valori per la probabilità del 90%.

>
>
Se hai bisogno di numeri più esatti, consulta un esperto in statistiche.

## Modificare metriche o formule {#section-7f09ff84c3514f26b78d29294e1f03d9}

* Nella legenda di affidabilità, fai clic sul campo **[!UICONTROL Metric or Formula]** e digita la metrica o l’espressione desiderata. Per le regole di sintassi delle espressioni, vedere [Sintassi della lingua delle query](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f).

## Esportare in Microsoft Excel {#section-f36e2db7273740b7af278f8a2b79d564}

Per informazioni sull&#39;esportazione di finestre, vedere [Esportazione di dati di finestre](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
