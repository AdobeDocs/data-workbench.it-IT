---
description: Informazioni concettuali sui livelli del profilo Geografia, i tipi di livelli delle immagini e la creazione di nuovi livelli.
title: Informazioni sui livelli immagine
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Informazioni sui livelli immagine{#understanding-imagery-layers}

Informazioni concettuali sui livelli del profilo Geografia, i tipi di livelli delle immagini e la creazione di nuovi livelli.

## Tipi di livelli immagine {#section-ce25364651a04cd1b83f9ac7c231fa41}

Data Workbench [!DNL Geography] consente di visualizzare i seguenti tipi di livelli immagine all’interno di Data Workbench:

* **Livello immagine del terreno:** questo tipo di livello visualizza le immagini del terreno della Terra, su cui possono essere visualizzati i dati geografici. La visualizzazione a livello globale all’interno di Data Workbench è un esempio di livello immagine del terreno. Consulta [Utilizzo dei livelli immagine del terreno](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Livello del punto elemento:** questo tipo di livello visualizza un punto sul globo per ogni elemento di una dimensione. Consulta [Utilizzo dei livelli del punto elemento](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Livello vettoriale:** questo tipo di livello visualizza i dati vettoriali (line art) sul globo. Consulta [Utilizzo dei livelli vettoriali](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

All’interno di Data Workbench, puoi selezionare i livelli da visualizzare per una particolare attività di analisi.

## Livelli del profilo geografico {#section-4d9fb9b357764493a4d97d2b4068bb67}

Il profilo [!DNL Geography] offre un set di livelli predefiniti per immagini, memorizzati nella cartella Profiles\Geography\Maps folder within the data workbench server installation directory:

* **Marmo blu 2 km:** questo livello di immagine del terreno crea una mappa 3D del mondo, che è ciò che viene visualizzato quando si aggiunge la visualizzazione del globo a un&#39;area di lavoro. Quando questo livello non è selezionato, il globo non è visibile ma gli altri livelli vengono comunque visualizzati. Il file [!DNL Blue Marble 2km.layer] fa riferimento al file [!DNL Blue Marble 2km.tsi].

   Per informazioni sulle operazioni con la visualizzazione a livello globale, consulta la *Guida utente Data Workbench*.

* **Punti ZIP:** questo livello di punto elemento ti consente di mappare le posizioni nel set di dati utilizzando un codice ZIP degli Stati Uniti. Il file di ricerca [!DNL Zip Points.txt] (fornito dall’Adobe) contiene un elenco di tutti i codici ZIP degli Stati Uniti e di latitudine e longitudine di ciascun codice ZIP. Il file [!DNL Zip Points.layer] fa riferimento al file [!DNL Zip Points.txt] e al file [!DNL Zipcode.dim] e contiene i parametri di configurazione necessari per visualizzare le posizioni sul globo. Ogni elemento della dimensione del codice ZIP ( [!DNL Zipcode.dim]) definito all’interno del set di dati viene mappato sul globo utilizzando la latitudine e la longitudine elencate per tale codice ZIP nel file di ricerca [!DNL Zip Points.txt] .

   Per informazioni sulla definizione delle dimensioni, vedere la *Guida alla configurazione del set di dati.*

* **Limiti:** Questo livello vettoriale fornisce i principali confini politici mondiali, come i paesi, così come i confini delle caratteristiche fisiche naturali della Terra, come i laghi e le isole. Il file [!DNL Boundaries.layer] fa riferimento a uno o più dei file [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec] e [!DNL world boundaries.vec].

* **Coordinate IP:** questo livello di punto elemento utilizza punti dinamici per consentire di mappare le posizioni nel set di dati utilizzando gli indirizzi IP. Il file [!DNL IP Coordinates.layer] fa riferimento alla dimensione Coordinate ( [!DNL Coordinates.dim]) e specifica la metrica Visitatori come metrica da utilizzare per determinare la dimensione dei punti sul globo per ciascuna coordinata.

Il profilo [!DNL Geography] o altri profili presenti nell&#39;installazione possono contenere livelli aggiuntivi di immagini forniti dall&#39;Adobe o creati dalla società.

## Creazione di nuovi livelli {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

È possibile creare nuovi livelli di immagini copiando il tipo appropriato di file di livello incluso nel profilo [!DNL Geography] in qualsiasi cartella Profiles\*profile name*\Maps, quindi rinominando e modificando il file come appropriato. Tutti i nuovi livelli devono soddisfare i seguenti requisiti:

* Il file [!DNL .layer] deve rispettare il formato di uno dei tipi di livello supportati.
* Se necessario, il file [!DNL .layer] deve fare riferimento ai file di ricerca e dimensione appropriati.
* Anche il file di ricerca di riferimento deve essere memorizzato nella directory di installazione del server di Data Workbench e il relativo percorso deve essere specificato con precisione nel file [!DNL .layer].

Per ulteriori informazioni sul formato e i parametri per ciascun tipo di file di livello e i relativi file associati, vedere la sezione di questo capitolo relativa al tipo di livello appropriato.
