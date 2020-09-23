---
description: Dopo aver definito l'obiettivo, le ipotesi e i dettagli dell'esperimento e aver creato il contenuto di test, è necessario configurare Sensor per distribuire l'esperimento controllato.
solution: Analytics,Analytics
title: Configurazione e distribuzione dell’esperimento
topic: Data workbench
uuid: 460d3ea4-a6c8-4ac4-9a3f-eab71f65b096
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---


# Configurazione e distribuzione dell’esperimento{#configuring-and-deploying-the-experiment}

Dopo aver definito l&#39;obiettivo, le ipotesi e i dettagli dell&#39;esperimento e aver creato il contenuto di test, è necessario configurare Sensor per distribuire l&#39;esperimento controllato.

## Configurazione del file di configurazione dell’esperimento {#section-037fe7dea9c94aee9cdc354dafdb7c03}

Per configurare l’esperimento, dovete completare il foglio di calcolo di configurazione dell’esperimento fornito da  Adobe (denominato [!DNL TestExperiment.xls] per impostazione predefinita). Questo file si configura [!DNL Sensor] per eseguire l&#39;esperimento ed è la versione Excel del file di testo specificata in [Modifica del parametro](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)ExpFile.

Questo file può contenere informazioni su più esperimenti, che possono essere eseguiti allo stesso tempo o in momenti diversi e utilizzare gruppi e percentuali diversi, ma questi esperimenti non sono in alcun modo correlati.

Gli utenti vengono inseriti in un gruppo per ogni esperimento elencato nel file configurato per l&#39;esecuzione in questa fase.

>[!NOTE]
>
>Ogni esperimento è indipendente da tutti gli altri esperimenti. Le modifiche apportate a un esperimento non influiscono su nessun altro esperimento, e anche se i visitatori possono essere in più esperimenti, i risultati non si riferiscono l’uno all’altro. Se pensate che esista una correlazione tra le modifiche apportate a più esperimenti, dovete creare un nuovo esperimento che sottoponga a test tali modifiche.

**Per configurare l&#39;esperimento**

Completate questo file prima dell&#39;inizio dell&#39;esperimento e non modificate le informazioni durante l&#39;esecuzione dell&#39;esperimento.

>[!NOTE]
>
>Qualsiasi esperimento è immediatamente nullo se la definizione dell&#39;esperimento cambia dopo l&#39;inizio dell&#39;esperimento.

1. Se disponete dell&#39;accesso dell&#39;amministratore ai server Web o applicazione, andate alla cartella di [!DNL Sensor] installazione su qualsiasi [!DNL Sensor] computer del cluster Web per accedere al [!DNL TestExperiment.xls] file. Se non disponete dell&#39;accesso dell&#39;amministratore, contattate il vostro account manager  Adobe per richiedere il [!DNL TestExperiment.xls] file.

1. Aprite il [!DNL TestExperiment.xls] file (se lo desiderate potete rinominare) e completate i seguenti campi:

