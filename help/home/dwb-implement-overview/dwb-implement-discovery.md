---
description: Raccogliere e descrivere le domande aziendali appropriate per il proprio ambiente di marketing durante l'implementazione di Workbench dati.
title: Individuazione e requisiti di Workbench dati
uuid: 436f0c32-b4e2-41dd-a8e9-531e0a195276
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# Individuazione e requisiti di Workbench dati{#data-workbench-discovery-and-requirements}

Raccogliere e descrivere le domande aziendali appropriate per il proprio ambiente di marketing durante l&#39;implementazione di Workbench dati.

Questa sezione consente di raccogliere informazioni sulle domande e sulle attività necessarie per sviluppare soluzioni in Workbench dati (DWB), in grado di risolvere tali questioni in modo accurato, chiaro e indipendente dalla tecnologia, fornendo riferimenti alla terminologia aziendale e alla soluzione Adobe Analytics Premium. Questa sezione fornisce informazioni su questi obiettivi e sui relativi requisiti.

## Fase 1: Obiettivi/obiettivi aziendali chiave {#section-bb8f3d6071bf48d9a546ac2b80341e1d}

Le tabelle riportate di seguito indicano come identificare la base clienti e analizzare la costruzione dell’implementazione DWB.

* Conoscenza della base cliente
* Informazioni su casi aziendali specifici (ad esempio, efficacia di Self-Service e altri canali di dati/origini dati offline)

**Conoscenza della base cliente**

Scopri perché i clienti utilizzano il tuo sito, quali sono le sfide da affrontare e in che modo DWB ti aiuterà in base al tuo modello di business. Ad esempio, come misurare, monitorare e analizzare i clienti per cross-selling di altri prodotti e servizi, ottenere l&#39;elenco degli utenti attivi e la penetrazione dell&#39;account e altri obiettivi.

| ID | Domanda/requisito aziendale | Priorità | Fase | Dipendenze |
|---|---|---|---|---|
| 1a | Questione specifica 1 | Alta/Media/Bassa | 1 | Chiave comune, a seconda di un&#39;altra chiave, ecc. |
| 1b | Domanda specifica sull&#39;impresa 2 | Alta | 1 | Qualsiasi dipendenza |

Costruzione analisi

<table id="table_6CA959E521964E27804BB2A65EC4BBDE"> 
 <tbody> 
  <tr> 
   <td colname="col1">Origini dati di Analysis Workspace</td> 
   <td colname="col2"> Aggiungi nome area di lavoro </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensioni e metriche dell'area di lavoro necessarie </p> </td> 
   <td colname="col2"> <p>Identifica dimensioni: </p> <p>Identifica metriche: </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtri, contrassegni e strumenti dell’area di lavoro richiesti </td> 
   <td colname="col2"> <p>Identifica segmenti: </p> <p>Identifica strumenti: </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Quali azioni possono essere derivate da tale analisi? </td> 
   <td colname="col2"> Comprendere le attività e il contenuto utilizzando aree di lavoro DWB specifiche. </td> 
  </tr> 
 </tbody> 
</table>

## Fase 2: Informazioni su casi aziendali specifici {#section-309d7ec6f631458c9c9e6bd2cef2fa4c}

Comprendi le altre origini dati e i canali e impara in che modo questi saranno correlati ai tuoi business case.

<table id="table_733CCD9F4E9048C2865758B8E8D027DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> Domande/requisiti aziendali </th> 
   <th colname="col3" class="entry"> Priorità </th> 
   <th colname="col04" class="entry"> Fase </th> 
   <th colname="col4" class="entry"> Dipendenze </th> 
   <th colname="col5" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2a </td> 
   <td colname="col2"> Requisiti specifici per le imprese 1 </td> 
   <td colname="col3"> <p>Alta/Media/Bassa </p> </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>Chiave comune, a seconda di un'altra chiave, contrassegno/identificatore account ecc. </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2b </td> 
   <td colname="col2"> <p>Requisito aziendale specifico 2 </p> </td> 
   <td colname="col3"> Alta/Media/Bassa </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>Qualsiasi dipendenza </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
 </tbody> 
</table>

**Progettazione analisi**

<table id="table_680C5D257CBF42519EFB8B96A00543C5"> 
 <tbody> 
  <tr> 
   <td colname="col1">Origini dati di Analysis Workspace
     </td> 
   <td colname="col2">
     Nome area di lavoro di esempio </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensioni e metriche dell'area di lavoro necessarie </p> </td> 
   <td colname="col2"> <p>Dimensioni: Definite le dimensioni richieste. </p> <p>Metriche: Definizione delle metriche necessarie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtri, contrassegni e strumenti dell’area di lavoro richiesti </td> 
   <td colname="col2"> <p>Segmenti: Identifica i segmenti di clienti. </p> <p>Strumenti: Selezionate gli strumenti richiesti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Quali azioni possono essere derivate da tale analisi? </td> 
   <td colname="col2"> Informazioni da acquisire da questa area di lavoro </td> 
  </tr> 
 </tbody> 
</table>

**Origini dati**

| Origini dati | Priorità | Con quale frequenza vengono ricevuti i dati? |
|---|---|---|
| Suite di rapporti Nome sito 1 (RSID) | 1 | Ogni ora |
| Nome del sito 2 (se presente) (RSID) | 1 | Ogni ora |
| Origine dati 1 (se applicabile) | 2 | Giornaliero? |
| Origine dati 2 (se applicabile) | 3 | Giornaliero? |
