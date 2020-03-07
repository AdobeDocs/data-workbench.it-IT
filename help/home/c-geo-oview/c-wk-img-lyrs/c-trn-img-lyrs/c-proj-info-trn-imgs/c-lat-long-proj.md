---
description: Il formato di proiezione latitudine-longitudine (LatLonProjection) nel file Terrain Images.cfg è definito da quattro parametri per latitudine e longitudine.
solution: Analytics
title: Proiezioni Latitudine-Longitudine
topic: Data workbench
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Proiezioni Latitudine-Longitudine{#latitude-longitude-projections}

Il formato di proiezione latitudine-longitudine (LatLonProjection) nel file Terrain Images.cfg è definito da quattro parametri per latitudine e longitudine.

Per specificare un LatLonProjection per immagini non proiettate (immagini bitmap non proiettate e immagini generali, non proiettate), è possibile immettere le impostazioni per LatLonProjection all&#39;interno della [!DNL Terrain Images.cfg] finestra nel workbench dati. Consultate [Specifica di un&#39;immagine LatLonProjection per le immagini](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)non proiettate.

Per specificare un LatLonProjection per le immagini con informazioni di proiezione incorporate, è necessario aprire il [!DNL Terrain Images.cfg] file in un editor di testo come Notepad, impostare il parametro Informazioni proiezione su &quot;LatLonProjection&quot; e aggiungere le impostazioni per LatLonProjection. Consultate [Per specificare un LatLonProjection per le immagini all&#39;interno delle informazioni di proiezione incorporate...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [Per specificare una proiezione LatLon per immagini non proiettate](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [Per specificare una proiezione LatLon per le immagini all&#39;interno delle informazioni di proiezione incorporate...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## Per specificare una proiezione LatLon per immagini non proiettate {#section-26554eefe645481faba68396fa13756a}

1. Aprite il [!DNL Terrain Images.cfg] file nel workbench dati e aggiungete un’origine del livello immagine del terreno come descritto in [Per definire un livello](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)immagine del terreno.

1. Modificate i parametri Informazioni proiezione utilizzando come guida la seguente tabella di parametri:

   | Parametro | Descrizione |
   |---|---|
   | Lat0 | Latitudine del bordo superiore dell&#39;immagine, in gradi, dove 90 corrisponde al Polo Nord e -90 al Polo Sud. |
   | Lat1 | Latitudine del bordo inferiore dell’immagine. |
   | Lon0 | La longitudine del bordo sinistro dell&#39;immagine, in gradi, dove i numeri positivi sono orientali e i numeri negativi sono longitudini occidentali. |
   | Lon1 | Longitudine del bordo destro dell’immagine. |

1. Salvare il file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic su **[!UICONTROL Save]**.

1. Per salvare le modifiche apportate localmente al computer server workbench dati, fare clic con il pulsante destro del [!DNL Server Files Manager]mouse sul segno di spunta [!DNL Terrain Images.cfg] nella [!DNL Temp] colonna, quindi scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Per specificare una proiezione LatLon per le immagini all&#39;interno delle informazioni di proiezione incorporate {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL Terrain Images.cfg] file si trova all&#39;interno di questa directory.

1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Terrain Images.cfg], quindi scegliere **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Terrain Images.cfg].

1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il [!DNL Terrain Images.cfg] file viene visualizzato in una finestra Blocco note.

1. Modificate i parametri Informazioni proiezione utilizzando come guida il seguente frammento di file di esempio. Accertatevi di specificare il tipo di proiezione come evidenziato di seguito. Per una descrizione dei parametri, vedere la tabella Parametri LatLonProjection nella procedura precedente.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```

