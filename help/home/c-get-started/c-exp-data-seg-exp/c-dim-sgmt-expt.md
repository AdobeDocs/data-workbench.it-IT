---
description: Eventuali dati da esportare devono essere definiti come una dimensione all’interno del profilo.
solution: Analytics
title: Creare dimensioni da utilizzare con l’esportazione di segmenti
topic: Data workbench
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creare dimensioni da utilizzare con l’esportazione di segmenti{#create-dimensions-for-use-with-segment-export}

Eventuali dati da esportare devono essere definiti come una dimensione all’interno del profilo.

Se la dimensione non esiste già nel profilo, è necessario crearla. Potete creare le dimensioni utilizzando uno dei seguenti metodi:

* Aggiungete una dimensione al [!DNL Transformation.cfg] file. Consulta la Guida alla configurazione del *set di dati*.

* Create a new [!DNL .dim] file. Consultate [Creazione e modifica di dimensioni](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93)derivate.

* Effettuare selezioni in una visualizzazione, ad esempio una mappa di processo o un segmento, e salvare le selezioni come una dimensione. Consultate [Salvataggio di dimensioni dalle mappe](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) di processo e [Creazione di dimensioni](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e)di segmento.

Per esportare un campo di dati come ID tracciamento o Indirizzo e-mail (che può contenere molti elementi) è necessario creare una dimensione standard in cui memorizzare le stringhe di dati non elaborate.

Per ulteriori informazioni sulle dimensioni standard, consulta la Guida alla configurazione del *set di dati*.
