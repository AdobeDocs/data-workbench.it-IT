---
description: Il workbench dati supporta sia le proiezioni di latitudine-longitudine che le proiezioni UWP (Universal Transverse Mercator) per tutte le sorgenti di livello immagine del terreno.
solution: Analytics
title: Specificare le informazioni di proiezione per le immagini del terreno
topic: Data workbench
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Specificare le informazioni di proiezione per le immagini del terreno{#specify-projection-information-for-terrain-images}

Il workbench dati supporta sia le proiezioni di latitudine-longitudine che le proiezioni UWP (Universal Transverse Mercator) per tutte le sorgenti di livello immagine del terreno.

Le informazioni sulla proiezione sono necessarie per immagini bitmap non proiettate e per immagini generali, non proiettate. È possibile specificare le informazioni di proiezione per le immagini con informazioni di proiezione incorporate, anche se in genere non sono necessarie perché i parametri della proiezione sono determinati automaticamente dai dati geodetici incorporati nell&#39;immagine stessa. Le sezioni seguenti forniscono dettagli sulla specifica di questi formati di proiezione nel [!DNL Terrain Images.cfg] file.

## Proiezioni Latitudine-Longitudine {#section-6e335357ec28462ba39c565e0a5986c7}

Il formato di proiezione latitudine-longitudine (LatLonProjection) nel [!DNL Terrain Images.cfg] file è definito da quattro parametri per latitudine e longitudine.

Per specificare un LatLonProjection per le immagini non proiettate (immagini bitmap non proiettate e immagini generali, non proiettate), è possibile immettere le impostazioni per LatLonProjection nella [!DNL Terrain Images.cfg] finestra di Workbench dati.

Per specificare un LatLonProjection per le immagini con informazioni di proiezione incorporate, è necessario aprire il [!DNL Terrain Images.cfg] file in un editor di testo come Notepad, impostare il parametro Informazioni proiezione su LatLonProjection e aggiungere le impostazioni per il [!DNL LatLonProjection].

**Per specificare una proiezione LatLon per immagini non proiettate**

1. Aprire il [!DNL Terrain Images.cfg] file in Workbench dati e aggiungere un&#39;origine del livello immagine del terreno come descritto in [Per definire un livello](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f)immagine del terreno.
1. Modificate i parametri Informazioni proiezione utilizzando come guida la seguente tabella di parametri:

<table id="table_32F6EADB2DA34592ABD6FFAC9E00BB27"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lat0 </p> </td> 
   <td colname="col2"> <p>Latitudine del bordo superiore dell'immagine, in gradi, dove 90 corrisponde al Polo Nord e -90 al Polo Sud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>Latitudine del bordo inferiore dell’immagine. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>La longitudine del bordo sinistro dell'immagine, in gradi, dove i numeri positivi sono orientali e i numeri negativi sono longitudini occidentali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>Longitudine del bordo destro dell’immagine. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Salvare il file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic su **[!UICONTROL Save]**.
1. Per salvare le modifiche apportate localmente al computer del server Workbench dati, fare clic con il pulsante destro del mouse sul segno di spunta [!DNL Server Files Manager]nella [!DNL Terrain Images.cfg] colonna, quindi scegliere [!DNL Temp] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

**Per specificare un LatLonProjection per le immagini all&#39;interno di informazioni di proiezione incorporate**

Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL Terrain Images.cfg] file si trova all&#39;interno di questa directory.

Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Terrain Images.cfg], quindi scegliere **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Terrain Images.cfg].

Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il [!DNL Terrain Images.cfg] file viene visualizzato in una finestra Blocco note.

Modificate i parametri Informazioni proiezione utilizzando come guida il seguente frammento di file di esempio. Accertatevi di specificare il tipo di proiezione come evidenziato di seguito. Per una descrizione dei parametri, vedere la tabella Parametri LatLonProjection nella procedura precedente.

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## Proiezioni Mercatore Trasversale Universale {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

La proiezione Universal Transverse Mercator (UTM) è definita da otto parametri. Quando specificate una proiezione Universal Transverse Mercator per un livello di immagine del terreno, i file immagine del terreno devono essere allineati con false (proiettate) a nord verso la parte superiore dell’immagine e con false a est verso destra dell’immagine.

Per specificare una proiezione UTM per qualsiasi origine immagine del terreno, è necessario aprire il [!DNL Terrain Images.cfg] file in un editor di testo come Blocco note, impostare il parametro Projection Info su &quot;TransverseMercatorProjection&quot; e aggiungere le impostazioni per la proiezione UTM.

**Per specificare una proiezione di Mercatore trasversale universale**

1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL Terrain Images.cfg] file si trova all&#39;interno di questa directory.
1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Terrain Images.cfg], quindi scegliere **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Terrain Images.cfg.]
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il [!DNL Terrain Images.cfg] file viene visualizzato in una finestra Blocco note.
1. Modificate i parametri Informazioni proiezione utilizzando come guide il seguente frammento di file di esempio e la tabella dei parametri. Accertatevi di specificare il tipo di proiezione come evidenziato di seguito.

   ```
   Projection Info = TransverseMercatorProjection:
     Ellipsoid Inverse Flattening = double: 294.9786982139006
     Ellipsoid Semimajor Axis = double: 6378206.4000000004
     False Easting = double: 500000
     False Northing = double: 0
     Northwest Corner Coordinates = v3d: (550339, 5.42059e+006, 0)
     Prime Meridian = double: -123
     Scale Factor = double: 0.9996
     Southeast Corner Coordinates = v3d: (555099, 5.41356e+006, 0)
   ```

<table id="table_71AEEAE808B9436B9846987A54D5D1D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ellipsoide Inverse Flattening, Ellipsoid Semimajor Axis </p> </td> 
   <td colname="col2"> <p>I parametri dell'ellissi utilizzati per la proiezione. L'asse del semimajor è specificato in metri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falso dietetico </p> </td> 
   <td colname="col2"> <p>Il falso spreco del meridiano centrale della proiezione, in metri. Per l'UTM, questo è sempre 500.000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falso Normale </p> </td> 
   <td colname="col2"> <p>La falsa nordazione dell'equatore nella proiezione, in metri. Per l'UTM, questo è 0 per le zone dell'emisfero nord e 10.000 per le zone dell'emisfero sud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Coordinate Angolo Nord-Ovest, Coordinate Angolo Sud-Est </p> </td> 
   <td colname="col2"> <p>Le coordinate (in metri proiettati) degli angoli in alto a sinistra e in basso a destra dell’immagine. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Meridiano </p> </td> 
   <td colname="col2"> <p>La longitudine del meridiano centrale della proiezione, specificata in gradi ad est di Greenwich. I numeri negativi possono essere utilizzati per specificare i gradi a ovest. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fattore di scala </p> </td> 
   <td colname="col2"> <p>Rapporto tra il raggio del cilindro di proiezione e l'asse del semimajor dell'ellissoide. Per le proiezioni UWP (Universal Transverse Mercator), questo è sempre 0,9996. </p> </td> 
  </tr> 
 </tbody> 
</table>

