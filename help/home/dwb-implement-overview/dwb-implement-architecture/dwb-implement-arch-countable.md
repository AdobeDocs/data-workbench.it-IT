---
description: Spiegazione di Countables in Dataworkbench (DWB) per la progettazione e l’implementazione dello schema.
title: Struttura dello schema delle strutture conteggiate
uuid: 2530980d-1c6b-4a96-b9c1-431fc75678bb
exl-id: 4f2a2f8a-7b42-42bb-8ba1-2675ffe6b2c2
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 1%

---

# Struttura dello schema delle strutture conteggiate{#schema-design-countable-structures}

Spiegazione di Countables in Dataworkbench (DWB) per la progettazione e l’implementazione dello schema.

## Comprensione di Countable nella Data Workbench {#section-6e6b8d1c17634d669e62c91a80a0bc62}

Al livello più alto ci sono dimensioni conteggiate. Le dimensioni conteggiate servono due funzioni principali. Innanzitutto, si tratta di dimensioni di cui desideri conteggiare gli elementi. In altre parole, Countables risponde a domande come:

* Quanti visitatori hanno visitato la vostra homepage?

* Quante visite sono venute da Google.com?

`<discoiqbr>`Le dimensioni conteggiate vengono generalmente utilizzate per creare metriche di somma che restituiscono il conteggio o la somma di tutti gli elementi della dimensione. È possibile definire dimensioni numerabili per conteggiare le istanze, ad esempio prenotazioni o ordini di prodotti. Ad esempio, puoi definire gli ordini di dimensioni numerabili i cui elementi (voci di registro corrispondenti agli ordini del tuo negozio online) possono essere conteggiati. Per visualizzare un conteggio degli ordini all’interno di una visualizzazione, definisci la metrica della somma degli ordini, che può essere valutata su una dimensione o a cui sono applicati filtri.

Le dimensioni conteggiate possono essere genitori di altre dimensioni o figli di altre dimensioni conteggiate.

Anche se la dimensione conteggiata principale non deve essere associata agli ID di tracciamento nei dati, Adobe consiglia di configurare la dimensione conteggiata principale del set di dati per utilizzare il campo ID di tracciamento (x-trackingid) come chiave. Di conseguenza, ogni elemento della tabella contabile principale è associato a un valore univoco di x-trackingid e tutti i dati relativi a ciascun elemento sono raggruppati insieme.

Le dimensioni conteggiate sono definite dai seguenti parametri:

