---
description: Informazioni concettuali sui livelli del profilo Geografia, sui tipi di livelli di immagini e sulla creazione di nuovi livelli.
solution: Analytics
title: Nozioni di base sui livelli delle immagini
topic: Data workbench
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Nozioni di base sui livelli delle immagini{#understanding-imagery-layers}

Informazioni concettuali sui livelli del profilo Geografia, sui tipi di livelli di immagini e sulla creazione di nuovi livelli.

## Tipi di livelli di immagini {#section-ce25364651a04cd1b83f9ac7c231fa41}

Workbench dati [!DNL Geography] consente di visualizzare i seguenti tipi di livelli di immagini nel workbench dati:

* **Livello immagine terreno:** Questo tipo di strato mostra le immagini del terreno della Terra, su cui possono essere visualizzati i dati geografici. La visualizzazione globale nel workbench dati è un esempio di un livello di immagine del terreno. Consultate [Utilizzo dei livelli](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)immagine terreno.

* **Livello punto elemento:** Questo tipo di livello visualizza un punto sul globo per ogni elemento di una dimensione. Consultate [Utilizzo dei livelli](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9)dei punti elemento.

* **Livello vettoriale:** Questo tipo di livello visualizza i dati vettoriali (line art) sul globo. Consultate [Utilizzo dei livelli](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620)vettoriali.

Nel workbench dati, potete selezionare quale dei livelli visualizzare per una particolare attività di analisi.

## Livelli profilo di geografia {#section-4d9fb9b357764493a4d97d2b4068bb67}

Il [!DNL Geography] profilo fornisce un set di livelli predefiniti per immagini, memorizzati nella cartella Profiles\Geography\Maps folder within the data workbench server installation directory:

* **Marmo blu 2 km:** Questo livello di immagine del terreno crea una mappa 3D del mondo, che è ciò che viene visualizzato quando aggiungete la visualizzazione globale a un’area di lavoro. Se questo livello non è selezionato, il globo non è visibile ma gli altri livelli continuano a essere visualizzati. Il [!DNL Blue Marble 2km.layer] file fa riferimento al [!DNL Blue Marble 2km.tsi] file.

   Per informazioni su come utilizzare la visualizzazione globale, consulta la Guida *utente di Workbench* dati.

* **Punti ZIP:** Questo livello punto elemento consente di mappare le posizioni nel set di dati utilizzando un CAP statunitense. Il file di [!DNL Zip Points.txt] ricerca (fornito da Adobe) contiene un elenco di tutti i codici ZIP degli Stati Uniti e di latitudine e longitudine di ciascun codice ZIP. Il [!DNL Zip Points.layer] file fa riferimento al [!DNL Zip Points.txt] file e al [!DNL Zipcode.dim] file e contiene i parametri di configurazione necessari per visualizzare le posizioni nel mondo. Ogni elemento della dimensione del codice ZIP ( [!DNL Zipcode.dim]) definito all&#39;interno del set di dati viene mappato sul globo utilizzando la latitudine e la longitudine elencate per tale codice ZIP nel file di [!DNL Zip Points.txt] ricerca.

   Per informazioni sulla definizione delle dimensioni, vedere la Guida alla configurazione del *set di dati.*

* **Bordi:** Questo strato vettoriale fornisce i principali confini politici mondiali, come i paesi, così come i confini delle caratteristiche fisiche naturali della Terra, come i laghi e le isole. Il [!DNL Boundaries.layer] file fa riferimento a uno o più file [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]e [!DNL world boundaries.vec] .

* **Coordinate IP:** Questo livello punto elemento utilizza punti dinamici per consentire la mappatura delle posizioni nel set di dati utilizzando indirizzi IP. Il [!DNL IP Coordinates.layer] file fa riferimento alla dimensione Coordinate ( [!DNL Coordinates.dim]) e specifica la metrica Visitatori come metrica da utilizzare per determinare la dimensione dei punti sul globo per ciascuna coordinata.

Il vostro [!DNL Geography] profilo o altri profili nell’installazione potrebbe contenere ulteriori livelli di immagini forniti da Adobe o creati dalla vostra società.

## Creazione di nuovi livelli {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Potete creare nuovi livelli di immagini copiando il tipo appropriato di file di livello incluso nel [!DNL Geography] profilo in qualsiasi cartella Profili\*nome profilo*\Maps, quindi rinominando e modificando il file come appropriato. Tutti i nuovi livelli devono soddisfare i seguenti requisiti:

* Il [!DNL .layer] file deve rispettare il formato di uno dei tipi di livelli supportati.
* Se necessario, il [!DNL .layer] file deve fare riferimento ai file di ricerca e dimensione appropriati.
* Anche il file di ricerca di riferimento deve essere memorizzato nella directory di installazione del server workbench dati e il relativo percorso deve essere specificato con precisione nel [!DNL .layer] file.

Per ulteriori informazioni sul formato e i parametri di ciascun tipo di file di livello e dei relativi file associati, consultate la sezione di questo capitolo relativa al tipo di livello appropriato.
