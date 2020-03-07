---
description: Nuove funzioni introdotte in Workbench dati 6.0.4, incluse correzioni di bug e problemi noti.
solution: Analytics
title: Note sulla versione di Workbench dati 6.0
topic: Data workbench
uuid: b348425e-3304-4db7-a280-479a34452bdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Note sulla versione di Workbench dati 6.0

Nuove funzioni introdotte in Workbench dati 6.0.4, incluse correzioni di bug e problemi noti.

## Nuove funzionalità {#section-1225066ea8f44cf68e42e019d0bca816}

Workbench dati (Insight 6.0) include queste nuove funzioni e visualizzazioni per funzionalità di reporting e strumenti di analisi predittiva aggiuntivi.

| Funzioni del workbench dati | Descrizione |
|---|---|
| [Visualizzazione funnel](../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-funnel-visualization.md#concept-79a0854325324bb9a60906cf79ef66da) | La visualizzazione Funnel consente di definire il flusso sequenziale del processo dei clienti e fornisce visibilità sull’abbandono dei visitatori in ogni fase del processo. |
| [Clustering visitatore](../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d) | Il clustering consente di sfruttare le caratteristiche dei clienti per classificare in modo dinamico i visitatori e generare set di cluster basati su input di dati selezionati per l&#39;analisi e il targeting dei clienti. |
| [Analisi di correlazione](../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md#concept-a7c8766b40be43aaa4084612689b630c) | L&#39;analisi di correlazione consente di identificare rapidamente relazioni rilevanti tra i dati per estendere e migliorare l&#39;analisi. |
| [Distribuzione DeviceAtlas aggiornata](../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md#concept-28b7bd5c0d854e73834261c431bed1e0) | Il file JSON DeviceAtlas verrà ora distribuito in un file .bundle (un file .tar.gz rinominato) insieme a DeviceAtlas.dll e DeviceAtlas64.dll. |

## Requisiti per l&#39;aggiornamento client {#section-f316103b48374b6eac77e8feb5c47ecf}

Completa queste attività di aggiornamento per le funzionalità client workbench dati (Insight 6.0):

**Aggiornamento del file .zbin per il client**

Workbench dati ora supporta un IME (Input Method Editor) come processo di immissione di testo secondario che consente di immettere caratteri internazionali dalla tastiera utilizzando una casella di testo mobile. Il workbench dati supporterà l&#39;inglese per impostazione predefinita, ma consente anche di caricare altri file per supportare le lingue internazionali, ad esempio una tastiera cinese virtuale (Pinyin IME).

Un nuovo file dizionario (un file .zbin) è richiesto dall&#39;applicazione client prima di eseguire l&#39;aggiornamento alla versione 6.0. È possibile ottenere il file .zbin necessario dal profilo Software e Docs (Softdocs).

Prerequisiti:

* Prima di eseguire l&#39;aggiornamento al client Insight 6.0 e al server di report 6.0, l&#39;amministratore di Insight deve prima eseguire l&#39;aggiornamento a Insight Server 6.0.
* L&#39;amministratore di Insight dovrà scegliere un file zbin basato sulla lingua (en-us.zbin, zh-cn.zbin), copiare il file della lingua, quindi rinominarlo in insight.zbin e inserire il file rinominato nella directory principale del server di report in cui si trova l&#39;eseguibile. Quindi riavviate il server di report Insight.

Per ulteriori informazioni sull&#39;aggiornamento lato server, consulta Requisiti [per l&#39;aggiornamento del](../../../home/c-release-notes-insight/release-notes.md) server.

**Per aggiornare il file zbin per il client (dalla versione 5.x alla 6.0)**

1. Per essere certi che il client non venga aggiornato dal server Insight durante l&#39;aggiornamento, imposta l&#39;argomento Insight.cfg su false.

   ```
   Update Software = bool: false
   ```

1. Riavviate il client Insight.
1. Andate al profilo Software e Docs (profilo SoftDocs) e scaricate il **[!UICONTROL Insight.zbin]** file richiesto: [!DNL Software\Insight Client\v6.00\Insight_6.00.zip]

1. Copiate il file Insight.zbin nella stessa cartella del file Insight.exe.
1. Per essere certi che il client Insight ora venga aggiornato dal server Insight, imposta l&#39;argomento del file Insight.cfg su true:

   ```
   Update Software = bool: true
   ```

1. Riavviate il client.

   Il client si sincronizzerà con il server e verrà visualizzato un messaggio in cui si informa che il client sta scaricando. Al termine del download, riceverete un messaggio in cui viene richiesto se desiderate riavviare il client Insight.
1. Fate clic su **OK** per riavviare il client.

   Il client verrà avviato e aggiornato alla versione 6.0.

1. Riavviate il client per rendere effettiva la sincronizzazione del client Insight.zbin.

   Se ricevete il messaggio seguente, significa che lo zbin non è stato inserito nella posizione corretta accanto al file Insight.exe.

   ```
   Insight Terminated: The backup dictionary file insight.zbin 
   is missing.
   ```

   Per correggere il problema, eliminare Insight.exe e rinominare la versione più recente di Insight.exe.old in Insight.exe, quindi riavviare con il passaggio 1 precedente.

## Requisiti per l&#39;aggiornamento del server {#section-d6edba8b36234957ba8d06b555667a5a}

Completa le seguenti attività di aggiornamento per le funzionalità del server Insight 6.0:

**Aggiorna tutti i pacchetti** Insight Server 6.0. Insight 6.0 include i pacchetti server che devono essere aggiornati, incluso il nuovo profilo Predictive Analytics.

>[!IMPORTANT]
>
>È consigliabile che gli utenti aggiornino i cluster di server con le nuove installazioni di Insight Server 6.0 durante l&#39;aggiornamento.

È inoltre consigliabile aggiornare i cluster di server client con la nuova installazione di Insight Server 6.0.

## Aggiorna cluster server

**Preparate il file della lingua (file .zbin).** L’amministratore di Insight seleziona il `<language>.zbin` file per la lingua richiesta (ad esempio: en-us.zbin , zh-cn.zbin) che si trova nella `/localization/<language>.zbin` cartella. L’amministratore copia quindi il file della lingua e lo rinomina in &quot;insight.zbin&quot;.

Dopo aver preparato il file della lingua (.zbin), è necessario aggiornare sia il client Insight che il server di report. Insight Client viene aggiornato durante il processo [di aggiornamento del](../../../home/c-release-notes-insight/release-notes.md)client, ma nella maggior parte dei casi l&#39;amministratore di Insight aggiorna il server di report.

**Aggiorna il server di report con un file della lingua (file .zbin)**.

Per tutte le lingue, Report Server 6.0 richiede il file &quot;insight.zbin&quot; copiato nella cartella principale del server di report.

Aggiornare i file della lingua del server di report:

1. Aggiungete il file &quot;insight.zbin&quot; rinominato nella directory principale di ReportServer.
1. Il file di configurazione del server di report (reportserver.cfg) richiede impostazioni di font per le lingue a doppio byte. Ad esempio, il cinese richiede l&#39;aggiunta di font utilizzando SimSun:

   ```
   Report Server.cfg - Add Fonts 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. È necessario passare un parametro per Report Server 6.0 nella riga di comando per la localizzazione, ad esempio:

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Se non vengono specificate impostazioni internazionali, il server di report utilizza per impostazione predefinita la lingua selezionata nel file insight.zbin.

   Seguite i passaggi per avviare ReportServer come servizio con i parametri delle impostazioni internazionali:

   1. Avviate un prompt dei comandi come amministratore.
   1. Andate alla cartella di installazione di ReportServer.
   1. Digitate il comando seguente per avviare il servizio:

      * Per inglese: [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * Per cinese: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. Per verificare se ReportServer è in esecuzione con i parametri corretti:

   1. Aprire Windows Service Manager.
   1. Right-click [!DNL Adobe Insight Report Server - Properties].
   Il percorso dell&#39;eseguibile conterrà i parametri:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Modificate il file di configurazione del profilo per Predictive Analytics**. L&#39;amministratore di Insight dovrà modificare il file profile.cfg personalizzato per includere il profilo Predictive Analytics disponibile in Insight.

Esempio della voce profile.cfg:

```
Example ("profile.cfg"): 
Profile = profileInfo:  
  Active = bool: true 
  Directories = vector: 5 items 
    0 = string: Base\\  
    1 = string: Predictive Analytics\\ 
    2 = string: Geography\\ 
    3 = string: Adobe SC\\ 
    4 = string: Custom Profile\\ 
```

**Aggiornate il file** PAServer.cfg. Se si desidera inviare i processi di clustering Predictive Analytics ai server Insight, sarà necessario configurare il file PAServer.cfg per la gestione degli invii del clustering lato server.

Il profilo personalizzato deve ereditare il file PAServer.cfg dal profilo Predictive Analytics (Server\Profiles\Predictive Analytics\Dataset). Configura e salva il file PAServer.cfg per il sito di implementazione.

>[!NOTE]
>
>Una volta configurato PAServer.cfg e salvato nel profilo personalizzato, è necessario riavviare Insight Server in tutto il sito.

**Aggiorna server di report.** Sarà necessario aggiornare i font e i parametri di avvio per Report Server.

Prerequisiti:

* Prima di aggiornare Report Server 6.0, l&#39;amministratore di Insight deve effettuare l&#39;aggiornamento a Insight Server 6.0.
* Per tutte le lingue, Report Server 6.0 richiede l&#39;aggiunta di Insight.zbin alla cartella principale del server di report. Accertatevi che il file `base/localization/<language>.zbin` sia copiato e rinominato in &quot;insight.zbin&quot;. Copiatelo nella directory principale del server di report.

Aggiornate i parametri Font e Avvio:

1. Il server di report richiede l&#39;impostazione dei font per il doppio byte al fine di eseguire l&#39;output in lingue diverse,

   ad esempio:

   Report Server.cfg - Aggiungi font

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Il parametro per Report Server 6.0 deve essere passato nella riga di comando per la localizzazione.

   Per avviare il server di report come servizio con i parametri delle impostazioni internazionali:

   1. Arrestate il servizio del server di report.
   1. Avviate un prompt dei comandi come amministratore.
   1. Andate alla cartella di installazione del server di report.
   1. Digitate il comando seguente per avviare il servizio:

      ```
      ReportServer.exe -RegServer -Locale -en-us
      ```

Per verificare se il server di report è in esecuzione con i parametri corretti:

1. Apri Windows Service Manager
1. Right-click [!DNL Adobe Insight Report Server - Properties].
1. Il percorso dell&#39;eseguibile conterrà i parametri:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Aggiornate il feed di dati SiteCatalyst per Insight 6.0**. Il formato del nome file del feed di dati SiteCatalyst per Insight 6.0 è stato modificato.

Formato file corrente:

```
 RSID_YYYYMMDD_HH0000.tsv.gz
```

Nuovo formato del nome file:

```
YYYYMMDD-RSID_HH0000.tsv.gz
```

>[!NOTE]
>
>Questa modifica non influisce sugli utenti attualmente distribuiti con la versione *wbench/ecom* del feed di dati SiteCatalyst.

La modifica del formato del nome del file consentirà l’uso completo delle dichiarazioni di inizio e fine di Insight durante l’elaborazione del registro. Questo consente al processo di valutare se il contenuto del file deve essere letto, anziché filtrare tutti i file sorgente utilizzando una ricerca riga per riga.

Nella maggior parte dei casi, una procedura di ridenominazione è stata implementata dopo la ricezione del file per fornire il pieno utilizzo di questa funzionalità. Questa modifica fornisce la convenzione di denominazione richiesta per impostazione predefinita, senza la necessità e il sovraccarico di un processo secondario.

Per utilizzare il nuovo feed di dati SiteCatalyst:

1. Determinare in che modo il processo di ricezione gestirà il nuovo formato del nome file.

   Gli script standard di ridenominazione/spostamento distribuiti durante l&#39;implementazione spostano i file con estensione &quot;.gz&quot; ed eseguono un nuovo nome solo se il nome file corrisponde al formato del nome del file con l&#39;RSID precedente.

   Il nuovo formato del nome file:

   ```
    YYYYMMDD-RSID_HH0000.tsv.gz
   ```

1. Valutare i percorsi di origine del registro definiti per confermare che tutti i file saranno letti.

   Se è già stato implementato uno script di ridenominazione, le origini di registro sono già definite per la lettura del nuovo formato di nome file.

## Problemi risolti {#section-203f917dd6224114a1f801309c4c2cee}

* Ora, la combinazione di tasti per lasciare un’area di lavoro senza salvare le modifiche è stata aggiornata a **[!UICONTROL `<Ctrl>`+`<Backspace>`]**. Precedentemente, era possibile annullare le modifiche e chiudere un’area di lavoro premendo`<Ctrl>`+`<Delete>`.

## Data Workbench 6.0.4 Release Notes{#data-workbench-release-notes}

Nuove funzioni introdotte in Workbench dati 6.0.4, incluse correzioni di bug e problemi noti.

Per visualizzare le funzioni e le correzioni precedenti basate su ciascuna versione precedente, consulta gli archivi delle note sulla [versione](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html).

## Nuove funzionalità {#section-2-1225066ea8f44cf68e42e019d0bca816}

Workbench dati 6.0.4 include queste nuove funzioni e visualizzazioni per funzionalità di reporting e strumenti di analisi predittiva aggiunti.

**Visualizzazione** Propensity Scoring (Punteggio tendenza). Il workbench dati calcola i punteggi per ogni visitatore come probabilità stimata che si verifichi un evento specificato. La visualizzazione Punteggio visitatori consente di creare una dimensione punteggio che dia la probabilità di un evento specificato per ogni visitatore di interesse in base alle variabili di input.

![](assets/visitor_scoring_visual.png)

Per ulteriori informazioni su questa funzione, consultate [Punteggio](../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-visitor-propensity.md#concept-2958f4640dd44b9d86ad51c4f6165f40) tendenza.

## Requisiti per l&#39;aggiornamento {#section-08bd6fe3da8740fcb19688e8cac6f223}

**È necessario definire** l’ID origine del registro. A partire dalla versione 6.04, se l’ID origine registro non è definito, verrà visualizzato il seguente errore:

```
Missing Log Souce ID in log processing.cfg. Log Source ID must be  
defined for all log sources.
```

La registrazione di righe per origine log è stata aggiunta in Workbench dati 6.0 e può essere definita nel profilo personalizzato Log Processing.cfg aggiungendo un ID origine log denominato in modo univoco. Se si dispone di un ID origine log vuoto, è possibile che si verifichino problemi di elaborazione log come la lettura incompleta dei dati di origine del log e altre discrepanze.

```
Log Processing.cfg 
Log Sources = vector: 2 items 
  0 = VisualSensor: 
    Compressed = bool: false 
    Log Paths = vector: 1 items 
      0 = Path: \some path\ 
    Log Server = serverInfo:  
      Address = string:  
      Name = string:  
      Port = int: 80 
      Proxy Address = string:  
      Proxy Password = string:  
      Proxy Port = int: 8080 
      Proxy User Name = string:  
      SSL Client Certificate = string: Certificates\\server_cert.pem 
      SSL Server Common Name = string:  
      Use SSL = bool: false 
     
Log Source ID = string: <Name your ID Here>
    Name = string:  
    Recursive = bool: false
```

**Possibilità di delegare le risorse FSU**

In [!DNL Profiles/`<profilename>`/dataset/Cluster.cfg], è ora possibile specificare unità di file server (FSU) distinte per i server Normalize (Normalizza) e Source List (Elenco di origine). Questi servizi non sono più legati al Master FSU.

>[!NOTE]
>
>Se il server di riepilogo non è specificato, il server di riepilogo erediterà le impostazioni di configurazione del server di normalizzazione.

Example in the [!DNL cluster.cfg] file.

```
Cluster = ClusterConfig: 
  Normalize Server = serverInfo: 
    Address = string: normalizeserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false 
  List Server = serverInfo: 
    Address = string: sourcelistserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false
```

## Bug fissi {#section-3b4b85a35f534288adf8a5246ef028cc}

* In Workbench dati 6.0, la matrice di correlazione e Generatore cluster non supportavano l&#39;opzione Calcola in background. Questo problema è stato risolto nella versione 6.0.4.
* Precedentemente, se si selezionava un passaggio e si rimuoveva un passaggio, si poteva verificare una violazione dell&#39;accesso. Questo è stato risolto.
* Risolto un problema di potenziale condizione di blocco in Segment Export (Esportazione segmento) che poteva causare problemi in condizioni di carico elevate.
