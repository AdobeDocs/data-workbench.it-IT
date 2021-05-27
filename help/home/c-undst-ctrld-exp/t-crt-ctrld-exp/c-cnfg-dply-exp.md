---
description: Dopo aver definito l’obiettivo, l’ipotesi e i dettagli dell’esperimento e aver creato il contenuto del test, devi configurare Sensor per implementare l’esperimento controllato.
solution: Analytics,Analytics
title: Configurazione e distribuzione dell’esperimento
uuid: 460d3ea4-a6c8-4ac4-9a3f-eab71f65b096
exl-id: 957c2ea2-72a5-4bb2-af1d-65187613c26d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# Configurazione e distribuzione dell’esperimento{#configuring-and-deploying-the-experiment}

Dopo aver definito l’obiettivo, l’ipotesi e i dettagli dell’esperimento e aver creato il contenuto del test, devi configurare Sensor per implementare l’esperimento controllato.

## Configurazione del file di configurazione dell’esperimento {#section-037fe7dea9c94aee9cdc354dafdb7c03}

Per configurare l’esperimento, devi completare il foglio di calcolo di configurazione dell’esperimento fornito dall’Adobe (denominato [!DNL TestExperiment.xls] per impostazione predefinita). Questo file configura [!DNL Sensor] per eseguire l&#39;esperimento ed è la versione Excel del file di testo specificato in [Modifica del parametro ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

Questo file può contenere informazioni su più esperimenti, che possono essere eseguiti nello stesso momento o in momenti diversi e utilizzare diversi gruppi e percentuali, ma questi esperimenti non sono in alcun modo correlati.

Gli utenti vengono inseriti in un gruppo per ogni esperimento elencato nel file configurato in esecuzione in questo momento.

>[!NOTE]
>
>Ogni esperimento è indipendente da tutti gli altri esperimenti. Le modifiche apportate a un esperimento non influiscono su nessun altro esperimento e, anche se i visitatori possono essere presenti in più esperimenti, i risultati non si riferiscono gli uni agli altri. Se pensi che esista una correlazione tra le modifiche apportate a più esperimenti, devi creare un nuovo esperimento che verifichi queste modifiche insieme.

**Per configurare l&#39;esperimento**

Devi completare questo file prima dell&#39;inizio dell&#39;esperimento e non modificare le informazioni mentre l&#39;esperimento è in esecuzione.

>[!NOTE]
>
>Qualsiasi esperimento è prontamente nullo se la definizione dell&#39;esperimento cambia dopo l&#39;inizio dell&#39;esperimento.

1. Se disponi dell&#39;accesso dell&#39;amministratore ai server Web o applicazioni, passa alla cartella di installazione [!DNL Sensor] in qualsiasi computer [!DNL Sensor] del cluster Web per accedere al file [!DNL TestExperiment.xls]. Se non disponi dell&#39;accesso di amministratore, contatta il tuo account manager Adobe per richiedere il file [!DNL TestExperiment.xls] .

1. Apri il file [!DNL TestExperiment.xls] (se lo desideri puoi rinominare) e completa i campi seguenti:

<table id="table_FDD6AE631C614F97AD7AE8829E53CCAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Esperimento </td> 
   <td colname="col2"> <p>Un nome descrittivo per l'esperimento. Ogni nome di esperimento deve essere univoco e non può contenere spazi. </p> <p>I nomi degli esperimenti vengono utilizzati per visualizzare i risultati degli esperimenti in <span class="keyword"> Insight </span>. I nomi vengono visualizzati come la prima metà dei nomi degli elementi nella dimensione sperimentale controllata. La seconda metà del nome dell'elemento è il nome del gruppo del campo Gruppo in questo file. Ogni gruppo viene denominato nel formato seguente utilizzando il nome dell'esperimento seguito dal nome del gruppo: </p> <p><i>NomeEsperimento.NomeGruppo</i> </p> <p>Ad esempio: <span class="filepath"> New_Homepage.Control </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Inizio </td> 
   <td colname="col2"> <p>Data e ora in cui vuoi che inizi l’esperimento. Se non immetti valori, l’esperimento inizia immediatamente dopo la distribuzione del file. </p> <p>Formato: MM/GG/AAAA H:MM </p> 
    <ul id="ul_FB8B50C688584683AC2226FCBED40AF9"> 
     <li id="li_223EF962CFC64454965444E66284F670">Se lasciate vuoti i tempi di inizio e fine, l'esperimento viene eseguito a tempo indefinito. </li> 
     <li id="li_0544C9A98635418CAECD85B67F345772">È possibile predefinire i tempi di inizio e di arresto con largo anticipo; pertanto, puoi configurare tutti gli esperimenti per l’anno successivo in una sola volta, se lo desideri. </li> 
     <li id="li_BDFBB74B1D134E57B37DC5C3457AA1A9">I tempi di avvio e arresto sono basati sull'ora di sistema del server web. Se l'orologio cambia per qualsiasi motivo, l'esperimento potrebbe iniziare o arrestarsi inaspettatamente. </li> 
     <li id="li_3295FE5B2AC64B6CA90CC7F31B808EB9">Se desideri aggiungere un esperimento come voce di file di configurazione ma non desideri che l'esperimento venga eseguito in un prossimo futuro, puoi commentare le informazioni dell'esperimento utilizzando il simbolo cancelletto "#" oppure definire gli orari di inizio e fine del passato. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stop </td> 
   <td colname="col2"> <p>Data e ora in cui si desidera terminare l'esperimento. Quando si verifica la data e l’ora di arresto, <span class="wintitle"> Sensor </span> smetterà di inviare i valori dei cookie identificati come gruppo di test agli URI del test e invierà tutti i cookie agli URI del gruppo di controllo. </p> <p>Formato: MM/GG/AAAA H:MM </p> <p>Vedere le note del campo <span class="wintitle"> Start </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gruppo </td> 
   <td colname="col2"> <p>Un nome descrittivo per ciascun gruppo di visitatori nell'esperimento. I nomi dei gruppi non possono contenere spazi. </p> <p>I nomi dei gruppi vengono utilizzati per visualizzare i risultati degli esperimenti in <span class="keyword"> Insight </span>. Per ulteriori informazioni, consulta la descrizione del campo Esperimento . </p> <p>Un gruppo di controllo può essere definito in modo implicito o esplicito in base al valore immesso nel campo Percentuale. </p> <p> <p>Nota:  Per soddisfare il numero di visitatori necessari durante il periodo di tempo definito affinché l’esperimento sia statisticamente valido, potrebbe essere necessario ridurre il livello di affidabilità o aumentare il periodo di tempo. Ad esempio, se l’intervallo di tempo è di cinque giorni, il livello di affidabilità è del 98% e il numero di visitatori necessari supera il numero previsto per quel periodo di tempo, è necessario aumentare il periodo di tempo o ridurre il livello di affidabilità fino a quando il numero di visitatori previsto non supera il numero necessario per eseguire un esperimento statisticamente valido. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Percentuale </td> 
   <td colname="col2"> <p>La percentuale di visitatori del sito web da includere in ciascun gruppo definito. Questi valori possono essere espressi come percentuali o come valori decimali. Inoltre, entrambi i valori devono essere maggiori o minori di uno. </p> <p>Ad esempio: </p> <p>33,3% e 66,7% </p> <p>.99 e .01 </p> <p>Se la somma per tutti i gruppi è inferiore a 100, l'eccesso non definito viene impostato automaticamente su un gruppo di controllo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL originale </td> 
   <td colname="col2"> <p>URI del contenuto da rimappare, seguito da $. Questo valore è sensibile a maiuscole e minuscole. </p> <p>Formato: index.asp$ </p> <p>Gli URI originali possono essere specificati utilizzando un simbolo del dollaro ($) alla fine dell’URI per indicare che è necessaria una corrispondenza esatta del nome del file. Ad esempio, l'espressione <span class="filepath"> /product/product_view.asp$ </span> corrisponde solo alla pagina esatta, mentre <span class="filepath"> /product </span> corrisponde a qualsiasi pagina nella directory <span class="filepath"> /product </span> e può essere utilizzata per eseguire il mapping dell'intero sottoalbero. Le voci dell’URL originale che non specificano il carattere $ alla fine del nome del file vengono ignorate dall’esperimento, a meno che il parametro ExpPartialMatch non sia stato impostato su "on". Per ulteriori informazioni su questo parametro, consulta <a href="../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e"> Modifica del parametro ExpPartialMatch (facoltativo) </a>. </p> <p>La funzionalità sperimentale controllata ignora eventuali stringhe di query aggiunte al gambo URI. Ad esempio, la pagina </p> <p> <span class="filepath"> /product/product_view.asp?productid=53982 non  </span> è un URI valido, ma la pagina  <span class="filepath"> /product/product_view.asp  </span> è un URI valido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL rimosso </td> 
   <td colname="col2"> <p>URI del contenuto alternativo. </p> <p>Formato: index2.asp </p> <p>Vedere le note per il campo URL originale. </p> </td> 
  </tr> 
 </tbody> 
