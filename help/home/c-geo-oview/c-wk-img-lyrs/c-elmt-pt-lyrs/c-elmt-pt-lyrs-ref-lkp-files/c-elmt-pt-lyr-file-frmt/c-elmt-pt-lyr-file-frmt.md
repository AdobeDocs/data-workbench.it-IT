---
description: Formattazione delle informazioni sul file di livello del punto elemento.
solution: Analytics
title: Formato file livello punto elemento
topic: Data workbench
uuid: a8b3d2f4-0ed2-480d-a2a6-75d43025a579
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Formato file livello punto elemento{#element-point-layer-file-format}

Formattazione delle informazioni sul file di livello del punto elemento.

Ogni file di livello punto elemento che fa riferimento a un file di ricerca deve essere formattato utilizzando il seguente modello: [!DNL .layer]

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
   <td colname="col1"> Colonna Longitudine </td> 
   <td colname="col2"> Il nome della colonna nel file di ricerca contenente i dati di longitudine. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonna Latitude </td> 
   <td colname="col2"> Il nome della colonna nel file di ricerca contenente i dati di latitudine. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonna Nome </td> 
   <td colname="col2"> Facoltativo. Il nome della colonna nel file di ricerca contenente i nomi delle posizioni rappresentate dai dati di latitudine e longitudine. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonna chiave </td> 
   <td colname="col2"> <p>Il nome della colonna nel file di ricerca contenente i dati chiave comuni, che consente al server workbench dati di integrare i dati nel file di ricerca nel dataset. Deve essere la prima colonna del file di ricerca. </p> <p>Ogni riga in questa colonna è un elemento di una dimensione. Questa dimensione deve essere definita nel file <span class="filepath"> Transformation.cfg</span> o in un set di dati di trasformazione includere file e specificata nel parametro Dimension di questo file. Per ulteriori informazioni sui file di configurazione della trasformazione, vedere la Guida alla configurazione del <i>set di dati</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensione </td> 
   <td colname="col2">Nome della dimensione (definita in un file di configurazione della trasformazione) contenente elementi che corrispondono alle righe di dati nella colonna <span class="wintitle"> Chiave</span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metrica </td> 
   <td colname="col2"> Nome della metrica valutata sulla dimensione specificata nel parametro Dimension. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scala </td> 
   <td colname="col2"> Facoltativo. Valore usato per ridimensionare i punti nel livello. Il valore predefinito è 100. Valori maggiori aumentano i punti e valori più bassi li rendono più piccoli. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colore </td> 
   <td colname="col2"> Facoltativo. Il vettore del colore RGB, espresso come (rosso, verde, blu). Per ogni colore del vettore, potete immettere un valore compreso tra 0,0 e 1,0. Ad esempio, (1.0, 0.0, 0.0) è rosso chiaro e (0.5, 0.5, 0.5) è grigio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modalità di rendering </td> 
   <td colname="col2"> <p>Facoltativo. Valore intero che rappresenta la modalità di rendering da utilizzare per il livello. Le tre modalità disponibili sono le seguenti: 
     <ul id="ul_CBB26B32505846A39FEB85E831E1C7AB"> 
      <li id="li_B31528A8858C4418ABCDFF0B4EFB25D7">Modalità di rendering 1. Le dimensioni dei punti sono definite nello spazio sullo schermo (i punti rimangono costanti rispetto allo schermo del computer). Il rendering dei punti viene eseguito utilizzando i poligoni, pertanto non esiste alcun limite superiore per la dimensione in punti. Questa è la modalità di rendering predefinita. </li> 
      <li id="li_CA0C3E0DBF004ADBB4D7819C0BF192FC">Modalità di rendering 2. La dimensione del punto è definita nello spazio del mondo (i punti rimangono una dimensione costante rispetto al globo). Il rendering dei punti viene eseguito utilizzando i poligoni, pertanto non esiste alcun limite superiore per la dimensione in punti. </li> 
      <li id="li_8F8729976DDB434D869E81D4381E2688">Modalità di rendering 3. La dimensione del punto è definita nello spazio sullo schermo. Il rendering dei punti viene eseguito utilizzando i punti morbidi OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Il [!DNL Zip Points.layer] file è formattato come segue:

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

