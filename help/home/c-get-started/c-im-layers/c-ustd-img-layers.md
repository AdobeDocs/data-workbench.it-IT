---
description: Informazioni concettuali sui livelli delle immagini.
solution: Analytics
title: I livelli delle immagini
topic: Data workbench
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# I livelli delle immagini{#about-imagery-layers}

Informazioni concettuali sui livelli delle immagini.

## Tipi di livelli di immagini {#section-891cbf61e8334690bd203a2bb9761b25}

In Workbench dati è possibile visualizzare i seguenti tipi di livelli di immagini:

* **[!UICONTROL Terrain image layer]:**Questo tipo di strato mostra le immagini del terreno della Terra, su cui possono essere visualizzati i dati geografici. La visualizzazione globale in è un esempio di un livello di immagine del terreno. Consultate[Utilizzo dei livelli](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f)immagine terreno.

* **[!UICONTROL Element point layer]:**Questo tipo di livello visualizza un punto sul globo per ogni elemento di una dimensione. Consultate[Utilizzo dei livelli](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd)dei punti elemento.

* **[!UICONTROL Vector layer]:**Questo tipo di livello visualizza i dati vettoriali (line art) sul globo. Consultate[Utilizzo dei livelli](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9)vettoriali.

* **[!UICONTROL Presentation layer]** Annotate e definite le visualizzazioni con una sovrapposizione delle presentazioni. Aggiungete note di testo, frecce, immagini e codifica colore per evidenziare e definire i dati e condividerli con gli altri utenti.

In Workbench dati è possibile selezionare i livelli da visualizzare per una particolare attività di analisi.

## Livelli del profilo di geografia {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

Il [!DNL Geography] profilo fornisce un set di livelli predefiniti per immagini, memorizzati nella cartella Profiles\Geography\Maps folder within the Data Workbench server installation directory:

* **[!UICONTROL Blue Marble 2km]:**Questo livello di immagine del terreno crea una mappa 3D del mondo, che è ciò che viene visualizzato quando aggiungete la visualizzazione globale a un’area di lavoro. Se questo livello non è selezionato, il globo non è visibile ma gli altri livelli continuano a essere visualizzati. Il[!DNL Blue Marble 2km.layer]file fa riferimento al[!DNL Blue Marble 2km.tsi]file.

* **[!UICONTROL Zip Points]:**Questo livello punto elemento consente di mappare le posizioni nel set di dati utilizzando un CAP statunitense. Il file di[!DNL Zip Points.txt]ricerca (fornito da Adobe) contiene un elenco di tutti i codici ZIP degli Stati Uniti e di latitudine e longitudine di ciascun codice ZIP. Il[!DNL Zip Points.layer]file fa riferimento al[!DNL Zip Points.txt]file e al[!DNL Zipcode.dim]file e contiene i parametri di configurazione necessari per visualizzare le posizioni nel mondo. Ogni elemento della dimensione del codice ZIP ([!DNL Zipcode.dim]) definito all&#39;interno del set di dati viene mappato sul globo utilizzando la latitudine e la longitudine elencate per tale codice ZIP nel file di[!DNL Zip Points.txt]ricerca.

   Per informazioni sulla definizione delle dimensioni, vedere la Guida alla configurazione del *set di dati*.

* **[!UICONTROL Boundaries]:**Questo strato vettoriale fornisce i principali confini politici mondiali, come i paesi, così come i confini delle caratteristiche fisiche naturali della Terra, come i laghi e le isole. Il[!DNL Boundaries.layer]file fa riferimento a uno o più file[!DNL mwcoast.vec],[!DNL mwisland.vec],[!DNL mwlake.vec],[!DNL mwnation.vec],[!DNL mwriver.vec],[!DNL mwstate.vec],[!DNL US states.vec]e[!DNL world boundaries.vec].

* **[!UICONTROL IP Coordinates]:**Questo livello punto elemento utilizza punti dinamici per consentire la mappatura delle posizioni nel set di dati utilizzando indirizzi IP. Il[!DNL IP Coordinates.layer]file fa riferimento alla dimensione Coordinate ([!DNL Coordinates.dim]) e specifica la metrica Visitatori come metrica da utilizzare per determinare la dimensione dei punti sul globo per ciascuna coordinata.

Il profilo [!UICONTROLNL Geografia] o altri profili dell&#39;installazione possono contenere ulteriori livelli di immagini forniti da Adobe o creati dalla società.

## Create a new layer {#section-b5313773316c4e0fa748f7376a8e7f0b}

Potete creare nuovi livelli di immagini copiando il tipo appropriato di file di livello incluso nel [!DNL Geography] profilo in qualsiasi cartella Profili\*nome profilo*\Maps, quindi rinominando e modificando il file come appropriato. Tutti i nuovi livelli devono soddisfare i seguenti requisiti:

* Il [!DNL .layer] file deve rispettare il formato di uno dei tipi di livelli supportati.
* Se necessario, il [!DNL .layer] file deve fare riferimento ai file di ricerca e dimensione appropriati.
* Anche il file di ricerca di riferimento deve essere memorizzato nella directory di installazione del server Workbench dati e il relativo percorso deve essere specificato con precisione nel [!DNL .layer] file.

Per ulteriori informazioni sul formato e i parametri di ciascun tipo di file di livello e dei relativi file associati, consultate la sezione di questo capitolo relativa al tipo di livello appropriato.