</table>

Di seguito è riportato un esempio di foglio di calcolo completato [!DNL TextExperiment.xls]:

![](assets/TestExperimentSpreadsheet.png)

>[!NOTE]
>
>Non modificare le posizioni delle colonne nel foglio di calcolo.

Questo esempio indica che l’esperimento &quot;New_Homepage&quot; inizia il 1° giugno 2006 e termina il 30 giugno 2006 e contiene un gruppo di controllo con il 50% dei visitatori e un gruppo di test con il 50% dei visitatori, che visualizzano contenuti diversi per un URI.

>[!NOTE]
>
>Anche se il file di esempio sopra ha un gruppo di controllo esplicito definito, non è necessario definire esplicitamente un gruppo di controllo: l&#39;esperimento crea automaticamente il gruppo di controllo. Se la somma delle percentuali per tutti i gruppi di un esperimento è inferiore al 100%, un gruppo di controllo implicito viene assegnato agli utenti che non rientrano in uno dei gruppi espliciti.

1. Per inserire commenti per fornire ulteriori informazioni su esperimenti specifici, inizia la cella con un simbolo numerico (#) e segui i tuoi commenti. I commenti possono essere inseriti in qualsiasi punto del file.
1. Dopo aver completato le variabili nel foglio di calcolo per la configurazione dell&#39;esperimento, salva le modifiche, quindi salva il file in formato testo delimitato da tabulazioni ( [!DNL *.txt]) utilizzando il nome specificato nel parametro ExpFile nel file di configurazione [!DNL Sensor]. Vedere [Modifica del parametro ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   Di seguito è riportato un esempio di file di testo di configurazione di un esperimento:

   ![](assets/testexperiment.png)

   >[!NOTE]
   >
   >A causa delle schede richieste in questo file, non modificare manualmente il file di testo della configurazione dell&#39;esperimento. Se devi apportare modifiche al file, apporta le modifiche nel file Excel della configurazione sperimentale e salva nuovamente il file come file di testo delimitato da tabulazioni.

Se hai definito i tempi di avvio e arresto, non c&#39;è motivo di eliminare mai un esperimento dal file di configurazione dell&#39;esperimento. Mantenere tutti gli esperimenti elencati nel file di configurazione dell&#39;esperimento è in realtà un buon modo per tenere traccia di come hai definito ciascuno dei tuoi esperimenti.

## Distribuzione del file di configurazione e del contenuto di test {#section-34ff29649f584b93bc6129b75084b37c}

Devi distribuire il file di configurazione dell&#39;esperimento su ogni computer del cluster web che esegue un [!DNL Sensor] e servire le pagine coinvolte nell&#39;esperimento. È possibile farlo utilizzando una procedura manuale o il sistema di gestione dei contenuti esistente.

**Per distribuire il contenuto del test**

* Su ogni applicazione o server web che esegue un [!DNL Sensor] che serve le pagine coinvolte nell&#39;esperimento, utilizza il processo di pubblicazione esistente per distribuire il contenuto del test nella posizione appropriata.

   Ad esempio, se desideri pubblicare la pagina del gruppo di test [!DNL index2.asp] nella cartella di test del sito web ( [!DNL mysite.com]), devi pubblicare il file in [!DNL www.mysite.com/test].

   >[!NOTE]
   >
   >Non collegare nessuno dei file di test direttamente da una pagina del sito web. In questo modo i risultati dei test e i punteggi dell&#39;indice vengono invalidati.

**Per implementare l&#39;esperimento**

* Su ogni applicazione o server web che esegue un [!DNL Sensor] che serve le pagine coinvolte nell&#39;esperimento, posiziona il file di testo della configurazione sperimentale nella directory specificata nel parametro ExpFile nel file di configurazione [!DNL Sensor]. Vedere [Modifica del parametro ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

[!DNL Sensor] seleziona in modo casuale i visitatori del sito web per ciascun gruppo in base alle percentuali definite nel file e trasmette loro il contenuto del test o del gruppo di controllo, a seconda delle necessità.
