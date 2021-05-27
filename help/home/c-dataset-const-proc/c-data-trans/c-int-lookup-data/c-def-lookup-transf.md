---
description: Informazioni sulle trasformazioni che è possibile utilizzare per incorporare i dati di ricerca nel set di dati.
title: Definizione delle trasformazioni di ricerca
uuid: 4f7358b1-9e6a-4d03-b0c6-411e454fc11e
exl-id: 7b1504be-8669-4340-8400-e33f9663b602
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2288'
ht-degree: 2%

---

# Definizione delle trasformazioni di ricerca{#defining-lookup-transformations}

Informazioni sulle trasformazioni che è possibile utilizzare per incorporare i dati di ricerca nel set di dati.

Tieni presente che non tutti i tipi possono essere utilizzati durante entrambe le fasi del processo di costruzione del set di dati.

* [Categorizzare](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-8474376c14e54d14ae73749696ada468)
* [RicercaFileFlat](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-e09b2eeb96444a859b14f03cdaab31f2)
* [ODBCLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-4dcc3747e42e45c0a057e85f308a83cc)

## Categorizzare {#section-8474376c14e54d14ae73749696ada468}

La trasformazione [!DNL Categorize] utilizza una tabella di ricerca a due colonne composta da coppie stringa-pattern/valore. Durante questa trasformazione, il server di Data Workbench legge a turno ogni record di dati evento e confronta il contenuto di un campo designato nel record con ciascuna delle stringhe del pattern elencate nella prima colonna della tabella di ricerca. Se il campo designato corrisponde a una delle stringhe del pattern, il server di Data Workbench scrive il valore (trovato nella seconda colonna) associato a tale stringa del pattern in un campo di output designato nel record.

Facoltativamente, le stringhe nella prima colonna della tabella di ricerca possono iniziare con il carattere ^ e/o terminare nel carattere $ per forzare la corrispondenza all&#39;inizio e/o alla fine. Questa trasformazione non accetta espressioni regolari per la definizione delle condizioni di corrispondenza nella prima colonna. Se il valore di input è un vettore di stringhe, ogni stringa viene eseguita attraverso la trasformazione e i risultati vengono aggiunti a un vettore di stringa di output.

Una trasformazione [!DNL Categorize] è generalmente più semplice e veloce che utilizzare una trasformazione [!DNL Regular Expression] per eseguire la stessa operazione.

>[!NOTE]
>
>Il test della sottostringa utilizzato in [!DNL Categorize] distingue tra maiuscole e minuscole, se non diversamente specificato utilizzando il parametro [!DNL Case Sensitive] .

<table id="table_1773344FAAE34BD4919CC4414249FDEE"> 
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
   <td colname="col1"> Distintivo tra maiuscole e minuscole </td> 
   <td colname="col2"> True o false. Specifica se il test della sottostringa fa distinzione tra maiuscole e minuscole. </td> 
   <td colname="col3"> true </td> 
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
   <td colname="col1"> impostazione predefinita </td> 
   <td colname="col2"> Il valore predefinito da utilizzare se il test della condizione viene superato e nessuna voce nel file di categorizzazione corrisponde all'input oppure se il campo di input non è definito nella voce di registro specificata. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimitatore </td> 
   <td colname="col2"> <p>Stringa utilizzata per separare le colonne nel file di ricerca. Deve essere un singolo carattere di lunghezza. </p> <p> Se tieni premuto il tasto Ctrl e fai clic con il pulsante destro del mouse all'interno del parametro Delimitatore , viene visualizzato un menu <span class="wintitle"> Inserisci</span> . Questo menu contiene un elenco di caratteri speciali che vengono spesso utilizzati come delimitatori. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori multipli </td> 
   <td colname="col2"> True o false. Se true, quando più righe del file corrispondono all’input, ciascuna corrispondenza determina l’aggiunta di un valore al vettore di output delle stringhe. Se false, nell’output viene utilizzata solo la prima riga corrispondente nel file. In quest’ultimo caso, se l’input è un vettore, l’output è anche un vettore di lunghezza equivalente. Se l'input è una stringa semplice, anche l'output è una stringa semplice. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> File </td> 
   <td colname="col2"> Percorso e nome file del file di classificazione. I percorsi relativi riguardano la directory di installazione del server di Data Workbench. Questo file si trova in genere nella directory delle ricerche all’interno della directory di installazione del server di Data Workbench. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresso </td> 
   <td colname="col2"> Il file di classificazione corrisponde alle relative sottostringhe rispetto al valore in questo campo per identificare la riga corrispondente nel file. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uscita </td> 
   <td colname="col2"> Nome del campo associato al risultato. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Considerazioni per categorizzare**