<table id="table_FDD6AE631C614F97AD7AE8829E53CCAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Sperimentazione </td> 
   <td colname="col2"> <p>Un nome descrittivo per l'esperimento. Ogni nome esperimento deve essere univoco e non può contenere spazi. </p> <p>I nomi degli esperimenti vengono utilizzati per visualizzare i risultati degli esperimenti in <span class="keyword"> Insight </span>. I nomi appaiono come la prima metà dei nomi degli elementi nella dimensione dell'esperimento controllato. La seconda metà del nome dell'elemento è il nome del gruppo dal campo Gruppo in questo file. Ogni gruppo viene denominato nel seguente formato utilizzando il nome dell’esperimento seguito dal nome del gruppo: </p> <p><i>NomeEsperimento.NomeGruppo</i> </p> <p>Ad esempio: <span class="filepath"> New_Homepage.Control </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Inizio </td> 
   <td colname="col2"> <p>Data e ora in cui iniziare l’esperimento. Se non immettete dei valori, l’esperimento ha inizio immediatamente dopo che il file è stato distribuito. </p> <p>Formato: MM/GG/AAAA H:MM </p> 
    <ul id="ul_FB8B50C688584683AC2226FCBED40AF9"> 
     <li id="li_223EF962CFC64454965444E66284F670">Se lasciate vuoti gli orari di inizio e fine, l'esperimento viene eseguito a tempo indeterminato. </li> 
     <li id="li_0544C9A98635418CAECD85B67F345772">È possibile preimpostare l'ora di inizio e di fine con molto anticipo; quindi, potete configurare tutti i vostri esperimenti per il prossimo anno, se lo desiderate. </li> 
     <li id="li_BDFBB74B1D134E57B37DC5C3457AA1A9">I tempi di avvio e arresto sono basati sull'ora del sistema del server Web. Se l'orologio cambia per qualsiasi motivo, l'esperimento potrebbe iniziare o terminare inaspettatamente. </li> 
     <li id="li_3295FE5B2AC64B6CA90CC7F31B808EB9">Se desiderate aggiungere un esperimento come voce di file di configurazione ma non desiderate che l'esperimento venga eseguito in un futuro prossimo, potete aggiungere un commento alle informazioni dell'esperimento utilizzando il simbolo cancelletto "#" o definire gli orari di inizio e di fine del passato. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stop </td> 
   <td colname="col2"> <p>Data e ora in cui si desidera che l’esperimento termini. Quando si verifica la data e l'ora di arresto, <span class="wintitle"> Sensor </span> interrompe l'invio dei valori dei cookie identificati come un gruppo di test agli URI del test e invierà tutti i cookie agli URI del gruppo di controllo. </p> <p>Formato: MM/GG/AAAA H:MM </p> <p>Vedere le note per il <span class="wintitle"> campo Inizio </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gruppo </td> 
   <td colname="col2"> <p>Un nome descrittivo per ciascun gruppo di visitatori nell'esperimento. I nomi dei gruppi non possono contenere spazi. </p> <p>I nomi dei gruppi vengono utilizzati per visualizzare i risultati degli esperimenti in <span class="keyword"> Insight </span>. Per ulteriori informazioni, consultate la descrizione del campo Sperimento. </p> <p>Un gruppo di controllo può essere definito in modo implicito o esplicito in base al valore immesso nel campo Percentuale. </p> <p> <p>Nota:  Per soddisfare il numero di visitatori necessari durante il periodo di tempo definito affinché l'esperimento sia statisticamente valido, potrebbe essere necessario ridurre il livello di confidenza o aumentare il periodo di tempo. Ad esempio, se l’intervallo di tempo è di cinque giorni, il livello di confidenza è del 98% e il numero di visitatori necessari supera il numero previsto per quel periodo di tempo, è necessario aumentare il periodo di tempo o diminuire il livello di confidenza fino a quando il numero di visitatori previsti supera il numero necessario per eseguire un esperimento statisticamente valido. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Percentuale </td> 
   <td colname="col2"> <p>La percentuale di visitatori del sito Web da includere in ciascun gruppo definito. Questi valori possono essere espressi come valori percentuali o decimali. Inoltre, entrambi i valori devono essere maggiori o minori di uno. </p> <p>Ad esempio: </p> <p>33,3% e 66,7% </p> <p>.99 e .01 </p> <p>Se la somma per tutti i gruppi è inferiore a 100, l'eccesso non definito viene impostato per impostazione predefinita su un gruppo di controllo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL originale </td> 
   <td colname="col2"> <p>URI del contenuto da mappare, seguito da $. Questo valore fa distinzione tra maiuscole e minuscole. </p> <p>Formato: index.asp$ </p> <p>Gli URI originali possono essere specificati utilizzando un simbolo di dollaro ($) alla fine dell'URI per indicare che è necessaria una corrispondenza esatta del nome del file. Ad esempio, l'espressione <span class="filepath"> /product/product_view.asp$ </span> corrisponde solo alla pagina esatta, mentre <span class="filepath"> /product </span> corrisponde a qualsiasi pagina nella directory <span class="filepath"> /product </span> e può essere utilizzata per rimappare l'intera sottostruttura. Le voci dell’URL originale che non specificano il carattere $ alla fine del nome del file vengono ignorate dall’esperimento a meno che il parametro ExpPartialMatch non sia stato impostato su "on". Per ulteriori informazioni su questo parametro, consultate <a href="../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e"> Modifica del parametro ExpPartialMatch (facoltativo) </a>. </p> <p>La funzionalità di prova controllata ignora tutte le stringhe di query aggiunte allo stelo URI. Ad esempio, la pagina </p> <p> <span class="filepath"> /product/product_view.asp?productid=53982 </span> non è un URI valido, ma la pagina <span class="filepath"> /product/product_view.asp </span> è un URI valido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL modificato </td> 
   <td colname="col2"> <p>URI del contenuto alternativo. </p> <p>Formato: index2.asp </p> <p>Vedere le note per il campo URL originale. </p> </td> 
  </tr> 
 </tbody> 
