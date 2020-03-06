---
description: La proiezione Universal Transverse Mercator (UTM) è definita da otto parametri.
solution: Analytics
title: Proiezioni Mercatore Trasversale Universale
topic: Data workbench
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Proiezioni Mercatore Trasversale Universale{#universal-transverse-mercator-projections}

La proiezione Universal Transverse Mercator (UTM) è definita da otto parametri.

Quando specificate una proiezione Universal Transverse Mercator per un livello di immagine del terreno, i file immagine del terreno devono essere allineati con false (proiettate) a nord verso la parte superiore dell’immagine e con false a est verso destra dell’immagine.

Per specificare una proiezione UTM per qualsiasi origine immagine del terreno, è necessario aprire il [!DNL Terrain Images.cfg] file in un editor di testo come Blocco note, impostare il parametro Projection Info su &quot;TransverseMercatorProjection&quot; e aggiungere le impostazioni per la proiezione UTM.

**Per specificare una proiezione di Mercatore trasversale universale**

1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL Terrain Images.cfg] file si trova all&#39;interno di questa directory.

1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server per [!DNL Terrain Images.cfg], quindi fare clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Terrain Images.cfg].

1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il [!DNL Terrain Images.cfg]file viene visualizzato in una finestra Blocco note.

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

| Parametro | Descrizione |
|---|---|
| Ellipsoide Inverse Flattening, Ellipsoid Semimajor Axis | I parametri dell&#39;ellissi utilizzati per la proiezione. L&#39;asse del semimajor è specificato in metri. |
| Falso dietetico | Il falso spreco del meridiano centrale della proiezione, in metri. Per l&#39;UTM, questo è sempre 500.000. |
| Falso Normale | La falsa nordazione dell&#39;equatore nella proiezione, in metri. Per l&#39;UTM, questo è 0 per le zone dell&#39;emisfero nord e 10.000 per le zone dell&#39;emisfero sud. |
| Coordinate Angolo Nord-Ovest, Coordinate Angolo Sud-Est | Le coordinate (in metri proiettati) degli angoli in alto a sinistra e in basso a destra dell’immagine. |
| Meridiano | La longitudine del meridiano centrale della proiezione, specificata in gradi ad est di Greenwich. I numeri negativi possono essere utilizzati per specificare i gradi a ovest. |
| Fattore di scala | Rapporto tra il raggio del cilindro di proiezione e l&#39;asse del semimajor dell&#39;ellissoide. Per le proiezioni UWP (Universal Transverse Mercator), questo è sempre 0,9996. |

