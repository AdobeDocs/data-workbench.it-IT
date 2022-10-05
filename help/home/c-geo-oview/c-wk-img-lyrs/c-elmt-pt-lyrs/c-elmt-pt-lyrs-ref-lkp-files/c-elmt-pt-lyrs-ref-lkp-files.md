---
description: Quando si crea un livello punto elemento che fa riferimento a un file di ricerca per ottenere dati di latitudine e longitudine, la posizione del punto viene ottenuta recuperando ogni elemento e la relativa latitudine e longitudine associate dal file di ricerca.
title: Definizione dei livelli del punto elemento con riferimento ai file di ricerca
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 4%

---

# Definizione dei livelli del punto elemento con riferimento ai file di ricerca{#defining-element-point-layers-referencing-lookup-files}

{{eol}}

Quando si crea un livello punto elemento che fa riferimento a un file di ricerca per ottenere dati di latitudine e longitudine, la posizione del punto viene ottenuta recuperando ogni elemento e la relativa latitudine e longitudine associate dal file di ricerca.

Invece di utilizzare un file di ricerca, puoi utilizzare la funzione [!DNL Dynamic Points] che incorpora la latitudine e la longitudine di una posizione nel nome di ciascun elemento di una dimensione. Vedi [Definizione dei livelli del punto elemento utilizzando i punti dinamici](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

Per definire un livello di punto elemento che fa riferimento a un file di ricerca, è necessario creare o disporre già dei seguenti elementi:

* **Una dimensione** definito in [!DNL Transformation.cfg] file o set di dati di trasformazione includono file . Per informazioni sui file di configurazione della trasformazione, consulta la sezione *Guida alla configurazione del set di dati*.

* **Un file di ricerca** contenente i dati utilizzati per tracciare ciascun punto dati. Questo file deve contenere almeno tre colonne di dati per ogni punto dati: la chiave, la longitudine e la latitudine. Per ulteriori informazioni sul formato richiesto del file di ricerca, vedi [Formato del file di ricerca del punto elemento](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **Un file di livello** che specifica la posizione del file di ricerca e identifica la dimensione e la metrica correlate, nonché i nomi delle colonne chiave, longitudine e latitudine nel file di ricerca. Per ulteriori informazioni sul formato richiesto del file di livello, vedi [Formato del file livello del punto elemento](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>La [!DNL Zip Points.layer] file, fornito con [!DNL Geography] profile, è un livello punto elemento che identifica [!DNL Zipcode.dim] file, [!DNL Sessions.metric] file, [!DNL Zip Points.txt] file di ricerca e i nomi delle colonne chiave, longitudine, latitudine e nome nel file di ricerca.
