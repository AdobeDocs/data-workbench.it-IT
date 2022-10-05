---
description: La Legenda di elaborazione fornisce informazioni dettagliate sull’elaborazione e la trasformazione dei dati di un particolare server, consentendoti di tenere traccia dell’avanzamento dei dati in fase di rielaborazione e di ritrasformazione.
title: Legenda di elaborazione
uuid: 6c082c8f-fbb3-4e48-a249-2a13345fda86
exl-id: a83ce514-c92b-4cf8-a3cc-bff4e2ba63f1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 1%

---

# Legenda di elaborazione{#processing-legend}

{{eol}}

La Legenda di elaborazione fornisce informazioni dettagliate sull’elaborazione e la trasformazione dei dati di un particolare server, consentendoti di tenere traccia dell’avanzamento dei dati in fase di rielaborazione e di ritrasformazione.

![](assets/vis_ProcessingLegend.png)

Nella tabella seguente sono elencate le attività che possono essere completate utilizzando [!DNL Processing Legend].

<table id="table_6149250C44B14C44A3CB1CEF68B280C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per eseguire questa operazione.. </th> 
   <th colname="col2" class="entry"> Fai questo... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Visualizzazione della dimensione totale di tutti i dati </p> </td> 
   <td colname="col2"> <p>Esamina i valori nella <span class="wintitle"> Totale voci di registro</span> e <span class="wintitle"> Totale byte di registro</span> campi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per verificare se il filtro funziona </p> </td> 
   <td colname="col2"> <p>Esamina i valori nella <span class="wintitle"> Totale voci di registro filtrate</span> campi. Se il valore è 0, il filtro non funziona e devi controllare la configurazione per risolvere il problema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per verificare l’avanzamento dell’elaborazione del registro </p> </td> 
   <td colname="col2"> <p>Rivedi il valore nel <span class="wintitle"> Avanzamento dell’elaborazione del registro</span> campo . Questa percentuale indica la quantità di rielaborazione completata. </p> <p>Durante la rielaborazione per perfezionare il set di dati, potresti voler controllare il numero di <span class="wintitle"> Totale voci di registro decodificate</span> rispetto al numero di <span class="wintitle"> Totale voci di registro filtrate</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per verificare il progresso della trasformazione </p> </td> 
   <td colname="col2"> <p>Rivedi il valore nel <span class="wintitle"> Avanzamento trasformazione</span> campo . Questa percentuale indica la quantità di trasformazione completata. </p> </td> 
  </tr> 
 </tbody> 
</table>