* Le modifiche ai file di ricerca nelle trasformazioni [!DNL Categorize] definite nel file [!DNL Transformation.cfg] o in un file [!DNL Transformation Dataset Include] richiedono la riconversione del set di dati. I file di ricerca per le trasformazioni [!DNL Categorize] definite nel file [!DNL Log Processing.cfg] o in un file [!DNL Log Processing Dataset Include] non sono soggetti a questa limitazione. Per informazioni sulla rielaborazione dei dati, vedere [Rielaborazione e ritrasformazione](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL Categorize] le trasformazioni definite nel  [!DNL Log Processing.cfg] file o in un  [!DNL Log Processing Dataset Include] file ricaricano i loro file di ricerca ogni volta che i file di ricerca cambiano. Le modifiche non vengono applicate retroattivamente, ma si applicano a tutti i dati di registro letti dopo la modifica.

Questo esempio illustra l’utilizzo della trasformazione [!DNL Categorize] per integrare i dati di ricerca con i dati evento raccolti dal traffico del sito web. Supponiamo che un particolare sito web abbia sezioni aziendali e che vi sia l&#39;obbligo di essere in grado di guardare e fare confronti in base al flusso di traffico e al valore generato dalle diverse sezioni. È possibile creare un file di ricerca in cui sono elencate le sottostringhe utilizzate per identificare queste diverse sezioni.

Il file di ricerca [!DNL Lookups\custommap.txt] contiene la tabella seguente:

| /products/ | Prodotti |
|---|---|
| ^/sport/ | Sport |
| ^/news/ | News |
| ... | ... |

Questo file di categorizzazione mappa tutto ciò che contiene la stringa &quot;/products/&quot; al valore &quot;Products&quot;, qualsiasi cosa che inizia con &quot;/sports/&quot; al valore &quot;Sports&quot;, e qualsiasi cosa che inizia con &quot;/news/&quot; al valore &quot;News&quot;. La seguente trasformazione di categorizzazione utilizza il valore nel campo cs-uri-stem come stringa all&#39;interno della quale stiamo cercando una sottostringa corrispondente. Il risultato della trasformazione viene inserito nel campo x-custommap.

![](assets/cfg_TransformationType_Categorize.png)

Presupponendo che il parametro Valori multipli sia impostato su false, l&#39;esempio produrrà i seguenti valori per x-custommap in base ai valori elencati per cs-uri-stem.

| [!DNL cs-uri-stem] | [!DNL x-custommap] |
|---|---|
| [!DNL /sports/news/today.php] | Sport |
| [!DNL /sports/products/buy.php] | Prodotti |
| [!DNL /news/headlines.php] | News |
| [!DNL /news/products/subscribe.php] | Prodotti |

L’output si basa sull’ordine delle sottostringhe nel file di ricerca. Ad esempio, cs-uri-stem [!DNL /sports/products/buy.php] restituisce &quot;Products&quot;. Anche se il fusto URI inizia con &quot;/sports/,&quot; la stringa &quot;/products/&quot; è elencata prima di &quot;/sports/&quot; nel file di ricerca. Se il parametro Valori multipli fosse impostato su true, ci sarebbe un valore aggiuntivo per x-custommap, in quanto l&#39;ultimo esempio corrisponderebbe a due righe nella tabella di ricerca: Prodotti e notizie.

