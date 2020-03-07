---
description: Quando si crea un livello punto elemento che fa riferimento a un file di ricerca per ottenere dati di latitudine e longitudine, la posizione del punto viene ottenuta recuperando ogni elemento e la relativa latitudine e longitudine associati dal file di ricerca.
solution: Analytics
title: Definizione dei livelli dei punti elemento con riferimento ai file di ricerca
topic: Data workbench
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definizione dei livelli dei punti elemento con riferimento ai file di ricerca{#defining-element-point-layers-referencing-lookup-files}

Quando si crea un livello punto elemento che fa riferimento a un file di ricerca per ottenere dati di latitudine e longitudine, la posizione del punto viene ottenuta recuperando ogni elemento e la relativa latitudine e longitudine associati dal file di ricerca.

Invece di utilizzare un file di ricerca, è possibile utilizzare la [!DNL Dynamic Points] funzionalità, che incorpora la latitudine e la longitudine di una posizione nel nome di ciascun elemento di una dimensione. Consultate [Definizione Dei Livelli Dei Punti Dell’Elemento Utilizzando I Punti](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)Dinamici.

Per definire un livello punto elemento che faccia riferimento a un file di ricerca, è necessario creare o disporre già di quanto segue:

* **Una dimensione** definita nel [!DNL Transformation.cfg] file o in un set di dati di trasformazione include il file. Per informazioni sui file di configurazione della trasformazione, vedere la Guida alla configurazione del *set di dati*.

* **Un file** di ricerca contenente i dati utilizzati per il plot di ciascun punto dati. Il file deve contenere almeno tre colonne di dati per ogni punto dati: la chiave, la longitudine e la latitudine. Per ulteriori informazioni sul formato richiesto del file di ricerca, vedere Formato [file di ricerca punto](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121)elemento.

* **Un file** di livello che specifica la posizione del file di ricerca e identifica la dimensione e la metrica correlate, nonché i nomi delle colonne chiave, longitudine e latitudine nel file di ricerca. Per ulteriori informazioni sul formato richiesto del file di livello, consultate Formato [file livello punto](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981)elemento.

>[!NOTE]
>
>Il [!DNL Zip Points.layer] file, fornito con il [!DNL Geography] profilo, è un livello punto elemento che identifica il [!DNL Zipcode.dim] file, il [!DNL Sessions.metric] file, il file di [!DNL Zip Points.txt] ricerca e i nomi delle colonne chiave, longitudine, latitudine e nome nel file di ricerca.

