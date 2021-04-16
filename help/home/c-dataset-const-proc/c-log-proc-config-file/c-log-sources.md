---
description: Le origini di registro sono file che contengono i dati da utilizzare per creare un set di dati.
title: Origini del registro
uuid: ea21c3d7-9188-4ba8-bacd-052d678bd799
exl-id: 36e0799b-197d-4c59-84ae-7a4350584ab1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '3664'
ht-degree: 1%

---

# Origini del registro{#log-sources}

Le origini di registro sono file che contengono i dati da utilizzare per creare un set di dati.

I dati disponibili nelle origini di registro sono chiamati dati evento perché ogni record di dati rappresenta un record di transazione o una singola istanza di un evento. Il server di Data Workbench può elaborare le origini di registro derivate dai dati raccolti da [!DNL Sensors] o estratti da altre origini dati.

* **Dati raccolti da [!DNL Sensors]: ** I dati raccolti da [!DNL Sensors] dai server HTTP e applicativi vengono trasmessi ai server di Data Workbench, che convertono i dati in file di log ( [!DNL .vsl]) altamente compressi. Consulta [File di sensore](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009).

* **Dati estratti da Insight Server:** il server di Data Workbench legge i dati evento contenuti in file flat, file XML o database conformi a ODBC e utilizza i relativi decoder per estrarre gli elementi desiderati dei dati. Tali dati dell’evento non devono necessariamente risiedere nella memoria, ma i record che contengono i dati devono includere un ID di tracciamento. Vedere [File di registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e), [Sorgenti di registro XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887) e [Origini dati ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

**Per aggiungere un’origine di registro**

1. Apri [!DNL Log Processing.cfg] in Data Workbench.
1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Log Sources]**, quindi fai clic su **[!UICONTROL Add New]**.

1. Seleziona una delle seguenti opzioni:

   * **[!UICONTROL Sensor]**
   * **[!UICONTROL Log File]**
   * **[!UICONTROL XML Log Source]**
   * **[!UICONTROL ODBC Data Source]**

1. I parametri specifici utilizzati per definire un set di dati variano in base al tipo di origine del registro da utilizzare nel processo di configurazione del set di dati. Specifica i parametri come indicato nella sezione corrispondente all’origine di registro appropriata:

   * [File sensore](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)
   * [File di registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)
   * [Sorgenti di log XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)
   * [Origini dati ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)