## RicercaFileFlat {#section-e09b2eeb96444a859b14f03cdaab31f2}

La trasformazione [!DNL FlatFileLookup] utilizza una tabella di ricerca composta da un numero qualsiasi di colonne e righe (anche se, ricorda che risiede nella memoria). Durante questo tipo di trasformazione, il server di Data Workbench legge a turno ogni record di dati evento e confronta il contenuto di un campo designato nel record con ciascuno dei valori in una colonna designata della tabella di ricerca. Se esiste una corrispondenza, il server di Data Workbench scrive uno o più valori dalla riga corrispondente nella tabella di ricerca in uno o più campi di output designati nel record di dati dell’evento.

La tabella di ricerca utilizzata durante questa trasformazione viene compilata da un file flat la cui posizione viene specificata quando si definisce la trasformazione.

<table id="table_772B8ABF3B44493F99069010DDB5F77A"> 
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
   <td colname="col1"> impostazione predefinita </td> 
   <td colname="col2"> Il valore predefinito da utilizzare se la condizione è soddisfatta e se nessuna voce nel file di ricerca corrisponde all’input. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimitatore </td> 
   <td colname="col2"> <p>Stringa utilizzata per separare le colonne nel file di ricerca. Deve essere un singolo carattere di lunghezza. </p> <p> Se tieni premuto il tasto Ctrl e fai clic con il pulsante destro del mouse all'interno del parametro Delimitatore , viene visualizzato un menu <span class="wintitle"> Inserisci</span> . Questo menu contiene un elenco di caratteri speciali che vengono spesso utilizzati come delimitatori. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> File </td> 
   <td colname="col2"> Percorso e nome file del file di ricerca. I percorsi relativi riguardano la directory di installazione del server di Data Workbench. Questo file si trova in genere nella directory delle ricerche all’interno della directory di installazione del server di Data Workbench. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Riga di intestazione </td> 
   <td colname="col2"> True o false. Indica che la prima riga della tabella è una riga di intestazione da ignorare durante l’elaborazione. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresso </td> 
   <td colname="col2"> <span class="wintitle"> Nome colonna </span> è il nome della colonna utilizzata per associare l’input alle righe nel file. Se Riga di intestazione è true, può essere il nome di una colonna nel file di ricerca. In caso contrario, deve essere il numero di colonna basato su zero a cui confrontarsi. <span class="wintitle"> Nome campo </span> è il nome del campo utilizzato per individuare la riga nel file di ricerca. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori multipli </td> 
   <td colname="col2"> <p>True o false. Determina se restituire un singolo valore (una riga corrispondente) o più valori (uno per ogni riga corrispondente). </p> <p> <p>Nota:  Se <span class="wintitle"> Multiple Values</span> è impostato su false, assicurati che non siano presenti più corrispondenze. Quando si verificano più corrispondenze, non esiste alcuna garanzia che la corrispondenza venga restituita. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uscite </td> 
   <td colname="col2"> <p>Un vettore di oggetti colonna (risultati) in cui ogni oggetto è definito dai nomi di colonna e di campo. </p> <p> <span class="wintitle"> Nome colonna </span> è la colonna da cui viene ottenuto il valore di output. Se <span class="wintitle"> Riga di intestazione</span> è true, può essere il nome di una colonna nel file di ricerca. In caso contrario, deve essere il numero di colonna basato su zero a cui confrontarsi. </p> <p> <span class="wintitle"> Nome campo </span> è il nome del campo utilizzato per acquisire l’output. Tieni presente che può essere un vettore di risultati, uno per ogni riga identificata nel caso in cui il parametro Valori multipli sia true. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Considerazioni per[!DNL FlatFileLookup]**

