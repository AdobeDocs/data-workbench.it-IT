---
description: Spiegazione di Countables in Dataworkbench (DWB) per progettare e implementare lo schema.
title: Struttura dello schema Strutture contabili
uuid: 2530980d-1c6b-4a96-b9c1-431fc75678bb
translation-type: tm+mt
source-git-commit: 8b0e9c8855a7c7228393dfab4bf78645f1953794

---


# Struttura dello schema Strutture contabili{#schema-design-countable-structures}

Spiegazione di Countables in Dataworkbench (DWB) per progettare e implementare lo schema.

## Informazioni sulla tabella contabile in Workbench dati {#section-6e6b8d1c17634d669e62c91a80a0bc62}

Al livello più alto ci sono dimensioni numerabili. Le dimensioni contabili sono due funzioni principali. In primo luogo, si tratta di dimensioni di cui si desidera contare gli elementi. In altre parole, countables risponde alle domande come:

* Quanti visitatori hanno visitato la vostra homepage?

* Quante visite sono arrivate da Google.com?

`<discoiqbr>`Le dimensioni contabili vengono in genere utilizzate per creare metriche di somma, che restituiscono il conteggio, o la somma, di tutti gli elementi della dimensione. È possibile definire dimensioni numerabili per contare le istanze, ad esempio prenotazioni o ordini di prodotti. Ad esempio, è possibile definire gli ordini di dimensioni numerabili i cui elementi (voci di registro corrispondenti agli ordini del negozio online) possono essere conteggiati. Se si desidera visualizzare un conteggio di ordini all&#39;interno di una visualizzazione, è possibile definire la metrica della somma degli ordini, che può essere valutata su una dimensione o a cui sono applicati filtri.

Le dimensioni contabili possono essere elementi padre di altre dimensioni o elementi secondari di altre dimensioni computabili.

Anche se la dimensione contabile principale non deve essere associata agli ID di tracciamento nei dati, Adobe consiglia di configurare la dimensione contabile principale del dataset per utilizzare il campo ID di tracciamento (x-trackingid) come chiave. Come risultato, ogni elemento della tabella contabile principale è associato a un valore univoco di x-trackingid, e tutti i dati relativi a ciascun elemento sono raggruppati insieme.

Le dimensioni contabili sono definite dai seguenti parametri:

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
   <td colname="col2"> Nome descrittivo della dimensione che verrà visualizzato all'utente nel workbench dati. Il nome della dimensione non può includere un trattino (-). </td> 
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
   <td colname="col2"> <p>Le condizioni in cui il campo di immissione contribuisce alla creazione della dimensione numerabile. Se specificata, una condizione limita l'insieme di voci di registro visibili alla dimensione e a tutti i relativi elementi secondari nello schema del set di dati. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nascosto </td> 
   <td colname="col2"> Determina se la dimensione viene visualizzata nell'interfaccia workbench dati. Per impostazione predefinita, questo parametro è impostato su false. Se, ad esempio, la dimensione deve essere utilizzata solo come base di una metrica, è possibile impostare questo parametro su true per nascondere la dimensione dalla visualizzazione del workbench dati. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chiave </td> 
   <td colname="col2"> <p>Facoltativo. Nome del campo da utilizzare come chiave. Se si definisce questo parametro, esiste un elemento della dimensione calcolabile per ogni combinazione di un elemento dell'elemento padre della dimensione calcolabile e un valore distinto del campo specificato come chiave. </p> <p>Ogni elemento della dimensione numerabile è necessario per fare riferimento a un insieme contiguo di voci di registro. Pertanto, se le voci di registro non sono ordinate dalla chiave, viene creato un elemento della dimensione numerabile ogni volta che il campo chiave cambia. Per evitare questa situazione, Adobe consiglia di utilizzare una chiave univoca contigua in ordine temporale. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elemento padre </td> 
   <td colname="col2"> <p> Nome della dimensione padre. Qualsiasi dimensione numerabile può essere una dimensione padre. Per fare di una dimensione la dimensione di primo livello nello schema del dataset, impostare il parametro su "root". La dimensione definita diventa la dimensione contabile principale per il dataset. Ad esempio, se lavori con il sito, la dimensione Visitatore è la dimensione contabile principale del set di dati. </p> <p>Nota: Anche se la dimensione contabile principale non deve essere associata agli ID di tracciamento nei dati, Adobe consiglia di configurare la dimensione contabile principale del dataset per utilizzare il campo ID tracciamento (x-trackingid) come chiave. Come risultato, ogni elemento della tabella contabile principale è associato a un valore univoco di x-trackingid, e tutti i dati relativi a ciascun elemento sono raggruppati insieme. Se desiderate configurare il set di dati in modo diverso, contattate Adobe. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Questo esempio illustra la definizione di una dimensione numerabile utilizzando i dati evento raccolti dal traffico del sito Web. La dimensione numerabile conta gli eventi della campagna Web all’interno di una determinata sessione. Si presume che tutte le risorse della campagna e-mail siano richieste dal server Web con &quot;email=&quot; come parte di cs-uri-query. Nell’esempio, il numero di volte in cui il visitatore risponde a una campagna e-mail durante una determinata sessione è di interesse, non il valore effettivo del campo cs-uri-query(email).

