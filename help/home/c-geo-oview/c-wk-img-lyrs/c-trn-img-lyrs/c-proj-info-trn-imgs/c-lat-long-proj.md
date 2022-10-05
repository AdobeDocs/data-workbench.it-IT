---
description: Il formato di proiezione latitudine-longitudine (LatLonProjection) nel file Terrain Images.cfg è definito da quattro parametri di latitudine e longitudine.
title: Proiezioni di latitudine e longitudine
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# Proiezioni di latitudine e longitudine{#latitude-longitude-projections}

{{eol}}

Il formato di proiezione latitudine-longitudine (LatLonProjection) nel file Terrain Images.cfg è definito da quattro parametri di latitudine e longitudine.

Per specificare un LatLonProjection per le immagini non proiettate (bitmap non proiettate e immagini generali, non proiettate), è possibile immettere le impostazioni per LatLonProjection all&#39;interno del [!DNL Terrain Images.cfg] all’interno di Data Workbench. Vedi [Per specificare una proiezione LatLon per le immagini non proiettate](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

Per specificare una proiezione LatLon per le immagini con informazioni di proiezione incorporate, è necessario aprire la [!DNL Terrain Images.cfg] in un editor di testo come Notepad, impostare il parametro Info proiezione su &quot;LatLonProjection&quot; e aggiungere le impostazioni per LatLonProjection. Vedi [Per specificare un LatLonProjection per le immagini all&#39;interno di informazioni di proiezione incorporate..](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [Per specificare una proiezione LatLon per le immagini non proiettate](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [Per specificare una proiezione LatLon per le immagini all&#39;interno delle informazioni di proiezione incorporate..](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## Per specificare una proiezione LatLon per le immagini non proiettate {#section-26554eefe645481faba68396fa13756a}

1. Apri [!DNL Terrain Images.cfg] in data workbench e aggiungi un’origine del livello immagine del terreno come descritto in [Per definire un livello immagine del terreno](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

1. Modificate i parametri Info proiezione utilizzando la tabella dei parametri riportata di seguito come guida:

   | Parametro | Descrizione |
   |---|---|
   | Lat0 | La latitudine del bordo superiore dell&#39;immagine, in gradi, dove 90 è il Polo Nord e -90 è il Polo Sud. |
   | Lat1 | Latitudine del bordo inferiore dell&#39;immagine. |
   | Lon0 | La longitudine del bordo sinistro dell&#39;immagine, in gradi, dove i numeri positivi sono orientali e i numeri negativi sono longitudini occidentali. |
   | Lon1 | La longitudine del bordo destro dell&#39;immagine. |

1. Salva il file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic su **[!UICONTROL Save]**.

1. Per salvare le modifiche apportate localmente al computer server di Data Workbench, nella [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta [!DNL Terrain Images.cfg] in [!DNL Temp] , quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Per specificare una proiezione LatLon per le immagini all&#39;interno delle informazioni di proiezione incorporate {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. La [!DNL Terrain Images.cfg] il file si trova all&#39;interno di questa directory.

1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Terrain Images.cfg], quindi fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nel [!DNL Temp] colonna per [!DNL Terrain Images.cfg].

1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nel [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. La [!DNL Terrain Images.cfg] il file viene visualizzato in una finestra Blocco note.

1. Modifica i parametri di Informazioni proiezione utilizzando come guida il seguente frammento di file di esempio. Assicurati di specificare il tipo di proiezione come evidenziato di seguito. Per una descrizione dei parametri, vedere la tabella Parametri LatLonProjection nella procedura precedente.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