* La corrispondenza del campo di input al file di ricerca è sempre sensibile a maiuscole e minuscole.
* Le modifiche ai file di ricerca nelle trasformazioni [!DNL FlatFileLookup] definite nel file [!DNL Transformation.cfg] o nei file [!DNL Transformation Dataset Include] richiedono la riconversione del set di dati. I file di ricerca per le trasformazioni [!DNL FlatFileLookup] definite nel file [!DNL Log Processing.cfg] o nei file [!DNL Log Processing Dataset Include] non sono soggetti a questa limitazione. Per informazioni sulla rielaborazione dei dati, vedere [Rielaborazione e ritrasformazione](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL FlatFileLookup] le trasformazioni nel  [!DNL Log Processing.cfg] file o nei  [!DNL Log Processing Dataset Include] file ricaricano i file di ricerca ogni volta che i file di ricerca cambiano. Le modifiche non vengono applicate retroattivamente, ma si applicano a tutti i dati di registro letti dopo la modifica.

Questo esempio illustra l’utilizzo della trasformazione [!DNL FlatFileLookup] per integrare i dati di ricerca con i dati evento raccolti dal traffico del sito web. Supponi di voler isolare i partner del sito web che indirizzano il traffico al sito web e trasformare i loro ID partner in nomi più user-friendly. Puoi quindi utilizzare i nomi descrittivi per creare dimensioni estese e visualizzazioni che si associano in modo più chiaro alla relazione di business rispetto alla relazione sito-to-sito utilizzata per il traffico di indirizzamento.

La trasformazione di esempio cerca il campo cs(referrer-query) per la coppia nome-valore PartnerID e, se disponibile, il file di ricerca [!DNL Lookups\partners.txt] viene utilizzato per confrontare il valore PartnerID rispetto ai valori nella colonna [!DNL Partner] della tabella. Se si trova una riga, al campo di output x-partner-name viene assegnato il nome dalla colonna [!DNL PrintName] della riga identificata.

![](assets/cfg_TransformationType_FlatFileLookup.png)

Se la tabella di ricerca conteneva le seguenti informazioni:

| ID | Partner | Avviato | NomeStampa |
|---|---|---|---|
| 1 | P154 | 21 agosto 1999 | Yahoo |
| 2 | P232 | 10 luglio 2000 | Microsoft |
| 3 | P945 | 12 gennaio 2001 | Amazon |

Gli esempi seguenti vengono trasformati come segue:

* Se cs(referrer)(PartnerID) ha restituito P232, al campo x-partner-name verrà assegnato il valore &quot;Microsoft&quot;.
* Se cs(referrer)(PartnerID) restituisce P100, al campo x-partner-name verrà assegnato il valore &quot;No Partner&quot;.
* Se cs(referrer)(PartnerID) non ha restituito nulla, al campo x-partner-name verrà assegnato il valore &quot;No Partner&quot; come specificato dal parametro Predefinito.

## ODBCLookup {#section-4dcc3747e42e45c0a057e85f308a83cc}

La trasformazione [!DNL ODBCLookup] funziona come una trasformazione [!DNL FlatFileLookup]. L&#39;unica differenza è che la tabella di ricerca utilizzata durante questa trasformazione viene compilata da un database ODBC e non da un file flat.

>[!NOTE]
>
>[!DNL ODBCLookup] le trasformazioni possono essere eseguite solo durante la fase di trasformazione del processo di costruzione del set di dati. Quando possibile, Adobe consiglia di utilizzare la trasformazione [!DNL FlatFileLookup] invece della trasformazione [!DNL ODBCLookup]. [!DNL FlatFileLookup] Le trasformazioni sono intrinsecamente più affidabili perché non dipendono dalla disponibilità di un sistema esterno. Inoltre, esiste un rischio minore che la tabella di ricerca venga modificata se si trova in un file flat controllato localmente.

