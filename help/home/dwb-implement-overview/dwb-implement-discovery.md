---
description: Raccogliere e descrivere le domande aziendali appropriate per il tuo ambiente di marketing durante l’implementazione di Data Workbench.
title: Individuazione e requisiti di Data Workbench
uuid: 436f0c32-b4e2-41dd-a8e9-531e0a195276
exl-id: 25cc2940-800a-4ad2-a7bb-c343e3d65500
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 8%

---

# Individuazione e requisiti di Data Workbench{#data-workbench-discovery-and-requirements}

{{eol}}

Raccogliere e descrivere le domande aziendali appropriate per il tuo ambiente di marketing durante l’implementazione di Data Workbench.

Questa sezione ti consente di raccogliere informazioni sulle domande e sui compiti necessari per sviluppare soluzioni in Data Workbench (DWB), in grado di risolvere queste domande con precisione, senza ambiguità e in modo indipendente dalla tecnologia, fornendo riferimenti alla terminologia aziendale e alla soluzione Adobe Analytics Premium. Questa sezione fornisce informazioni su questi obiettivi e sui relativi requisiti.

## Fase 1: Obiettivi/obiettivi aziendali chiave {#section-bb8f3d6071bf48d9a546ac2b80341e1d}

Le tabelle seguenti richiedono di identificare la base clienti e di analizzare la costruzione dell’implementazione DWB.

* Informazioni sulla base dati cliente
* Caso aziendale specifico (ad esempio, efficacia di Self-Service e di altri canali di dati/origini dati offline)

**Informazioni sulla base del cliente**

Scopri perché i clienti utilizzano il tuo sito, le sfide da affrontare e come DWB ti aiuterà in base al tuo modello di business. Ad esempio, come misurare, monitorare e analizzare i clienti per effettuare la cross-selling di altri prodotti e servizi, ottenere l’elenco degli utenti attivi e la penetrazione dell’account e altri obiettivi.

| ID | Domanda/requisiti aziendali | Priorità | Fase | Dipendenze |
|---|---|---|---|---|
| 1 bis | Questione commerciale specifica 1 | Alta/Media/Bassa | 1 | Chiave comune, dipendente da un&#39;altra chiave, ecc. |
| 1 ter | Questione commerciale specifica 2 | Alta | 1 | Qualsiasi dipendenza |

Costruzione analisi

<table id="table_6CA959E521964E27804BB2A65EC4BBDE"> 
 <tbody> 
  <tr> 
   <td colname="col1">Origine dati di Analysis Workspace</td> 
   <td colname="col2"> Aggiungi nome area di lavoro </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimension e metriche di Workspace necessari </p> </td> 
   <td colname="col2"> <p>Identifica Dimension: </p> <p>Identifica metriche: </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtri, flag e strumenti di Workspace necessari </td> 
   <td colname="col2"> <p>Identifica segmenti: </p> <p>Identifica strumenti: </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Quali azioni possono essere derivate da questa analisi? </td> 
   <td colname="col2"> Comprendere le attività e il contenuto utilizzando aree di lavoro DWB specifiche. </td> 
  </tr> 
 </tbody> 
</table>

## Fase 2: Informazioni su casi aziendali specifici {#section-309d7ec6f631458c9c9e6bd2cef2fa4c}

Comprendi altre origini dati e canali e scopri in che modo questi si relazioneranno ai tuoi casi aziendali.

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
   <td colname="col1"> 2 bis </td> 
   <td colname="col2"> Requisiti specifici per le imprese 1 </td> 
   <td colname="col3"> <p>Alta/Media/Bassa </p> </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>Chiave comune, a seconda di un'altra chiave, flag/identificatore account, ecc. </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 ter </td> 
   <td colname="col2"> <p>Requisito Commerciale Specifico 2 </p> </td> 
   <td colname="col3"> Alta/Media/Bassa </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>Qualsiasi dipendenza </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
 </tbody> 
</table>

**Costruzione di analisi**

<table id="table_680C5D257CBF42519EFB8B96A00543C5"> 
 <tbody> 
  <tr> 
   <td colname="col1">Origine dati di Analysis Workspace
     </td> 
   <td colname="col2">
     Nome area di lavoro di esempio </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimension e metriche di Workspace necessari </p> </td> 
   <td colname="col2"> <p>Dimension: Definisci le dimensioni richieste. </p> <p>Metriche: Definisci le metriche necessarie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtri, flag e strumenti di Workspace necessari </td> 
   <td colname="col2"> <p>Segmenti: Identifica i segmenti dei clienti. </p> <p>Strumenti: Seleziona gli strumenti necessari. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Quali azioni possono essere derivate da questa analisi? </td> 
   <td colname="col2"> Informazioni da questa area di lavoro </td> 
  </tr> 
 </tbody> 
</table>

**Origini dati**

| Origini dati | Priorità | Con quale frequenza vengono ricevuti i dati? |
|---|---|---|
| Suite di rapporti Nome sito 1 (RSID) | 1 | Oraria |
| Nome del sito 2 (se presente) (RSID) | 1 | Oraria |
| Origine dati 1 (se applicabile) | 2 | Giornaliero? |
| Origine dati 2 (se applicabile) | 3 | Giornaliero? |
