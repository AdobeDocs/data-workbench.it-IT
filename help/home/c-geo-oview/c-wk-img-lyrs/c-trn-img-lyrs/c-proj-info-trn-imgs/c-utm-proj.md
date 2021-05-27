---
description: La proiezione UWP (Universal Transverse Mercator) è definita da otto parametri.
title: Proiezioni universali trasverse di Mercatore
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
exl-id: 7d7610c3-14e7-474e-b792-ad413c86a2ef
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# Proiezioni universali trasverse di Mercatore{#universal-transverse-mercator-projections}

La proiezione UWP (Universal Transverse Mercator) è definita da otto parametri.

Quando si specifica una proiezione universale trasversa di Mercatore per un livello immagine del terreno, i file immagine del terreno devono essere allineati con falso (proiettato) a nord verso la parte superiore dell&#39;immagine e con falso a est verso destra dell&#39;immagine.

Per specificare una proiezione UTM per qualsiasi origine immagine del terreno, è necessario aprire il file [!DNL Terrain Images.cfg] in un editor di testo come Blocco note, impostare il parametro Info proiezione su &quot;TransverseMercatorProjection&quot; e aggiungere le impostazioni per la proiezione UTM.

**Per specificare una proiezione universale trasversa di Mercatore**

1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. Il file [!DNL Terrain Images.cfg] si trova all&#39;interno di questa directory.

1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* per [!DNL Terrain Images.cfg], quindi fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella colonna [!DNL Temp] per [!DNL Terrain Images.cfg].

1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il file [!DNL Terrain Images.cfg]viene visualizzato in una finestra Blocco note.

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

| Parametro | Descrizione |
|---|---|
| Flattura inversa Ellipsoide, Asse semimajor Ellipsoide | I parametri dell&#39;ellissoide utilizzati per la proiezione. L&#39;asse del semimaio è specificato in metri. |
| Falso Digitale | Il falso digiuno del meridiano centrale della proiezione, in metri. Per l&#39;UTM, questo è sempre 500.000. |
| Falso Normale | Il falso nord dell&#39;equatore nella proiezione, in metri. Per l&#39;UTM, questo è 0 per le zone dell&#39;emisfero nord e 10.000 per le zone dell&#39;emisfero sud. |
| Coordinate angolo nord-ovest, coordinate angolo sud-est | Le coordinate (in metri proiettati) degli angoli in alto a sinistra e in basso a destra dell&#39;immagine. |
| Meridiano | La longitudine del meridiano centrale della proiezione, specificata in gradi ad est di Greenwich. Per specificare i gradi a ovest è possibile utilizzare numeri negativi. |
| Fattore di scala | Rapporto tra il raggio del cilindro di proiezione e l&#39;asse del semimaio dell&#39;ellissoide. Per le proiezioni UWP (Universal Transverse Mercator), questo è sempre 0.9996. |