<table id="table_B903DB291BCC4F44B09D54300216D288"> 
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
   <td colname="col1"> Nome origine dati </td> 
   <td colname="col2"> Un DSN, fornito da un amministratore del computer server di Data Workbench su cui viene elaborato il set di dati, che fa riferimento al database da cui devono essere caricati i dati. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Password database </td> 
   <td colname="col2">Password da utilizzare per la connessione al database. Se è stata configurata una password per il DSN in <span class="wintitle"> Data Source Administrator</span>, questa potrebbe essere lasciata vuota. Qualsiasi password fornita qui sostituisce la password configurata per il DSN in <span class="wintitle"> Data Source Administrator</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID utente database </td> 
   <td colname="col2">ID utente da utilizzare per la connessione al database. Se un ID utente è stato configurato per il DSN in <span class="wintitle"> Data Source Administrator</span>, può essere lasciato vuoto. Qualsiasi ID utente fornito qui sostituisce l'ID utente configurato per il DSN in <span class="wintitle"> Data Source Administrator</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> impostazione predefinita </td> 
   <td colname="col2"> Il valore predefinito da utilizzare se la condizione è soddisfatta e nessuna voce nel file di ricerca corrisponde all’input. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonna di input </td> 
   <td colname="col2"> <span class="wintitle"> Nome colonna </span> è il nome della colonna o l’espressione SQL per i dati corrispondenti all’input. <span class="wintitle"> Nome campo </span> è il nome del campo contenente i dati da cercare. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori multipli </td> 
   <td colname="col2"> <p>True o false. Determina se restituire un singolo valore (una riga corrispondente) o più valori (uno per ogni riga corrispondente). </p> <p> <p>Nota:  Se <span class="wintitle"> Multiple Values</span> è impostato su false, assicurati che non siano presenti più corrispondenze. Quando si verificano più corrispondenze, non esiste alcuna garanzia che la corrispondenza venga restituita. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colonne di uscita </td> 
   <td colname="col2"> <p>Un vettore di oggetti colonna (risultati) in cui ogni oggetto è definito dai nomi di colonna e di campo. </p> <p> <span class="wintitle"> Nome colonna </span> è il nome dell'espressione o SQL per la colonna da cui viene ottenuto il valore di output. <span class="wintitle"> Nome campo </span> è il nome del campo utilizzato per acquisire l’output. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Identificatore tabella</span> </td> 
   <td colname="col2"> Espressione SQL che denomina la tabella o la visualizzazione da cui devono essere caricati i dati. Un identificatore di tabella tipico è costituito dal modulo SCHEMA.TABLE. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

* I parametri Nome origine dati, [!DNL Database User ID], [!DNL Database Password] e Identificatore tabella sono gli stessi dei parametri degli stessi nomi descritti per le origini dati ODBC. Vedere [Origini dati ODBC](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

* A differenza delle origini dati ODBC, le trasformazioni [!DNL ODBCLookup] non richiedono una colonna ID crescente. Vedere [Origini dati ODBC](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3). Questo perché il contenuto della tabella di ricerca non deve essere modificato in alcun modo mentre il set di dati è attivo. Le modifiche in una tabella o in una vista di ricerca non possono essere rilevate fino a quando non si verifica una riconversione. Per informazioni sulla rielaborazione dei dati, vedere [Rielaborazione e ritrasformazione](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

Si supponga di voler convertire i record DNS obsoleti nei record aggiornati. Entrambi i set di record sono archiviati in un database SQL. Per eseguire questa attività, fare riferimento a una tabella di ricerca generata dal database e sostituire i record DNS obsoleti.

La trasformazione del nostro esempio cerca le voci di log per il campo s-dns e, se si trova, la tabella di ricerca VISUAL.LOOKUP viene utilizzata per confrontare la voce s-dns rispetto alle voci nella colonna [!DNL OLDDNS] della tabella. Se una riga si trova nella tabella, al campo di output s-dns viene assegnata la voce di record DNS aggiornata dalla colonna [!DNL NEWDNS] della riga identificata.

![](assets/cfg_TransformationType_ODBCLookup.png)