</table>

Di seguito è riportato un esempio di [!DNL TextExperiment.xls] foglio di calcolo completato:

![](assets/TestExperimentSpreadsheet.png)

>[!NOTE]
>
>Non modificate le posizioni delle colonne nel foglio di calcolo.

Questo esempio indica che l&#39;esperimento &quot;New_Homepage&quot; inizia il 1° giugno 2006 e termina il 30 giugno 2006, e contiene un gruppo di controllo con il 50% dei visitatori e un gruppo di test con il 50% dei visitatori, che visualizzano contenuti diversi per un URI.

>[!NOTE]
>
>Anche se il file di esempio sopra ha un gruppo di controllo esplicito definito, non è necessario definire esplicitamente un gruppo di controllo — l&#39;esperimento crea automaticamente il gruppo di controllo. Se la somma delle percentuali per tutti i gruppi di un esperimento è inferiore al 100%, un gruppo di controllo implicito viene assegnato agli utenti che non rientrano in uno dei gruppi espliciti.

1. Per inserire commenti per fornire ulteriori informazioni su esperimenti specifici, iniziare la cella con un simbolo cancelletto (#) e seguire i commenti. I commenti possono essere inseriti ovunque nel file.
1. Dopo aver completato le variabili nel foglio di calcolo della configurazione dell’esperimento, salvate le modifiche, quindi salvate il file in formato di testo delimitato da tabulazioni ( [!DNL *.txt]) utilizzando il nome specificato nel parametro ExpFile nel file di [!DNL Sensor] configurazione. See [Modifying the ExpFile Parameter](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   Esempio di un file di testo di configurazione sperimentale:

   ![](assets/testexperiment.png)

   >[!NOTE]
   >
   >A causa delle schede richieste in questo file, non modificate manualmente il file di testo della configurazione dell&#39;esperimento. Se è necessario apportare modifiche al file, apportare le modifiche nel file Excel della configurazione sperimentale e salvare nuovamente il file come file di testo delimitato da tabulazioni.

Se avete definito i tempi di avvio e arresto, non c&#39;è motivo di eliminare un esperimento dal file di configurazione dell&#39;esperimento. Mantenere tutti i vostri esperimenti elencati nel file di configurazione dell&#39;esperimento è in realtà un buon modo per tenere traccia di come avete definito ciascuno dei vostri esperimenti.

## Distribuzione del file di configurazione e del contenuto di prova {#section-34ff29649f584b93bc6129b75084b37c}

Dovete distribuire il file di configurazione dell&#39;esperimento a ogni computer del cluster Web che esegue un test [!DNL Sensor] e gestisce le pagine coinvolte nell&#39;esperimento. È possibile farlo utilizzando una procedura manuale o il sistema di gestione dei contenuti esistente.

**Per distribuire il contenuto di prova**

* Su ogni applicazione o server Web che esegue un server Web [!DNL Sensor] che distribuisce le pagine coinvolte nell’esperimento, utilizzate il processo di pubblicazione esistente per distribuire il contenuto di prova nella posizione appropriata.

   Ad esempio, se desiderate pubblicare la pagina del gruppo di test [!DNL index2.asp] nella cartella di test del sito Web ( [!DNL mysite.com]), pubblicate il file in [!DNL www.mysite.com/test].

   >[!NOTE]
   >
   >Non collegate a nessuno dei file di prova direttamente da una pagina del sito Web. In questo modo i risultati dei test e i punteggi dell&#39;indice vengono invalidati.

**Per distribuire l&#39;esperimento**

* Su ogni applicazione o server Web che esegue un server [!DNL Sensor] che distribuisce le pagine coinvolte nell&#39;esperimento, inserite il file di testo della configurazione dell&#39;esperimento nella directory specificata nel parametro ExpFile nel file di [!DNL Sensor] configurazione. See [Modifying the ExpFile Parameter](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

[!DNL Sensor] seleziona in modo casuale i visitatori del sito Web per ciascun gruppo in base alle percentuali definite nel file e distribuisce loro il contenuto del gruppo di test o di controllo, a seconda delle necessità.
