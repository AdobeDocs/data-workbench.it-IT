---
description: Il workbench dati Geography supporta sia le proiezioni di latitudine-longitudine che le proiezioni UWP (Universal Transverse Mercator) per tutte le sorgenti di livello immagine del terreno.
solution: Analytics
title: Specifica delle informazioni di proiezione per le immagini del terreno
topic: Data workbench
uuid: 4a476192-e749-4187-b64e-9794f39b0019
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Specifica delle informazioni di proiezione per le immagini del terreno{#specifying-projection-information-for-terrain-images}

Il workbench dati Geography supporta sia le proiezioni di latitudine-longitudine che le proiezioni UWP (Universal Transverse Mercator) per tutte le sorgenti di livello immagine del terreno.

Le informazioni sulla proiezione sono necessarie per immagini bitmap non proiettate e per immagini generali, non proiettate. È possibile specificare le informazioni di proiezione per le immagini con informazioni di proiezione incorporate, anche se in genere non sono necessarie perché i parametri della proiezione sono determinati automaticamente dai dati geodetici incorporati nell&#39;immagine stessa. Le sezioni seguenti forniscono dettagli sulla specifica di questi formati di proiezione nel [!DNL Terrain Images.cfg] file.
