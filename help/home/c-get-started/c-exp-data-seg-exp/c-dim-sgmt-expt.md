---
description: Eventuali dati da esportare devono essere definiti come una dimensione all’interno del profilo.
title: Creare dimensioni da utilizzare con l’esportazione di segmenti
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
exl-id: 0f16c242-10f6-4014-b848-ea001e9d085c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 8%

---

# Creare dimensioni da utilizzare con l’esportazione di segmenti{#create-dimensions-for-use-with-segment-export}

Eventuali dati da esportare devono essere definiti come una dimensione all’interno del profilo.

Se la dimensione non esiste già nel profilo, devi crearla. Puoi creare dimensioni utilizzando uno dei seguenti metodi:

* Aggiungi una dimensione al file [!DNL Transformation.cfg]. Consulta la *Guida alla configurazione del set di dati*.

* Crea un nuovo file [!DNL .dim]. Consulta [Creazione e modifica di Dimension derivati](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* Effettuare selezioni in una visualizzazione, ad esempio una mappa del processo o un segmento, e salvare le selezioni come una dimensione. Consulta [Salvataggio di Dimension da Process Maps](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) e [Creazione di Dimension di segmenti](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e).

L’esportazione di un campo di dati come ID tracciamento o Indirizzo e-mail (che può contenere molti elementi) richiede la creazione di una dimensione standard che memorizzi le stringhe di dati non elaborate.

Per ulteriori informazioni sulle dimensioni comuni, consulta la *Guida alla configurazione del set di dati*.
