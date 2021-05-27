---
description: Data Workbench supporta sia le proiezioni di latitudine-longitudine che le proiezioni UTM (Universal Transverse Mercator) per tutte le sorgenti di livello immagine del terreno.
title: Specificare le informazioni di proiezione per le immagini del terreno
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
exl-id: 2638c5d4-164d-411b-8464-0a3af81b6537
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 3%

---

# Specificare le informazioni di proiezione per le immagini del terreno{#specify-projection-information-for-terrain-images}

Data Workbench supporta sia le proiezioni di latitudine-longitudine che le proiezioni UTM (Universal Transverse Mercator) per tutte le sorgenti di livello immagine del terreno.

Le informazioni di proiezione sono necessarie per le bitmap non proiettate e per le immagini generali, non proiettate. È possibile specificare le informazioni di proiezione per le immagini con informazioni di proiezione incorporate, anche se in genere non è necessario perché i parametri della proiezione sono determinati automaticamente dai dati geodetici incorporati nell&#39;immagine stessa. Le sezioni seguenti forniscono dettagli sulla specifica di questi formati di proiezione nel file [!DNL Terrain Images.cfg].

## Proiezioni di latitudine e longitudine {#section-6e335357ec28462ba39c565e0a5986c7}

Il formato di proiezione a latitudine e longitudine (LatLonProjection) nel file [!DNL Terrain Images.cfg] è definito da quattro parametri di latitudine e longitudine.

Per specificare un LatLonProjection per le immagini non proiettate (bitmap non proiettate e immagini generali, non proiettate), è possibile immettere le impostazioni per LatLonProjection nella finestra [!DNL Terrain Images.cfg] in Data Workbench.

Per specificare un LatLonProjection per le immagini con informazioni di proiezione incorporate, è necessario aprire il file [!DNL Terrain Images.cfg] in un editor di testo come Notepad, impostare il parametro Info proiezione su LatLonProjection e aggiungere le impostazioni per [!DNL LatLonProjection].

**Per specificare una proiezione LatLon per le immagini non proiettate**

1. Apri il file [!DNL Terrain Images.cfg] nella Data Workbench e aggiungi una sorgente di livello immagine del terreno come descritto in [Per definire un livello di immagine del terreno](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).
1. Modificate i parametri Info proiezione utilizzando la tabella dei parametri riportata di seguito come guida:

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
   <td colname="col2"> <p>La latitudine del bordo superiore dell'immagine, in gradi, dove 90 è il Polo Nord e -90 è il Polo Sud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>Latitudine del bordo inferiore dell'immagine. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>La longitudine del bordo sinistro dell'immagine, in gradi, dove i numeri positivi sono orientali e i numeri negativi sono longitudini occidentali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>La longitudine del bordo destro dell'immagine. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Salva il file facendo clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic su **[!UICONTROL Save]**.
1. Per salvare le modifiche apportate localmente al computer del server di Data Workbench, fare clic con il pulsante destro del mouse sul segno di spunta [!DNL Terrain Images.cfg] nella colonna [!DNL Temp], quindi fare clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.[!DNL Server Files Manager]

**Per specificare una proiezione LatLon per le immagini all&#39;interno di informazioni di proiezione incorporate**

In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. Il file [!DNL Terrain Images.cfg] si trova all&#39;interno di questa directory.

Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Terrain Images.cfg], quindi fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella colonna [!DNL Temp] per [!DNL Terrain Images.cfg].

Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il file [!DNL Terrain Images.cfg] viene visualizzato in una finestra Blocco note.

Modifica i parametri di Informazioni proiezione utilizzando come guida il seguente frammento di file di esempio. Assicurati di specificare il tipo di proiezione come evidenziato di seguito. Per una descrizione dei parametri, vedere la tabella Parametri LatLonProjection nella procedura precedente.

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## Proiezioni universali trasverse di Mercatore {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

La proiezione UWP (Universal Transverse Mercator) è definita da otto parametri. Quando si specifica una proiezione universale trasversa di Mercatore per un livello immagine del terreno, i file immagine del terreno devono essere allineati con falso (proiettato) a nord verso la parte superiore dell&#39;immagine e con falso a est verso destra dell&#39;immagine.

Per specificare una proiezione UTM per qualsiasi origine immagine del terreno, è necessario aprire il file [!DNL Terrain Images.cfg] in un editor di testo come Blocco note, impostare il parametro Info proiezione su &quot;TransverseMercatorProjection&quot; e aggiungere le impostazioni per la proiezione UTM.

**Per specificare una proiezione universale trasversa di Mercatore**

1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. Il file [!DNL Terrain Images.cfg] si trova all&#39;interno di questa directory.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Terrain Images.cfg], quindi fai clic su **[!UICONTROL Make Local]**. Un segno di spunta compare nella colonna [!DNL Temp] per [!DNL Terrain Images.cfg.]
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il file [!DNL Terrain Images.cfg] viene visualizzato in una finestra Blocco note.
1. Modifica i parametri di Informazioni proiezione utilizzando il frammento di file di esempio e la tabella dei parametri come guide. Assicurati di specificare il tipo di proiezione come evidenziato di seguito.

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
   <td colname="col1"> <p>Flattura inversa Ellipsoide, Asse semimajor Ellipsoide </p> </td> 
   <td colname="col2"> <p>I parametri dell'ellissoide utilizzati per la proiezione. L'asse del semimaio è specificato in metri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falso Digitale </p> </td> 
   <td colname="col2"> <p>Il falso digiuno del meridiano centrale della proiezione, in metri. Per l'UTM, questo è sempre 500.000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falso Normale </p> </td> 
   <td colname="col2"> <p>Il falso nord dell'equatore nella proiezione, in metri. Per l'UTM, questo è 0 per le zone dell'emisfero nord e 10.000 per le zone dell'emisfero sud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Coordinate angolo nord-ovest, coordinate angolo sud-est </p> </td> 
   <td colname="col2"> <p>Le coordinate (in metri proiettati) degli angoli in alto a sinistra e in basso a destra dell'immagine. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Meridiano </p> </td> 
   <td colname="col2"> <p>La longitudine del meridiano centrale della proiezione, specificata in gradi ad est di Greenwich. Per specificare i gradi a ovest è possibile utilizzare numeri negativi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fattore di scala </p> </td> 
   <td colname="col2"> <p>Rapporto tra il raggio del cilindro di proiezione e l'asse del semimaio dell'ellissoide. Per le proiezioni UWP (Universal Transverse Mercator), questo è sempre 0.9996. </p> </td> 
  </tr> 
 </tbody> 
</table>
