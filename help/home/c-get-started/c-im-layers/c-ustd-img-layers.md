---
description: Informazioni concettuali sui livelli delle immagini.
title: Informazioni sui livelli delle immagini
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
exl-id: c6d30747-70d2-4489-ad64-fd131e76a7a2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 5%

---

# Informazioni sui livelli delle immagini{#about-imagery-layers}

Informazioni concettuali sui livelli delle immagini.

## Tipi di livelli immagine {#section-891cbf61e8334690bd203a2bb9761b25}

Potete visualizzare i seguenti tipi di livelli di immagini nella Data Workbench:

* **[!UICONTROL Terrain image layer]:** Questo tipo di livello visualizza le immagini del terreno della Terra, su cui possono essere visualizzati i dati geografici. La visualizzazione del globo in è un esempio di livello immagine del terreno. Consulta [Utilizzo dei livelli immagine del terreno](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** questo tipo di livello visualizza un punto sul globo per ogni elemento di una dimensione. Consulta [Utilizzo dei livelli del punto elemento](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:** Questo tipo di livello visualizza i dati vettoriali (line art) sul globo. Consulta [Utilizzo dei livelli vettoriali](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]** Annotate e definite le visualizzazioni con una sovrapposizione delle presentazioni. Aggiungete note di testo, frecce, immagini e codifica colore per evidenziare e definire i dati e condividerli con gli altri utenti.

Nella Data Workbench, puoi selezionare i livelli da visualizzare per una particolare attività di analisi.

## Livelli del profilo geografico {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

Il profilo [!DNL Geography] offre un set di livelli predefiniti per immagini, memorizzati nella cartella Profiles\Geography\Maps folder within the Data Workbench server installation directory:

* **[!UICONTROL Blue Marble 2km]:** questo livello di immagine del terreno crea una mappa 3D del mondo, che è ciò che viene visualizzato quando aggiungi la visualizzazione del globo a un’area di lavoro. Quando questo livello non è selezionato, il globo non è visibile ma gli altri livelli vengono comunque visualizzati. Il file [!DNL Blue Marble 2km.layer] fa riferimento al file [!DNL Blue Marble 2km.tsi].

* **[!UICONTROL Zip Points]:** Questo livello punto elemento ti consente di mappare le posizioni nel tuo set di dati utilizzando un codice ZIP degli Stati Uniti. Il file di ricerca [!DNL Zip Points.txt] (fornito dall’Adobe) contiene un elenco di tutti i codici ZIP degli Stati Uniti e di latitudine e longitudine di ciascun codice ZIP. Il file [!DNL Zip Points.layer] fa riferimento al file [!DNL Zip Points.txt] e al file [!DNL Zipcode.dim] e contiene i parametri di configurazione necessari per visualizzare le posizioni sul globo. Ogni elemento della dimensione del codice ZIP ( [!DNL Zipcode.dim]) definito all’interno del set di dati viene mappato sul globo utilizzando la latitudine e la longitudine elencate per tale codice ZIP nel file di ricerca [!DNL Zip Points.txt] .

   Per informazioni sulla definizione delle dimensioni, vedere la *Guida alla configurazione del set di dati*.

* **[!UICONTROL Boundaries]:** Questo livello vettoriale fornisce i principali confini politici mondiali, come i paesi, così come i confini delle caratteristiche fisiche naturali della Terra, come i laghi e le isole. Il file [!DNL Boundaries.layer] fa riferimento a uno o più dei file [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec] e [!DNL world boundaries.vec].

* **[!UICONTROL IP Coordinates]:** questo livello di punto elemento utilizza punti dinamici per consentire di mappare le posizioni nel set di dati utilizzando gli indirizzi IP. Il file [!DNL IP Coordinates.layer] fa riferimento alla dimensione Coordinate ( [!DNL Coordinates.dim]) e specifica la metrica Visitatori come metrica da utilizzare per determinare la dimensione dei punti sul globo per ciascuna coordinata.

Il profilo [!UICONTROL NL Geography] o altri profili presenti nell&#39;installazione possono contenere livelli aggiuntivi di immagini forniti dall&#39;Adobe o creati dalla società.

## Crea un nuovo livello {#section-b5313773316c4e0fa748f7376a8e7f0b}

È possibile creare nuovi livelli di immagini copiando il tipo appropriato di file di livello incluso nel profilo [!DNL Geography] in qualsiasi cartella Profiles\*profile name*\Maps, quindi rinominando e modificando il file come appropriato. Tutti i nuovi livelli devono soddisfare i seguenti requisiti:

* Il file [!DNL .layer] deve rispettare il formato di uno dei tipi di livello supportati.
* Se necessario, il file [!DNL .layer] deve fare riferimento ai file di ricerca e dimensione appropriati.
* Anche il file di ricerca di riferimento deve essere memorizzato nella directory di installazione del server Data Workbench e il relativo percorso deve essere specificato con precisione nel file [!DNL .layer].

Per ulteriori informazioni sul formato e i parametri per ciascun tipo di file di livello e i relativi file associati, vedere la sezione di questo capitolo relativa al tipo di livello appropriato.