1. Dopo aver definito l’origine del registro (e apportato modifiche ad altri parametri) nel file [!DNL Log Processing.cfg], salva il file localmente e salvalo nel profilo del set di dati sul server di Data Workbench.

   >[!NOTE]
   >
   >Un server di Data Workbench [!DNL File Server Unit] può ricevere e memorizzare [!DNL Sensor] file, file di registro e file XML e distribuirli sul server di Data Workbench [!DNL Data Processing Units] che crea il set di dati. Consultare [Configurazione di un&#39;unità del file server di Insight Server](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d).

   Puoi aprire la configurazione di qualsiasi origine di registro da un [!DNL Transformation Dependency Map]. Per informazioni su [!DNL Transformation Dependency Map], consulta [Strumenti di configurazione del set di dati](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

<!--
c_sensor_files.xml
-->

## Requisiti {#section-d5901a4872774ad5bd01a18db114f1f2}

I dati evento raccolti da [!DNL Sensors] dai server HTTP e application vengono trasmessi ai server di Data Workbench, che convertono i dati in file di log ( [!DNL .vsl]) altamente compressi. Il formato di file [!DNL .vsl] viene gestito dal server di Data Workbench e ogni file ha un nome del formato:

AAAAMMGG-*SENSORID*.VSL

dove YYYMMDD è la data del file e *SENSORID* è il nome (assegnato dalla tua organizzazione) che indica quale [!DNL Sensor] ha raccolto e trasmesso i dati al server di Data Workbench.

## Parametri {#section-5c3f1e341c284486aeba3452057da7f3}

Per i file [!DNL Sensor] sono disponibili i seguenti parametri:

<table id="table_F583B475600041AFA3B9399AE0592146"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Percorsi di log </td> 
   <td colname="col2"> <p>Le directory in cui sono memorizzati i file <span class="filepath"> .vsl</span> . Il percorso predefinito è la directory Logs. Un percorso relativo fa riferimento alla directory di installazione del server di Data Workbench. </p> <p>Puoi utilizzare i caratteri jolly per specificare quali file <span class="filepath"> .vsl</span> elaborare: 
     <ul id="ul_AE144ED0FAB94FE8B32599A058659DE1"> 
      <li id="li_1E4E4CFD72C34B5EB71A3C59877950A9"> * corrisponde a qualsiasi numero di caratteri </li> 
      <li id="li_4664400FC12E44B39B28438B85D20ED8"> ? corrisponde a un singolo carattere </li> 
     </ul> </p> <p> Ad esempio, il percorso del registro <span class="filepath"> Logs\*.vsl</span> corrisponde a qualsiasi file nella directory Logs che termina in <span class="filepath"> .vsl</span>. Il percorso di log <span class="filepath"> Logs\*-SENSOR?.vsl</span> corrisponde ai file nella directory Logs con qualsiasi data (YYYMMDD) e un singolo carattere dopo SENSOR, come in SENSOR1. </p> <p> Se si desidera cercare tutte le sottodirectory del percorso specificato, è necessario impostare il parametro Ricorsivo su true. </p> <p> <p>Nota: Se i file devono essere letti dall' <span class="wintitle"> File Server Unit</span> di un server di Data Workbench, è necessario immettere gli URI appropriati nel parametro Log Paths. Ad esempio, l’ <span class="filepath"> URI /Logs/*-*.vsl</span> corrisponde a qualsiasi file <span class="filepath"> .vsl</span> nella directory Logs. Consultare <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurazione di un'unità del file server di Insight Server</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server di registro </td> 
   <td colname="col2">Informazioni (indirizzo, nome, porta e così via) necessarie per connettersi a un file server. Se nel parametro del server di registro è presente una voce, i <span class="wintitle"> percorsi di log</span> vengono interpretati come URI. In caso contrario, vengono interpretati come percorsi locali. Consultare <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurazione di un'unità del file server di Insight Server</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID origine registro </td> 
   <td colname="col2"> <p>Il valore di questo parametro può essere una qualsiasi stringa. Se viene specificato un valore, questo parametro consente di distinguere le voci di registro da diverse origini di registro per l'identificazione dell'origine o l'elaborazione mirata. Il campo x-log-source-id viene compilato con un valore che identifica l'origine del registro per ogni voce di registro. Ad esempio, se desideri identificare le voci di registro da un <span class="wintitle"> Sensor</span> denominato VSensor01, puoi digitare <span class="filepath"> da VSensor01</span> e passare tale stringa al campo x-log-source-id per ogni voce di registro da tale origine. </p> <p> Per informazioni sul campo x-log-source-id, vedere <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Campi record dati evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricorsivo </td> 
   <td colname="col2"> True o false. Se impostato su true, tutte le sottodirectory di ciascun percorso specificato in <span class="wintitle"> Log Paths</span> vengono cercate nei file che corrispondono al nome file o al pattern di caratteri jolly specificato. Il valore predefinito è false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usa ora di inizio/fine </td> 
   <td colname="col2"> <p>True o false. Se si specifica true e Start Time o End Time, tutti i file per questa origine di log devono avere nomi di file che iniziano con date in formato ISO (YYYMMDD). Si presume che ogni file contenga dati per un giorno GMT (ad esempio, l’intervallo di tempo che inizia alle 000 GMT di un giorno e termina alle 000 GMT del giorno successivo). Se i file delle origini del registro contengono dati che non corrispondono a un giorno GMT, allora questo parametro deve essere impostato su false per evitare risultati errati. </p> <p> <p>Nota: Per impostazione predefinita, i file <span class="filepath"> .vsl </span>contenenti dati raccolti da <span class="wintitle"> Sensor</span> soddisfano automaticamente i requisiti di denominazione e intervallo di tempo descritti in precedenza. Se si imposta questo parametro su true, il server di Data Workbench elabora sempre i dati dei file i cui nomi includono date ISO che si trovano tra l’ora di inizio e l’ora di fine specificate. Se si imposta questo parametro su false, il server di Data Workbench legge tutti i file <span class="filepath"> .vsl</span> durante l’elaborazione del registro per determinare quali file contengono dati nell’intervallo Ora di inizio e Ora di fine. </p> </p> <p> Per informazioni sui parametri Ora di inizio e Ora di fine, consulta <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtri dati</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Non utilizzare i parametri di configurazione per le origini dati [!DNL Sensor] per determinare quali voci di registro all&#39;interno di un file di registro includere in un set di dati. Imposta invece l&#39;origine dati in modo che punti a tutti i file di log all&#39;interno di una directory. Quindi utilizza i parametri Ora di inizio e Ora di fine di [!DNL Log Processing.cfg] per determinare quali voci di registro devono essere utilizzate nella costruzione del set di dati. Consulta [Filtri dati](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d).

<!--
c_log_files.xml
-->

Il file contenente i dati dell’evento deve soddisfare i seguenti requisiti:

* Ogni record di dati evento nel file deve essere rappresentato da una riga.
* I campi all’interno di un record devono essere separati, vuoti o meno, da un delimitatore ASCII. Il server di Data Workbench non richiede l’utilizzo di un delimitatore specifico. È possibile utilizzare qualsiasi carattere che non sia un carattere di fine riga e non sia visualizzato in alcun punto all’interno dei dati dell’evento stesso.
* Ogni record del file deve contenere:

   * Un ID di tracciamento
   * Un timestamp

* Per specificare l’ora di inizio e di fine dell’elaborazione dei dati, ciascun nome file deve essere del modulo:

   * [!DNL YYYYMMDD-SOURCE.log]

   dove *YYYMMDD* è il giorno di Greenwich Mean Time (GMT) di tutti i dati nel file e *SOURCE* è una variabile che identifica l&#39;origine dei dati contenuti nel file.

   >[!NOTE]
   >
   >Contatta Adobe Consulting Services per una revisione dei file di log che intendi incorporare nel set di dati.

## Parametri {#section-83a861ac24954d54bbb9530e4d8bf23c}

Per le origini di registro dei file di registro, sono disponibili i parametri della tabella seguente.

>[!NOTE]
>
>L&#39;elaborazione delle origini dei file di log richiede parametri aggiuntivi definiti in un file [!DNL Log Processing Dataset Include], che contiene un sottoinsieme dei parametri inclusi in un file [!DNL Log Processing.cfg] e parametri speciali per la definizione dei decoder per l&#39;estrazione dei dati dal file di log. Per informazioni sulla definizione dei decodificatori per le origini dei file di log, vedere [Gruppi decoder file di testo](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd).

<table id="table_F33735B5B90A48B0B21FA02D9198CCA9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Identificatore dell'origine del file di registro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Percorsi di log </td> 
   <td colname="col2"> <p>Le directory in cui sono memorizzati i file di registro. Il percorso predefinito è la directory Logs. Un percorso relativo fa riferimento alla directory di installazione del server di Data Workbench. </p> <p> Puoi utilizzare i caratteri jolly per specificare quali file di registro elaborare: 
     <ul id="ul_1F02D26A08D846E2A3114E5C33F60ECF"> 
      <li id="li_ECAE1C03A1C448A1B86AE00B3A955708"> * corrisponde a qualsiasi numero di caratteri. </li> 
      <li id="li_24FDB500C5934CAAA4124C435DF4B290"> ? corrisponde a un singolo carattere. </li> 
     </ul> </p> <p> Ad esempio, il percorso del registro <span class="filepath"> Logs\*.log</span> corrisponde a qualsiasi file nella directory Logs che termina in <span class="filepath"> .log</span>. </p> <p> Se si desidera cercare tutte le sottodirectory del percorso specificato, è necessario impostare il parametro Ricorsivo su true. </p> <p> Se i file devono essere letti dall' <span class="wintitle"> File Server Unit</span> di un server di Data Workbench, è necessario immettere gli URI appropriati nel parametro Log Paths. Ad esempio, l’ <span class="filepath"> URI/Logs/*.log</span> corrisponde a qualsiasi file <span class="filepath"> .log</span> nella directory Logs. Consultare <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurazione di un'unità del file server di Insight Server</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server di registro </td> 
   <td colname="col2"> Informazioni (indirizzo, nome, porta e così via) necessarie per connettersi a un file server. Se nel parametro del server di registro è presente una voce, i <span class="wintitle"> percorsi di log</span> vengono interpretati come URI. In caso contrario, vengono interpretati come percorsi locali. Consultare <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurazione di un'unità del file server di Insight Server</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compresso </td> 
   <td colname="col2"> True o false. Questo valore deve essere impostato su true se i file di registro da leggere dal server di Data Workbench sono file gzip compressi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gruppo decodificatore </td> 
   <td colname="col2"> Nome del gruppo di decodificatori file di testo da applicare all'origine del registro file di registro. Questo nome deve corrispondere esattamente al nome del gruppo di decodificatori del file di testo corrispondente specificato nel file <span class="wintitle"> Dataset Include</span> di elaborazione del registro. Vedere <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Gruppi decoder file di testo</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID origine registro </td> 
   <td colname="col2"> <p>Il valore di questo parametro può essere una qualsiasi stringa. Se viene specificato un valore, questo parametro consente di distinguere le voci di registro da diverse origini di registro per l'identificazione dell'origine o l'elaborazione mirata. Il campo x-log-source-id viene compilato con un valore che identifica l'origine del registro per ogni voce di registro. Ad esempio, se si desidera identificare le voci di registro da un'origine file di registro denominata LogFile01, è possibile digitare <span class="filepath"> da LogFile01</span> e tale stringa viene passata al campo x-log-source-id per ogni voce di registro da tale origine. </p> <p> Per informazioni sul campo x-log-source-id, vedere <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Campi record dati evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pattern di maschera </td> 
   <td colname="col2"> <p>Espressione regolare con un singolo sottopattern di acquisizione che estrae un nome coerente utilizzato per identificare l’origine di una serie di file di registro. Viene considerato solo il nome del file. Il percorso e l'estensione non vengono considerati per la corrispondenza delle espressioni regolari. Se non si specifica un <span class="wintitle"> pattern di maschera</span>, viene generata automaticamente una maschera. </p> <p> Per i file <span class="filepath"> Logs\010105server1.log</span> e <span class="filepath"> Logs\010105server2.log</span>, il <span class="wintitle"> pattern di maschera</span> sarebbe <code>[0-9]{6}(.*)</code>. Questo pattern estrae la stringa "server1" o "server2" dai nomi dei file riportati sopra. </p> <p> Consulta <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Espressioni regolari</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricorsivo </td> 
   <td colname="col2"> True o false. Se questo parametro è impostato su true, tutte le sottodirectory di ciascun percorso specificato in <span class="wintitle"> Log Paths</span> vengono cercate i file che corrispondono al nome file o al pattern di caratteri jolly specificato. Il valore predefinito è false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rifiuta file </td> 
   <td colname="col2"> Il percorso e il nome del file contenente le voci di registro che non soddisfano le condizioni del decoder. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usa ora di inizio/fine </td> 
   <td colname="col2"> <p>True o false. Se questo parametro è impostato su true e viene specificato Start Time o End Time, tutti i file per questa origine di log devono avere nomi di file che iniziano con date in formato ISO (YYYYMMDD). Si presume che ogni file contenga dati per un giorno GMT (ad esempio, l’intervallo di tempo che inizia alle 000 GMT di un giorno e termina alle 000 GMT del giorno successivo). Se i nomi dei file delle origini di registro non iniziano con date ISO o se i file contengono dati che non corrispondono a un giorno GMT, allora questo parametro deve essere impostato su false per evitare risultati errati. </p> <p> <p>Nota:  Se i requisiti di denominazione e intervallo di tempo descritti in precedenza sono soddisfatti per i file di registro e si imposta questo parametro su true, il gruppo di decodificatori file di testo specificato limita i file letti a quelli i cui nomi hanno date ISO che rientrano tra l'ora di inizio e l'ora di fine specificate. Se si imposta questo parametro su false, il server di Data Workbench legge tutti i file di registro durante l’elaborazione del registro per determinare quali file contengono dati nell’intervallo Ora di inizio e Ora di fine. </p> </p> <p> Per informazioni sui parametri Ora di inizio e Ora di fine, consulta <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtri dati</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

In questo esempio, il set di dati è costruito da due tipi di origini di registro.

Origine registro 0 specifica i file di registro generati dai dati dell&#39;evento acquisiti da [!DNL Sensor]. Questa origine dati punta a una directory denominata Logs e a tutti i file presenti in tale directory con estensione del nome file [!DNL .vsl].

Origine registro 1 punta a tutti i file nella directory Logs con estensione del nome file [!DNL .txt]. Il gruppo di decodificatori per questa origine di log si chiama &quot;Registri di testo&quot;.

![](assets/cfg_LogProcessing_LogSources.png)

Non eliminare o spostare file di registro dopo la definizione delle origini dati per un set di dati. Solo i file di registro appena creati devono essere aggiunti alla directory per le origini dati.

<!--
c_xml_log_sources.xml
-->

Il file contenente i dati dell’evento deve soddisfare i seguenti requisiti:

* I dati evento devono essere inclusi in un file XML formattato correttamente con relazioni padre-figlio appropriate.
* Per ogni formato di file XML deve esistere un gruppo di decodificatori univoco. Per informazioni sulla costruzione di un gruppo di decodificatori, vedere [Gruppi decoder XML](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).
* Ogni record visitatore nel file deve contenere:

   * Un ID di tracciamento
   * Un timestamp

* Per specificare l’ora di inizio e di fine dell’elaborazione dei dati, ogni nome file deve essere del modulo

[!DNL YYYYMMDD-SOURCE.log]

dove *YYYMMDD* è il giorno di Greenwich Mean Time (GMT) di tutti i dati nel file e *SOURCE* è una variabile che identifica l&#39;origine dei dati contenuti nel file.

Per un esempio di file XML che soddisfa questi requisiti, vedere [Gruppi decoder XML](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

>[!NOTE]
>
>Contattare Adobe Consulting Services per una revisione dei file di log XML che si intende incorporare nel set di dati.

## Parametri {#section-d07b96d7f6ad4affb9cc0a0bc1b88c4d}

Per le origini di registro XML, sono disponibili i parametri della tabella seguente.

>[!NOTE]
>
>L&#39;elaborazione delle origini di registro XML richiede parametri aggiuntivi definiti in un file [!DNL Log Processing Dataset Include] che contiene un sottoinsieme dei parametri inclusi in un file [!DNL Log Processing.cfg] e parametri speciali per la definizione dei decoder per l&#39;estrazione dei dati dal file XML. Per informazioni sulla definizione dei decodificatori per le origini di log XML, vedere [Gruppi decoder XML](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

<table id="table_86B849F379CF4FEBA9294ACEF8F55184"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Identificatore per l'origine del registro XML. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Percorsi di log </td> 
   <td colname="col2"> <p>Le directory in cui sono memorizzate le origini di registro XML. Il percorso predefinito è la directory Logs. Un percorso relativo fa riferimento alla directory di installazione del server di Data Workbench. </p> <p> È possibile utilizzare caratteri jolly per specificare quali origini di registro XML elaborare: 
     <ul id="ul_0AE5D0ADE0F64CFAA856492A49239F58"> 
      <li id="li_4CBC0D1733F04258B3A55CC6FA714538 "> * corrisponde a qualsiasi numero di caratteri </li> 
      <li id="li_81B597436A1241FF94E73C18A0ABBFA1"> ? corrisponde a un singolo carattere </li> 
     </ul> </p> <p>Ad esempio, il percorso del registro <span class="filepath"> Logs\*.xml</span> corrisponde a qualsiasi file nella directory Logs che termina in <span class="filepath"> .xml</span>. </p> <p> Per cercare tutte le sottodirectory del percorso specificato, è necessario impostare il campo <span class="wintitle"> Recursive</span> su true. </p> <p> <p>Nota: Se i file devono essere letti dall' <span class="wintitle"> File Server Unit</span> di un server di Data Workbench, è necessario immettere gli URI appropriati nel campo <span class="wintitle"> Log Paths</span> . Ad esempio, l’ <span class="filepath"> URI/Logs/*.xml</span> corrisponde a qualsiasi file <span class="filepath"> .xml</span> nella directory Logs. Consultare <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurazione di un'unità del file server di Insight Server</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server di registro </td> 
   <td colname="col2"> Informazioni (indirizzo, nome, porta e così via) necessarie per connettersi a un file server. Se nel campo <span class="wintitle"> Log Server</span> è presente una voce, i <span class="wintitle"> Log Paths</span> vengono interpretati come URI. In caso contrario, vengono interpretati come percorsi locali. Consultare <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurazione di un'unità del file server di Insight Server</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compresso </td> 
   <td colname="col2"> True o false. Questo valore deve essere impostato su true se le origini di registro XML da leggere dal server di Data Workbench sono file gzip compressi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gruppo decodificatore </td> 
   <td colname="col2"> Nome del gruppo di decodificatori XML da applicare all'origine di log XML. Questo nome deve corrispondere esattamente al nome del gruppo di decodificatori XML corrispondente specificato nel file <span class="wintitle"> Dataset Include</span> di elaborazione del registro. Vedere <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> Gruppi decoder XML</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID origine registro </td> 
   <td colname="col2"> <p>Il valore di questo campo può essere una qualsiasi stringa. Se viene specificato un valore, questo campo consente di distinguere le voci di registro da diverse origini di registro per l'identificazione dell'origine o l'elaborazione mirata. Il campo x-log-source-id viene compilato con un valore che identifica l'origine del registro per ogni voce di registro. Ad esempio, se desideri identificare le voci di registro da un’origine di file di registro denominata XMLFile01, puoi digitare <span class="filepath"> da XMLFile01</span> e passare tale stringa al campo x-log-source-id per ogni voce di registro da tale origine. </p> <p> Per informazioni sul campo x-log-source-id, vedere <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Campi record dati evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pattern di maschera </td> 
   <td colname="col2"> <p>Espressione regolare con un singolo sottopattern di acquisizione che estrae un nome coerente utilizzato per identificare l’origine di una serie di file di registro. Viene considerato solo il nome del file. Il percorso e l'estensione non vengono considerati per la corrispondenza delle espressioni regolari. Se non si specifica un <span class="wintitle"> pattern di maschera</span>, viene generata automaticamente una maschera. </p> <p> Per i file <span class="filepath"> Logs\010105server1.xml</span> e <span class="filepath"> Logs\010105server2.xml</span>, il pattern della maschera sarebbe <code>[0-9]{6}(.*)</code>. Questo pattern estrae la stringa "server1" o "server2" dai nomi dei file riportati sopra. </p> <p> Consulta <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Espressioni regolari</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricorsivo </td> 
   <td colname="col2"> True o false. Se questo parametro è impostato su true, tutte le sottodirectory di ciascun percorso specificato in <span class="wintitle"> Log Paths</span> vengono cercate i file che corrispondono al nome file o al pattern di caratteri jolly specificato. Il valore predefinito è false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rifiuta file </td> 
   <td colname="col2"> Il percorso e il nome del file contenente le voci di registro che non soddisfano le condizioni del decoder. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usa ora di inizio/fine </td> 
   <td colname="col2"> <p>True o false. Se questo parametro è impostato su true e viene specificato Start Time o End Time, tutti i file per questa origine di log devono avere nomi di file che iniziano con date in formato ISO (YYYYMMDD). Si presume che ogni file contenga dati per un giorno GMT (ad esempio, l’intervallo di tempo che inizia alle 000 GMT di un giorno e termina alle 000 GMT del giorno successivo). Se i nomi dei file delle origini di registro non iniziano con date ISO o se i file contengono dati che non corrispondono a un giorno GMT, allora questo parametro deve essere impostato su false per evitare risultati errati. </p> <p> <p>Nota:  Se i requisiti di denominazione e intervallo di tempo descritti sopra sono soddisfatti per i file XML e si imposta questo parametro su true, il gruppo di decodificatori XML specificato limita i file letti a quelli i cui nomi hanno date ISO che si trovano tra l'ora di inizio e l'ora di fine specificate. Se si imposta questo parametro su false, il server di Data Workbench legge tutti i file XML durante l’elaborazione del registro per determinare quali file contengono dati nell’intervallo Ora di inizio e Ora di fine. </p> </p> <p> Per informazioni sui parametri Ora di inizio e Ora di fine, consulta <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtri dati</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Non eliminare o spostare le origini di registro XML dopo la definizione delle origini dati per un set di dati. Solo i file XML appena creati devono essere aggiunti alla directory delle origini dati.

<!--
AVRO-log-file.xml
-->

Il feed di dati Avro offre un modo più efficiente di integrare i dati nella Data Workbench:

<!-- <a id="section_45E3105B971C4220AE9CF573BEBF6080"></a> -->

* Avro fornisce un formato a singola origine per i dati di traffico e commercio.
* Il feed Avro è compresso in dati di più blocchi sorgente forniti al giorno. Fornisce solo campi popolati e fornisce funzioni di monitoraggio e notifica, accesso ai dati storici e recupero automatico.
* Lo schema, un layout autodefinito dei file di log Avro, è incluso all&#39;inizio di ogni file.
* I nuovi campi vengono aggiunti con le informazioni di supporto per acquisire i dati delle Date Workbench senza che siano necessarie modifiche al decoder. Questi includono:

   * Evar: 1-250 (precedentemente 1-75)
   * Eventi personalizzati: 1-1000 (contro 1-100)
   * Accesso a variabili di soluzione per dati mobili, social e video

>[!NOTE]
>
>Inoltre, l’utilizzo del feed Avro consente l’accesso immediato a tutti i nuovi campi del feed senza spegnimento, consentendo l’aggiornamento dei campi senza requisiti di servizio per l’ora.

Il feed di dati Avro è configurato in file separati:

* Un **file di log Avro**: Questo è il formato di registro Avro generato dal decoder per formattare i dati del traffico e del commercio.
* Un **file Avro Decoder**: Questo file ti consente di mappare i valori nel nuovo formato Avro. È possibile impostare il decodificatore utilizzando Avro Decoder Wizard.

## Procedura guidata Decoder Avro {#section-9a824b4c3d5549e7952a7111232035b2}

Questa procedura guidata imposta il file di log del decodificatore Avro.

Per aprire, fai clic con il pulsante destro del mouse in un&#39;area di lavoro e seleziona **Amministratore** > **Procedure guidate** > **Procedura guidata Avro decoder**.

**Passaggio 1:** **selezionare un file di registro virtuale**.

In questo passaggio, puoi selezionare un file di origine per lo schema Avro. Gli schemi sono accessibili da un file di log (.log) o da un file decoder (.avrò) esistente. Gli schemi possono essere estratti da entrambi i file.

| **File di log Avro ** | Fai clic su per aprire un file di registro (.log) per visualizzare lo schema nella parte superiore del file di registro e generare il file di decodificatore. |
|---|---|
| **File decoder Avro** | Fai clic su per aprire e modificare lo schema di un file decoder (.avrò) esistente. |

**Passaggio 2: Selezionare Campi** di input.

Seleziona i campi di input da utilizzare nel set di dati per passare attraverso l’elaborazione del registro. Vengono visualizzati tutti i campi del file, che consentono di selezionare i campi per il feed.

>[!NOTE]
>
>Se nei dati viene rilevato un array, viene fornito un campo [!DNL x-product(Generates row)] . Questo campo genera nuove righe per i dati nidificati in una matrice come campi di input. Ad esempio, se si dispone di una riga Hit con molti valori di prodotto in un array, le righe verranno generate nel file di input per ogni prodotto.

| **Seleziona valori predefiniti** | Seleziona i campi da identificare come set standard di campi predefiniti . |
|---|---|
| **Seleziona tutto** | Seleziona tutti i campi nel file . |
| **Deseleziona tutto** | Cancella tutti i campi nel file . |

**Passaggio 3: Selezionare i campi da copiare per generare le righe.**

Poiché è possibile creare nuove righe dai valori nidificati in un array, ogni nuova riga creata deve avere un ID di tracciamento e un timestamp. Questo passaggio ti consente di selezionare i campi da copiare nelle righe del record principale, ad esempio un ID di tracciamento e una marca temporale. È inoltre possibile selezionare altri valori da aggiungere a ogni riga.

| **Seleziona valori predefiniti** | Seleziona un set standard di campi predefiniti che richiedono l’aggiunta di nuovi valori di colonna a ciascuna riga, ad esempio un ID di tracciamento e una marca temporale. Ad esempio, un campo [!DNL hit_source] è un valore predefinito che deve essere aggiunto a ogni nuova riga (è definito come valore predefinito nell’elenco). È possibile aggiungere altri valori di colonna a ogni riga in base alle esigenze. |
|---|---|
| **Seleziona tutto** | Seleziona tutti i campi nel file . |
| **Deseleziona tutto** | Cancella tutti i campi nel file . |

Utilizzare la casella **Cerca** per trovare i valori nell&#39;elenco.

**Passaggio 4: specifica il nome del decodificatore**

Assegna un nome per il gruppo di campi e salva come file decoder. Il nome deve corrispondere al nome del gruppo Decoder specificato nell’origine del registro.

**Passaggio 5: Salva il file del decodificatore.**

Il menu file si apre per denominare il file decoder e salvare come file [!DNL .cfg] nella cartella **Logs**.
