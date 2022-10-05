---
description: Il server di Data Workbench (InsightServer64.exe) può leggere i dati evento da qualsiasi database SQL (ad esempio, Oracle o Microsoft SQL Server) con un driver compatibile ODBC 3.0.
title: Origini dati ODBC
uuid: 5b37cd41-2d79-472c-8e6d-00ff894991a9
exl-id: b22b1e27-9b6c-4708-b45c-a9605807689a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 1%

---

# Origini dati ODBC{#odbc-data-sources}

{{eol}}

Il server di Data Workbench (InsightServer64.exe) può leggere i dati evento da qualsiasi database SQL (ad esempio, Oracle o Microsoft SQL Server) con un driver compatibile ODBC 3.0.

Il supporto ODBC del server di Data Workbench è simile al supporto esistente per il caricamento di dati da Sensor o da file di registro generati da processi esterni. Esistono tuttavia alcune considerazioni e limitazioni aggiuntive:

* Il supporto ODBC del server di Data Workbench è compatibile con le funzionalità di clustering. I dati vengono distribuiti tra tutti i server di elaborazione e tutte le successive elaborazioni (compresa l’elaborazione delle query) beneficiano del clustering.
* Il supporto ODBC dipende da driver ODBC di terze parti. Affinché il supporto ODBC funzioni, questi driver devono essere configurati sul computer sul quale viene eseguito il server di Data Workbench, utilizzando strumenti esterni alla piattaforma Adobe. Le macchine Data Workbench non richiedono alcuna configurazione aggiuntiva.
* La tabella o la visualizzazione da cui vengono caricati i dati deve avere una colonna ID crescente. Per qualsiasi riga, il valore in questa colonna (che può essere una colonna effettiva nella tabella o in qualsiasi espressione di colonna SQL) non deve diminuire quando vengono inserite nuove righe nel database. Se questo vincolo viene violato, i dati vengono persi. Per prestazioni adeguate, è necessario un indice in questa espressione di colonna o colonna.

   >[!NOTE]
   >
   >È possibile che più righe abbiano lo stesso valore nel [!DNL Increasing ID] colonna. Una possibilità è una colonna timestamp con una precisione inferiore a quella perfetta.

* Il server di Data Workbench non è in grado di caricare colonne con dati lunghi (dati di lunghezza superiore a quella determinata dall’applicazione di database specifica in uso).
* Il recupero dei dati da un database è più lento della lettura da un file disco. I set di dati che caricano dati da un&#39;origine ODBC richiedono molto più tempo per l&#39;elaborazione (in particolare durante la rielaborazione) rispetto ai set di dati di dimensioni equivalenti i cui dati provengono da Sensor o da altri file disco.

