---
description: Quando si crea un livello punto elemento che fa riferimento a un file di ricerca per ottenere dati di latitudine e longitudine, la posizione del punto viene ottenuta recuperando ogni elemento e la relativa latitudine e longitudine associate dal file di ricerca.
title: Definire i livelli dei punti di elemento che fanno riferimento ai file di ricerca
uuid: 32c8de7a-4316-4f91-9810-7f584bc7fb0b
exl-id: 2275fa8e-82fe-49e4-ab3e-91ec6ecb6233
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 3%

---

# Definire i livelli dei punti di elemento che fanno riferimento ai file di ricerca{#define-element-point-layers-referencing-lookup-files}

{{eol}}

Quando si crea un livello punto elemento che fa riferimento a un file di ricerca per ottenere dati di latitudine e longitudine, la posizione del punto viene ottenuta recuperando ogni elemento e la relativa latitudine e longitudine associate dal file di ricerca.

>[!NOTE]
>
>Invece di utilizzare un file di ricerca, puoi utilizzare la funzionalità Punti dinamici, che incorpora la latitudine e la longitudine di una posizione nel nome di ciascun elemento di una dimensione. Vedi [Definizione dei livelli del punto elemento utilizzando i punti dinamici](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#concept-51adc5e1df8a48e7bd7a582967e4c512).

Per definire un livello di punto elemento che fa riferimento a un file di ricerca, è necessario creare o disporre già dei seguenti elementi:

* **Una dimensione** definito in [!DNL Transformation.cfg file] o [!DNL transformation dataset include] file. Per informazioni sui file di configurazione della trasformazione, consulta la sezione *Guida alla configurazione del set di dati*.

* **Un file di ricerca** contenente i dati utilizzati per tracciare ciascun punto dati. Questo file deve contenere almeno tre colonne di dati per ogni punto dati: la chiave, la longitudine e la latitudine. Per ulteriori informazioni sul formato richiesto del file di ricerca, vedi [Formato del file livello del punto elemento](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2).

* **Un file di livello** che specifica la posizione del file di ricerca e identifica la dimensione e la metrica correlate, nonché i nomi delle colonne chiave, longitudine e latitudine nel file di ricerca. Per ulteriori informazioni sul formato richiesto del file di livello, vedi [Formato del file livello del punto elemento](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2).

   >[!NOTE]
   >
   >La [!DNL Zip Points.layer] file, fornito con [!DNL Geography] profile, è un livello punto elemento che identifica [!DNL Zipcode.dim] file, [!DNL Sessions.metric] file, [!DNL Zip Points.txt] file di ricerca e i nomi delle colonne chiave, longitudine, latitudine e nome nel file di ricerca.

## Formato del file di ricerca del punto elemento {#section-0bc8c652c1bd40eb84078f2af71a5c06}

Il file di ricerca a livello di punto elemento deve contenere almeno le tre colonne seguenti:

* **[!DNL Key]colonna:** Questa colonna deve contenere dati chiave comuni, che consentono al server Data Workbench di collegare i dati nel file di ricerca a quelli nel set di dati. La [!DNL key] deve essere la prima colonna del file di ricerca. Ogni riga in questa colonna identifica un elemento della dimensione.

* **[!DNL Longitude]colonna:** Questa colonna deve contenere la longitudine di ogni punto dati nel [!DNL Key] colonna.

* **[!DNL Latitude]colonna:** Questa colonna deve contenere la latitudine di ciascun punto dati nel [!DNL Key] colonna.

* **[!DNL Name]Colonna (facoltativo):** Se desideri specificare un nome da visualizzare sulla mappa per ogni punto dati, puoi includere una [!DNL Name] nel file di ricerca.

Ogni riga nel [!DNL Zip Points.txt] il file di ricerca contiene un codice ZIP nella prima colonna seguito da longitudine, latitudine e nome della città associato.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

## Formato del file del livello del punto elemento {#section-52d7e92be8354d979af9e7a2210b76f2}

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

<table id="table_7287F8869DD04886BE1477CBB11EB796"> 
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
   <td colname="col2"> <p>Il nome della colonna nel file di ricerca contenente i dati della chiave comune, che consente al server di Data Workbench di integrare i dati nel file di ricerca nel set di dati. Deve essere la prima colonna del file di ricerca. </p> <p>Ogni riga in questa colonna è un elemento di una dimensione. Questa dimensione deve essere definita nel <span class="filepath"> Transformation.cfg</span> file o <span class="wintitle"> set di dati di trasformazione include</span> e specificato nel parametro di Dimension di questo file. Per ulteriori informazioni sui file di configurazione della trasformazione, consulta la sezione <i>Guida alla configurazione del set di dati</i>. </p> </td> 
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
     <ul id="ul_F15E43B3BFE54CDD8026837027E25819"> 
      <li id="li_5405D939540E4D0FA7828D2623D72C44">Modalità di rendering 1. Le dimensioni dei punti sono definite nello spazio dello schermo (i punti rimangono costanti rispetto allo schermo del computer). I punti vengono sottoposti a rendering utilizzando i poligoni, quindi non esiste un limite superiore per le dimensioni dei punti. Questa è la modalità di rendering predefinita. </li> 
      <li id="li_61C5AA926777449E8804C7BCE9E46F9B">Modalità di rendering 2. La dimensione del punto è definita nello spazio del mondo (i punti rimangono costanti rispetto al globo). I punti vengono sottoposti a rendering utilizzando i poligoni, quindi non esiste un limite superiore per le dimensioni dei punti. </li> 
      <li id="li_C00527F959354D3BB7422EFFE1FB5135">Modalità di rendering 3. La dimensione del punto è definita nello spazio dello schermo. I punti vengono sottoposti a rendering utilizzando punti lisci OpenGL. </li> 
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