![](assets/dwb_impl_arch_1.png)

La seconda funzione principale dei countables è che essi formano la spina dorsale della struttura dello schema del dataset. Lo schema di dati e tutte le altre dimensioni sono organizzati in modo da essere raggruppati e appartengono a una tabella contabile. In altre parole, se consideriamo le dimensioni come &quot;categorie&quot;, allora i conti sono il modo in cui organizziamo queste &quot;categorie&quot; in gruppi.
Quando le dimensioni sono raggruppate sotto una dimensione numerabile, si dice che siano al &quot;livello&quot; della dimensione numerabile. Ad esempio, nella figura seguente è possibile vedere che &#39;Indirizzo e-mail&#39; è a livello di Visitatore e &quot;Browser&quot; a livello di Visita. Per &quot;Elemento padre&quot; e &quot;figlio&quot; si intende la relazione tra la tabella contabile e le dimensioni raggruppate al di sotto. Ad esempio, il visitatore è un &quot;padre&quot; di indirizzo e-mail. Al contrario, l&#39;indirizzo e-mail è un &quot;figlio&quot; del visitatore. ![](assets/dwb_impl_arch_2.png) ![](assets/dwb_impl_arch_3.png)

## Creazione di una tabella contabile in Workbench dati {#section-491f3e8e4fbc429e95d6c97f012a208e}

Per creare la tabella Contabile in Workbench dati, procedere come segue:

1. Open Profile Manager
1. In Cartella Trasformazione, create un file di configurazione e apritelo nella workstation.
1. In Dimensioni estese, fai clic con il pulsante destro del mouse e scegli Aggiungi nuovo -> Contabile come mostrato di seguito: ![](assets/dwb_impl_arch_4.png)

1. Immettere il nome per la nuova tabella contabile. Nell&#39;esempio seguente, è definita la tabella Conteggio clienti. Se si tratta del Contabile di livello più alto, nel Livello padre scrivi Radice. ![](assets/dwb_impl_arch_5.png)

   Se il Contabile non è il primo livello, nel campo padre assegnare il nome della Contabile padre. Nell&#39;esempio seguente, viene creata la tabella Conteggio coinvolgimento e il padre per la tabella contabile è Cliente. ![](assets/dwb_impl_arch_5.png)

Per ulteriori informazioni sull&#39;architettura del workbench dati per la progettazione dello schema, le strutture calcolabili e le configurazioni del feed di dati offline, vedere l&#39;interfaccia [Schema](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-dtst-sch-intrf.html)DataSet.
