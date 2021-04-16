---
description: Quando crei un livello di punto elemento utilizzando punti dinamici, i dati di latitudine e longitudine vengono incorporati in ciascun elemento della dimensione.
title: Definire i livelli dei punti di elemento utilizzando i punti dinamici
uuid: f4b41969-329a-4c33-a8db-8d85597fa577
exl-id: 5f6e264c-5804-47fa-a3ca-8608a3f7e9d3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 5%

---

# Definire i livelli dei punti di elemento utilizzando i punti dinamici{#define-element-point-layers-using-dynamic-points}

Quando crei un livello di punto elemento utilizzando punti dinamici, i dati di latitudine e longitudine vengono incorporati in ciascun elemento della dimensione.

Per definire un livello di punto elemento utilizzando i punti dinamici, devi creare o disporre già dei seguenti elementi:

* Una dimensione, definita nel file [!DNL Transformation.cfg] o in un file [!DNL transformation dataset include], in cui ogni elemento contiene la stringa &quot;latitudine, longitudine&quot; o &quot;latitudine, longitudine, nome&quot;.

   Per i passaggi necessari per creare una dimensione, consulta la *Guida alla configurazione del set di dati*.

* File di livello che specifica la dimensione correlata.

Per ulteriori informazioni sul formato richiesto del file di livello, consulta [Formato del file di livello del punto elemento](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#section-0645fbc761c14bb986f3d6f02df407a0).

>[!NOTE]
>
>Quando utilizzi [!DNL Dynamic Points], è essenziale garantire che la cardinalità della dimensione specificata nel file di livello sia ragionevole. Se ogni riga di un set di dati ha una latitudine e una longitudine diverse, la dimensione si riempie rapidamente e la maggior parte delle righe cade in un elemento Small Elements. Poiché l’elemento Small Elements non ha una latitudine e una longitudine, non viene visualizzato sul globo.

## Formato del file del livello del punto elemento {#section-0645fbc761c14bb986f3d6f02df407a0}

Ogni file di livello del punto elemento che utilizza punti dinamici deve essere formattato utilizzando il seguente modello:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_8756BDCC49F447C0855BA64BC0078A0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensione </td> 
   <td colname="col2"> <p>Il nome della dimensione (definita in un file di configurazione della trasformazione), che deve contenere elementi con la stringa "latitudine, longitudine" o "latitudine, longitudine, nome", come mostrato negli esempi seguenti: 
     <ul id="ul_CC12F05459C640F5AB3C295932B04F83"> 
      <li id="li_9023CFA04A0F407E9DF0E1A4D71BB18C">37.5181,-77.1903 </li> 
      <li id="li_F002AB3AB98049A4AF1588B51167C7FA">35.3317,-77.8126,Da qualche parte </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metrica </td> 
   <td colname="col2"> Nome della metrica valutata sulla dimensione specificata nel parametro di Dimension. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Punti dinamici </td> 
   <td colname="col2"> Abilita i punti dinamici. Imposta su true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scala </td> 
   <td colname="col2"> Facoltativo. Valore utilizzato per ridimensionare i punti nel livello. Il valore predefinito è 100. Valori più grandi aumentano i punti e valori più piccoli li rendono più piccoli. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colore </td> 
   <td colname="col2"> Facoltativo. Il vettore del colore RGB, espresso come (rosso, verde, blu). Per ogni colore del vettore, è possibile immettere un valore compreso tra 0,0 e 1,0. Ad esempio, (1.0, 0.0, 0.0) è rosso chiaro e (0,5, 0,5, 0,5) è grigio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modalità di rendering </td> 
   <td colname="col2"> <p>Facoltativo. Valore intero che rappresenta la modalità di rendering da utilizzare per il livello. Le tre modalità disponibili sono le seguenti: 
     <ul id="ul_C7A74B9B085741C8B7116E4F110DF830"> 
      <li id="li_75CC2BE35C594B6895F743A1967A2E07">Modalità di rendering 1. Le dimensioni dei punti sono definite nello spazio dello schermo (i punti rimangono costanti rispetto allo schermo del computer). I punti vengono sottoposti a rendering utilizzando i poligoni, quindi non esiste un limite superiore per le dimensioni dei punti. Questa è la modalità di rendering predefinita. </li> 
      <li id="li_5B19C5B0F59548E28DCE7F7CD319E210">Modalità di rendering 2. La dimensione del punto è definita nello spazio del mondo (i punti rimangono costanti rispetto al globo). I punti vengono sottoposti a rendering utilizzando i poligoni, quindi non esiste un limite superiore per le dimensioni dei punti. </li> 
      <li id="li_DF0C9AEFE82642C9BD5AEA79770D2896">Modalità di rendering 3. La dimensione del punto è definita nello spazio dello schermo. I punti vengono sottoposti a rendering utilizzando punti lisci OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Il file [!DNL IP Coordinates.layer] viene formattato come segue:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```
