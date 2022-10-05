---
description: La geografia di Data Workbench supporta sia le proiezioni di latitudine-longitudine sia le proiezioni UWP (Universal Transverse Mercator) per tutte le sorgenti di livello immagine del terreno.
title: Specifica delle informazioni di proiezione per le immagini del terreno
uuid: 4a476192-e749-4187-b64e-9794f39b0019
exl-id: 400b9b59-f700-4b16-8549-fe93140cad1a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%

---

# Specifica delle informazioni di proiezione per le immagini del terreno{#specifying-projection-information-for-terrain-images}

{{eol}}

La geografia di Data Workbench supporta sia le proiezioni di latitudine-longitudine sia le proiezioni UWP (Universal Transverse Mercator) per tutte le sorgenti di livello immagine del terreno.

Le informazioni di proiezione sono necessarie per le bitmap non proiettate e per le immagini generali, non proiettate. È possibile specificare le informazioni di proiezione per le immagini con informazioni di proiezione incorporate, anche se in genere non è necessario perché i parametri della proiezione sono determinati automaticamente dai dati geodetici incorporati nell&#39;immagine stessa. Le sezioni seguenti forniscono dettagli sulla specifica di questi formati di proiezione nel [!DNL Terrain Images.cfg] file.
