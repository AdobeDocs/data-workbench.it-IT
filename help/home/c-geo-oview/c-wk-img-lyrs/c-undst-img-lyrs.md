---
description: Informazioni concettuali sui livelli del profilo Geografia, i tipi di livelli delle immagini e la creazione di nuovi livelli.
title: Informazioni sui livelli immagine
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Informazioni sui livelli immagine{#understanding-imagery-layers}

{{eol}}

Informazioni concettuali sui livelli del profilo Geografia, i tipi di livelli delle immagini e la creazione di nuovi livelli.

## Tipi di livelli immagine {#section-ce25364651a04cd1b83f9ac7c231fa41}

Workbench dati [!DNL Geography] consente di visualizzare i seguenti tipi di livelli immagine all’interno di Data Workbench:

* **Livello immagine del terreno:** Questo tipo di livello mostra le immagini del terreno della Terra, su cui possono essere visualizzati i dati geografici. La visualizzazione a livello globale all’interno di Data Workbench è un esempio di livello immagine del terreno. Vedi [Utilizzo dei livelli immagine del terreno](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Livello del punto elemento:** Questo tipo di livello visualizza un punto sul globo per ogni elemento di una dimensione. Vedi [Utilizzo dei livelli del punto elemento](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Livello vettoriale:** Questo tipo di livello visualizza i dati vettoriali (line art) sul globo. Vedi [Utilizzo dei livelli vettoriali](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

All’interno di Data Workbench, puoi selezionare i livelli da visualizzare per una particolare attività di analisi.

## Livelli del profilo geografico {#section-4d9fb9b357764493a4d97d2b4068bb67}

La [!DNL Geography] profile fornisce un set di livelli di immagini predefiniti, memorizzati nella cartella Profiles\Geography\Maps all’interno della directory di installazione del server di Data Workbench:

* **Marmo blu 2 km:** Questo livello di immagine del terreno crea una mappa 3D del mondo, che è ciò che viene visualizzato quando aggiungi la visualizzazione del globo a un&#39;area di lavoro. Quando questo livello non è selezionato, il globo non è visibile ma gli altri livelli vengono comunque visualizzati. La [!DNL Blue Marble 2km.layer] fa riferimento al file [!DNL Blue Marble 2km.tsi] file.

   Per informazioni sulle operazioni con la visualizzazione a livello globale, consulta la sezione *Guida utente di Data Workbench*.

* **Punti ZIP:** Questo livello punto elemento ti consente di mappare le posizioni nel set di dati utilizzando un codice ZIP degli Stati Uniti. La [!DNL Zip Points.txt] il file di ricerca (fornito dall’Adobe) contiene un elenco di tutti i codici ZIP degli Stati Uniti e di latitudine e longitudine di ciascun codice ZIP. La [!DNL Zip Points.layer] fa riferimento al file [!DNL Zip Points.txt] e [!DNL Zipcode.dim] e contiene i parametri di configurazione necessari per visualizzare le posizioni sul globo. Ogni elemento della dimensione del codice ZIP ( [!DNL Zipcode.dim]) che definisci all’interno del set di dati viene mappato sul globo utilizzando la latitudine e la longitudine elencate per quel codice ZIP nel [!DNL Zip Points.txt] file di ricerca.

   Per informazioni sulla definizione delle dimensioni, consulta la sezione *Guida alla configurazione del set di dati.*

* **Limiti:** Questo livello vettoriale fornisce i principali confini politici mondiali, come i paesi, così come i confini delle caratteristiche fisiche naturali della Terra, come i laghi e le isole. La [!DNL Boundaries.layer] fa riferimento a uno o più dei [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]e [!DNL world boundaries.vec] file.

* **Coordinate IP:** Questo livello punto elemento utilizza punti dinamici per consentire di mappare le posizioni nel set di dati utilizzando gli indirizzi IP. La [!DNL IP Coordinates.layer] fa riferimento alla dimensione Coordinate ( [!DNL Coordinates.dim]) e specifica la metrica Visitatori come metrica da utilizzare per determinare la dimensione dei punti sul globo per ciascuna coordinata.

Le [!DNL Geography] profilo o altri profili nell’installazione possono contenere livelli aggiuntivi di immagini forniti dall’Adobe o creati dalla società.

## Creazione di nuovi livelli {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

È possibile creare nuovi livelli di immagini copiando il tipo appropriato di file di livello incluso nel [!DNL Geography] inserisci il profilo in una cartella Profiles\*profile name*\Maps , quindi rinominalo e modificalo a seconda delle necessità. Tutti i nuovi livelli devono soddisfare i seguenti requisiti:

* La [!DNL .layer] il file deve rispettare il formato di uno dei tipi di livello supportati.
* La [!DNL .layer] Se necessario, il file deve fare riferimento ai file di ricerca e dimensione appropriati.
* Anche il file di ricerca a cui si fa riferimento deve essere memorizzato nella directory di installazione del server di Data Workbench e il relativo percorso deve essere specificato con precisione in [!DNL .layer] file.

Per ulteriori informazioni sul formato e i parametri per ciascun tipo di file di livello e i relativi file associati, vedere la sezione di questo capitolo relativa al tipo di livello appropriato.
