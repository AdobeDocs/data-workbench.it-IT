---
description: Formattazione delle informazioni sul file di livello del punto elemento.
title: Formato del file livello del punto elemento
uuid: a8b3d2f4-0ed2-480d-a2a6-75d43025a579
exl-id: 125796f6-a447-4f12-bcf2-3e669783cf1e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 5%

---

# Formato del file livello del punto elemento{#element-point-layer-file-format}

{{eol}}

Formattazione delle informazioni sul file di livello del punto elemento.

Ogni livello di punto elemento [!DNL .layer] il file che fa riferimento a un file di ricerca deve essere formattato utilizzando il seguente modello:

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Lookup File Name.txt
  Longitude Column = string: Longitude Column Name
  Latitude Column = string: Latitude Column Name
  Name Column = string: Location Column Name
  Key Column = string: Key Column Name
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_B2BC5FE8C80E4680B9A565878192D75B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Percorsi dati </td> 
   <td colname="col2"> Percorso del file di ricerca contenente dati di latitudine e longitudine. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonna a longitudine </td> 
   <td colname="col2"> Nome della colonna nel file di ricerca contenente i dati di longitudine. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonna Latitude </td> 
   <td colname="col2"> Nome della colonna nel file di ricerca contenente i dati di latitudine. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonna nome </td> 
   <td colname="col2"> Facoltativo. Nome della colonna nel file di ricerca contenente i nomi delle posizioni rappresentate dai dati di latitudine e longitudine. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonna chiave </td> 
   <td colname="col2"> <p>Il nome della colonna nel file di ricerca contenente i dati chiave comuni, che consente al server di Data Workbench di integrare i dati nel file di ricerca nel set di dati. Deve essere la prima colonna del file di ricerca. </p> <p>Ogni riga in questa colonna è un elemento di una dimensione. Questa dimensione deve essere definita nel <span class="filepath"> Transformation.cfg</span> file o set di dati di trasformazione includono file e specificato nel parametro di Dimension di questo file. Per ulteriori informazioni sui file di configurazione della trasformazione, consulta la sezione <i>Guida alla configurazione del set di dati</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensione </td> 
   <td colname="col2">Nome della dimensione (definita in un file di configurazione della trasformazione) contenente elementi corrispondenti alle righe di dati nel <span class="wintitle"> Chiave</span> colonna. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metrica </td> 
   <td colname="col2"> Nome della metrica valutata sulla dimensione specificata nel parametro di Dimension. </td> 
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
     <ul id="ul_CBB26B32505846A39FEB85E831E1C7AB"> 
      <li id="li_B31528A8858C4418ABCDFF0B4EFB25D7">Modalità di rendering 1. Le dimensioni dei punti sono definite nello spazio dello schermo (i punti rimangono costanti rispetto allo schermo del computer). I punti vengono sottoposti a rendering utilizzando i poligoni, quindi non esiste un limite superiore per le dimensioni dei punti. Questa è la modalità di rendering predefinita. </li> 
      <li id="li_CA0C3E0DBF004ADBB4D7819C0BF192FC">Modalità di rendering 2. La dimensione del punto è definita nello spazio del mondo (i punti rimangono costanti rispetto al globo). I punti vengono sottoposti a rendering utilizzando i poligoni, quindi non esiste un limite superiore per le dimensioni dei punti. </li> 
      <li id="li_8F8729976DDB434D869E81D4381E2688">Modalità di rendering 3. La dimensione del punto è definita nello spazio dello schermo. I punti vengono sottoposti a rendering utilizzando punti lisci OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

La [!DNL Zip Points.layer] file formattato come segue:

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Zip Points.txt
  Longitude Column = string: LONGITUDE
  Latitude Column = string: LATITUDE
  Name Column = string: NAME
  Key Column = string: ZIP_CODE
  Dimension = ref: wdata/model/dim/Zipcode
  Metric = ref: wdata/model/metric/Sessions
```
