---
description: La trasformazione IPLookup prende i dati di geolocalizzazione IP o geolintelligence IP (forniti da qualsiasi fornitore di tali dati e convertiti in un formato proprietario da Adobe) e trasforma i dati in informazioni geografiche utilizzabili per l'analisi.
solution: Analytics
title: IPLookup
topic: Data workbench
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# IPLookup{#iplookup}

La trasformazione IPLookup prende i dati di geolocalizzazione IP o geolintelligence IP (forniti da qualsiasi fornitore di tali dati e convertiti in un formato proprietario da Adobe) e trasforma i dati in informazioni geografiche utilizzabili per l&#39;analisi.

Nel menu Aggiungi nuovo > *Tipo di trasformazione *sono elencate due [!DNL IPLookup] trasformazioni:

* [!DNL IPLookup] Quova per [!DNL IP geo-location] i dati

* [!DNL IPLookup] Inviato digitale per [!DNL IP geo-intelligence] i dati

Quando definite una [!DNL IPLookup] trasformazione, scegliete la trasformazione appropriata per i vostri [!DNL IP geo-location] dati o [!DNL IP geo-intelligence] dati.

<table id="table_C438A30AB5E64160A5C486D6887B1D7E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> impostazione predefinita </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commenti </td> 
   <td colname="col2"> Facoltativo. Note sulla trasformazione. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione </td> 
   <td colname="col2"> Condizioni in cui viene applicata la trasformazione. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> File </td> 
   <td colname="col2"> Percorso e nome del file di ricerca. I percorsi relativi riguardano la directory di installazione del server workbench dati. Questo file si trova in genere nella directory Ricerche all'interno della directory di installazione del server workbench dati. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo IP </td> 
   <td colname="col2"> Campo da cui leggere l'indirizzo IP. </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uscite </td> 
   <td colname="col2"> <p>Nomi delle stringhe di output. </p> <p> Le trasformazioni <span class="wintitle"> IPLookup</span> Quova e <span class="wintitle"> IPLookup</span> Digital Envoy hanno diversi parametri di output. Assicurarsi di utilizzare la trasformazione appropriata per i dati di ricerca IP. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

In questo esempio, [!DNL IP geo-location] i dati (nel file di ricerca [!DNL Quova.bin]) vengono utilizzati per creare i campi di output elencati. Gli output (AOL, ASN, prefisso e così via) possono essere utilizzati per creare dimensioni per l’analisi geografica del traffico dei visitatori.

![](assets/cfg_TransformationType_IPLookup.png)

