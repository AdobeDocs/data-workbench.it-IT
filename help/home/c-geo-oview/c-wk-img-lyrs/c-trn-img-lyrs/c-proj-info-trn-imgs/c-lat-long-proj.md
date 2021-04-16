---
description: Il formato di proiezione latitudine-longitudine (LatLonProjection) nel file Terrain Images.cfg è definito da quattro parametri di latitudine e longitudine.
title: Proiezioni di latitudine e longitudine
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# Proiezioni di latitudine e longitudine{#latitude-longitude-projections}

Il formato di proiezione latitudine-longitudine (LatLonProjection) nel file Terrain Images.cfg è definito da quattro parametri di latitudine e longitudine.

Per specificare un LatLonProjection per le immagini non proiettate (bitmap non proiettate e immagini generali, non proiettate), è possibile immettere le impostazioni per LatLonProjection nella finestra [!DNL Terrain Images.cfg] di Data Workbench. Vedere [Per specificare una proiezione LatLon per le immagini non proiettate](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

Per specificare un LatLonProjection per le immagini con informazioni di proiezione incorporate, è necessario aprire il file [!DNL Terrain Images.cfg] in un editor di testo come Notepad, impostare il parametro Info proiezione su &quot;LatLonProjection&quot; e aggiungere le impostazioni per LatLonProjection. Vedere [Per specificare una proiezione LatLon per le immagini all&#39;interno di informazioni di proiezione incorporate...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [Per specificare una proiezione LatLon per le immagini non proiettate](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [Per specificare una proiezione LatLon per le immagini all&#39;interno delle informazioni di proiezione incorporate..](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## Per specificare una proiezione LatLon per le immagini non proiettate {#section-26554eefe645481faba68396fa13756a}

1. Apri il file [!DNL Terrain Images.cfg] in Data Workbench e aggiungi un’origine del livello immagine del terreno come descritto in [Per definire un livello immagine del terreno](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

1. Modificate i parametri Info proiezione utilizzando la tabella dei parametri riportata di seguito come guida:

   | Parametro | Descrizione |
   |---|---|
   | Lat0 | La latitudine del bordo superiore dell&#39;immagine, in gradi, dove 90 è il Polo Nord e -90 è il Polo Sud. |
   | Lat1 | Latitudine del bordo inferiore dell&#39;immagine. |
   | Lon0 | La longitudine del bordo sinistro dell&#39;immagine, in gradi, dove i numeri positivi sono orientali e i numeri negativi sono longitudini occidentali. |
   | Lon1 | La longitudine del bordo destro dell&#39;immagine. |

1. Salva il file facendo clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic su **[!UICONTROL Save]**.

1. Per salvare le modifiche apportate localmente al computer server di Data Workbench, fai clic con il pulsante destro del mouse sul segno di spunta [!DNL Terrain Images.cfg] nella colonna [!DNL Temp], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.[!DNL Server Files Manager]

## Per specificare una proiezione LatLon per le immagini all&#39;interno delle informazioni di proiezione incorporate {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. Il file [!DNL Terrain Images.cfg] si trova all&#39;interno di questa directory.

1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Terrain Images.cfg], quindi fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella colonna [!DNL Temp] per [!DNL Terrain Images.cfg].

1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il file [!DNL Terrain Images.cfg] viene visualizzato in una finestra Blocco note.

1. Modifica i parametri di Informazioni proiezione utilizzando come guida il seguente frammento di file di esempio. Assicurati di specificare il tipo di proiezione come evidenziato di seguito. Per una descrizione dei parametri, vedere la tabella Parametri LatLonProjection nella procedura precedente.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