Per informazioni sulla rielaborazione dei dati, consulta [Rielaborazione e ritrasformazione](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

**Per configurare Insight Server per ODBC[!DNL event data]**

La configurazione del server di Data Workbench per caricare dati da un database SQL richiede prima di tutto di eseguire i seguenti passaggi nell’ordine seguente:

1. Installare il software client di database appropriato, incluso un driver ODBC, nel computer server di Data Workbench in cui viene elaborato il set di dati.

   >[!NOTE]
   >
   >Se si stanno caricando dati evento ODBC per l’elaborazione su un cluster di server di Data Workbench, è necessario installare il software client di database su tutti i server di elaborazione del cluster. Per informazioni sulla specifica dei server di elaborazione in un cluster, consulta la *Guida all’installazione e all’amministrazione dei prodotti server*.

1. Configurare un&#39;origine dati utilizzando Amministratore origine dati ODBC per Windows.

   È importante notare che il server di Data Workbench (InsightServer64.exe) viene eseguito come servizio Windows. Di conseguenza, per poter essere utilizzato dal server di Data Workbench, l’origine dati deve essere configurata come DSN di sistema anziché come DSN utente. Per ulteriori informazioni su questo passaggio di configurazione, consulta la documentazione relativa al software del database.

Dopo aver installato il software client del database sul computer server di Data Workbench appropriato, è possibile configurare il set di dati per utilizzare l’origine dati ODBC modificando i parametri appropriati nel [!DNL Log Processing] file di configurazione per il profilo desiderato.

## Parametri {#section-15c0218d93364693a565f2609a12f73e}

Per i dati provenienti da database che utilizzano lo standard ODBC (Open Database Connectivity), sono disponibili i seguenti parametri:

<table id="table_606D8A90DA4A43C29F2C6130F8C753F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Identificatore dell'origine ODBC. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome origine dati </td> 
   <td colname="col2"> Un DSN, fornito da un amministratore del computer server di Data Workbench su cui viene elaborato il set di dati, che fa riferimento al database da cui devono essere caricati i dati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Password database </td> 
   <td colname="col2"> Password da utilizzare per la connessione al database. Se è stata configurata una password per il DSN nel <span class="wintitle"> Amministratore origine dati</span>, potrebbe essere lasciato vuoto. Qualsiasi password fornita in questo caso sostituisce la password configurata per il DSN nel <span class="wintitle"> Amministratore origine dati</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID utente database </td> 
   <td colname="col2"> ID utente da utilizzare per la connessione al database. Se è stato configurato un ID utente per il DSN in <span class="wintitle"> Amministratore origine dati</span>, potrebbe essere lasciato vuoto. Qualsiasi ID utente fornito qui si sovrappone all’ID utente configurato per il DSN nel <span class="wintitle"> Amministratore origine dati</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campi </td> 
   <td colname="col2"> Vettore di oggetti colonna che specifica una mappatura dalle colonne di dati nel database ai campi di dati nel motore di esecuzione del server di Data Workbench. Ogni colonna contiene voci <span class="wintitle"> Nome colonna</span> e <span class="wintitle"> Nome campo</span>. <span class="wintitle"> Nome colonna</span> è un'espressione di colonna SQL che deve essere valida nel contesto della tabella identificata da <span class="wintitle"> Identificatore tabella</span> descritto sopra. Può essere un nome di colonna o un'espressione SQL basata su un numero qualsiasi di colonne nella tabella. Potrebbe essere necessaria una funzione di formattazione per convertire i valori di determinati tipi di dati in stringhe in modo da non perdere precisione. Tutti i dati vengono convertiti in modo implicito in stringhe utilizzando il metodo di formattazione predefinito del database, il che potrebbe causare la perdita di dati per alcuni tipi di dati di colonna (ad esempio i tipi di dati data/ora) se non vengono utilizzate espressioni di formattazione esplicite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aumento della colonna ID </td> 
   <td colname="col2"> <p>Un nome di colonna o un'espressione di colonna SQL che soddisfa il criterio che aumenta (o almeno non diminuisce) quando vengono aggiunte nuove righe. In altre parole, se la riga B viene aggiunta alla tabella in un momento successivo alla riga A, il valore di questa colonna (o espressione di colonna) nella riga B deve essere maggiore (in base all’ordinamento nativo del database) del valore corrispondente nella riga A. </p> <p> 
     <ul id="ul_EBF6AEE4746B41B3B5BB6CC74194DAED"> 
      <li id="li_A5C9BE52B01649DE9726ECEC68B99828"> La <span class="wintitle"> Aumento della colonna ID </span>può essere lo stesso del nome di una colonna esistente, ma non è obbligatorio. </li> 
      <li id="li_CF69EAB4AFB14F4894F7A5CDCAF06947"> Si presume che questa espressione abbia un tipo di dati carattere SQL. Se la colonna ID incrementale effettiva è di un altro tipo di dati, questo valore deve essere un'espressione di colonna per convertirlo in una stringa. Poiché in genere i confronti sono lessicografici (carattere per carattere), è importante formattare attentamente il valore. </li> 
      <li id="li_58977431962E48039C898CFC47C53323"> L'espressione viene utilizzata nelle clausole SQL ORDER BY e confrontata con le clausole SQL WHERE. È importante disporre di un indice basato sull'espressione di colonna esatta utilizzata. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID origine registro </td> 
   <td colname="col2"> <p>Il valore di questo parametro può essere una qualsiasi stringa. Se viene specificato un valore, questo parametro consente di distinguere le voci di registro da diverse origini di registro per l'identificazione dell'origine o l'elaborazione mirata. Il campo x-log-source-id viene compilato con un valore che identifica l'origine del registro per ogni voce di registro. Ad esempio, se si desidera identificare le voci di registro da un'origine ODBC denominata ODBCSource01, è possibile digitare <span class="filepath"> da ODBCSource01.</span> e quella stringa verrebbe passata al campo x-log-source-id per ogni voce di registro da tale origine. </p> <p> Per informazioni sul campo x-log-source-id, vedi <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Campi record dati evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Esegui sul server </td> 
   <td colname="col2"> Valore di indice nel <span class="filepath"> profile.cfg</span> file del server di elaborazione che esegue le query ODBC per ottenere i dati dal database. (Il parametro Server di elaborazione nel <span class="filepath"> profile.cfg</span> file elenca tutti i server di elaborazione per il set di dati e ogni server ha un valore di indice, il primo è 0.) Il valore predefinito è 0. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Identificatore tabella </td> 
   <td colname="col2"> Espressione SQL che denomina la tabella o la visualizzazione da cui devono essere caricati i dati. Un identificatore di tabella tipico è costituito dal modulo SCHEMA.TABLE. </td> 
  </tr> 
 </tbody> 
</table>

Questo esempio mostra la [!DNL Log Processing] finestra di configurazione in Data Workbench con un’origine dati ODBC. Questa origine dati prende i dati da una tabella denominata [!DNL VISUAL.VSL] in un database con [!DNL Data Source Name] &quot;VSTestO.&quot; Cinque (5) oggetti colonna ( [!DNL Fields]) mappare i dati dalle colonne di dati del database al server di Data Workbench.

![](assets/cfg_LogProcessing_LogSources_ODBC.png)
