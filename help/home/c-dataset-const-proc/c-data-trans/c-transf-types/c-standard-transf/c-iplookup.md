---
description: La trasformazione IPLookup prende i dati di geolocalizzazione IP o geo-intelligence IP (forniti da qualsiasi venditore di tali dati e convertiti in un formato proprietario per Adobe) e li trasforma in informazioni geografiche che possono essere utilizzate nell'analisi.
title: IPLookup
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
exl-id: 3e9dba44-8d31-49af-8ce0-fecaf92edeb7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 4%

---

# IPLookup{#iplookup}

La trasformazione IPLookup prende i dati di geolocalizzazione IP o geo-intelligence IP (forniti da qualsiasi venditore di tali dati e convertiti in un formato proprietario per Adobe) e li trasforma in informazioni geografiche che possono essere utilizzate nell&#39;analisi.

Nel menu Aggiungi nuova > *Tipo di trasformazione *sono elencate due trasformazioni [!DNL IPLookup]:

* [!DNL IPLookup] Quova per  [!DNL IP geo-location] i dati

* [!DNL IPLookup] Inviato digitale per  [!DNL IP geo-intelligence] i dati

Quando definisci una trasformazione [!DNL IPLookup], scegli la trasformazione appropriata per i dati [!DNL IP geo-location] o [!DNL IP geo-intelligence].

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
   <td colname="col2"> Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commenti </td> 
   <td colname="col2"> Facoltativo. Note sulla trasformazione. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione </td> 
   <td colname="col2"> Le condizioni in cui viene applicata questa trasformazione. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> File </td> 
   <td colname="col2"> Percorso e nome file del file di ricerca. I percorsi relativi riguardano la directory di installazione del server di Data Workbench. Questo file si trova in genere nella directory delle ricerche all’interno della directory di installazione del server di Data Workbench. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo IP </td> 
   <td colname="col2"> Campo da cui leggere l’indirizzo IP. </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uscite </td> 
   <td colname="col2"> <p>Nomi delle stringhe di output. </p> <p> Le trasformazioni <span class="wintitle"> IPLookup</span> Quova e <span class="wintitle"> IPLookup</span> Digital Envoy hanno parametri di output diversi. Assicurati di utilizzare la trasformazione appropriata per i dati di ricerca IP. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

In questo esempio, i dati [!DNL IP geo-location] (nel file di ricerca [!DNL Quova.bin]) vengono utilizzati per creare i campi di output elencati. Gli output (AOL, ASN, prefisso e così via) possono essere utilizzati per creare dimensioni per l’analisi geografica del traffico dei visitatori.

![](assets/cfg_TransformationType_IPLookup.png)