<table id="table_5E00B72CFDD645368ADCC25AB9B5E53D"> 
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
   <td colname="col2"> Nome descrittivo della dimensione visualizzato all’utente all’interno di Data Workbench. Il nome della dimensione non può includere un trattino (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Commenti </p> </td> 
   <td colname="col2"> <p>Facoltativo. Note sulla dimensione estesa.

    &lt;/p> &lt;/td>
<td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Condizione </p> </td> 
   <td colname="col2"> <p>Le condizioni alle quali il campo di immissione contribuisce alla creazione della dimensione numerabile. Se specificata, una condizione limita il set di voci di registro visibili alla dimensione e a tutti i relativi elementi secondari nello schema del set di dati. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nascosto </td> 
   <td colname="col2"> Determina se la dimensione viene visualizzata nell’interfaccia di Data Workbench. Per impostazione predefinita, questo parametro è impostato su false. Se, ad esempio, la dimensione deve essere utilizzata solo come base di una metrica, puoi impostare questo parametro su true per nascondere la dimensione dalla visualizzazione di Data Workbench. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chiave </td> 
   <td colname="col2"> <p>Facoltativo. Nome del campo da utilizzare come chiave. Se definisci questo parametro, esiste un elemento della dimensione numerabile per ogni combinazione di un elemento dell'elemento padre della dimensione numerabile e un valore distinto del campo specificato come chiave. </p> <p>Ogni elemento della dimensione numerabile è necessario per riferirsi a un insieme contiguo di voci di registro. Pertanto, se le voci di registro non sono ordinate dalla chiave, viene creato un elemento della dimensione numerabile ogni volta che il campo chiave cambia. Per evitare questa situazione, l’Adobe consiglia di utilizzare una chiave univoca contigua in ordine temporale. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elemento padre </td> 
   <td colname="col2"> <p> Nome della dimensione padre. Qualsiasi dimensione conteggiata può essere una dimensione superiore. Per fare di una dimensione la dimensione di primo livello nello schema del set di dati, imposta il parametro su "root". La dimensione definita diventa la dimensione contabile principale del set di dati. Ad esempio, se lavori con il sito, la dimensione Visitatore è la dimensione conteggiata principale del set di dati. </p> <p>Nota: Anche se la dimensione conteggiata principale non deve essere associata agli ID di tracciamento nei dati, Adobe consiglia di configurare la dimensione conteggiata principale del set di dati per utilizzare il campo ID di tracciamento (x-trackingid) come chiave. Di conseguenza, ogni elemento della tabella contabile principale è associato a un valore univoco di x-trackingid e tutti i dati relativi a ciascun elemento sono raggruppati insieme. Se desideri configurare il set di dati in modo diverso, contatta l’Adobe . </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Questo esempio illustra la definizione di una dimensione numerabile utilizzando i dati evento raccolti dal traffico del sito web. La dimensione numerabile conta gli eventi della campagna web all’interno di una determinata sessione. Il presupposto è che tutte le risorse della campagna e-mail siano richieste dal server web con &quot;email=&quot; come parte di cs-uri-query. Nell’esempio, il numero di volte in cui il visitatore risponde a una campagna e-mail durante una determinata sessione è di interesse e non il valore effettivo del campo cs-uri-query(email) .

![](assets/dwb_impl_arch_1.png)

La seconda funzione principale delle tabelle di conteggio è che formano la spina dorsale della struttura dello schema del set di dati. Lo schema dei dati e tutte le altre dimensioni sono organizzati per essere raggruppati in e appartengono a un conto. In altre parole, se consideriamo le dimensioni come &quot;categorie&quot;, allora le tabelle sono il modo in cui organizziamo queste &quot;categorie&quot; in gruppi.
Quando le dimensioni sono raggruppate sotto una dimensione numerabile, si dice che siano al &quot;livello&quot; della dimensione numerabile. Ad esempio, nella figura seguente puoi vedere che &quot;Indirizzo e-mail&quot; è a livello di Visitatore e &quot;Browser&quot; a livello di Visita. Per &quot;Elemento padre&quot; e &quot;figlio&quot; si intende la relazione tra il numerabile e le dimensioni raggruppate al suo interno. Ad esempio, Visitatore è un &quot;padre&quot; dell’indirizzo e-mail. Al contrario, l’indirizzo e-mail è un &quot;figlio&quot; del visitatore. ![](assets/dwb_impl_arch_2.png) ![](assets/dwb_impl_arch_3.png)

## Creazione di una tabella conteggiata nella Data Workbench {#section-491f3e8e4fbc429e95d6c97f012a208e}

Esegui i seguenti passaggi per creare la tabella conteggiata in Workbench dati:

1. Apri Profile Manager
1. In Cartella di trasformazione, crea un file di configurazione e aprilo nella workstation.
1. In Dimension estesi, fai clic con il pulsante destro del mouse e scegli Aggiungi nuovo -> Contabile come mostrato di seguito: ![](assets/dwb_impl_arch_4.png)

1. Immettere il nome per la nuova tabella conteggiata. Nell’esempio seguente, è definita la tabella dei conteggi dei clienti . Se è il livello più alto conteggiata, allora nella radice di scrittura padre. ![](assets/dwb_impl_arch_5.png)

   Se il Conteggio non è quello di primo livello, assegnare al campo padre il nome della tabella Conteggiata padre. Nell&#39;esempio seguente viene creata la tabella Conteggio di coinvolgimento e il padre per questa tabella numerata è Cliente. ![](assets/dwb_impl_arch_5.png)

Per ulteriori informazioni sull&#39;architettura Data Workbench per la progettazione dello schema, le strutture numerabili e le configurazioni dei feed di dati offline, consulta l&#39; [Interfaccia schema set di dati](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-dtst-sch-intrf.html).
