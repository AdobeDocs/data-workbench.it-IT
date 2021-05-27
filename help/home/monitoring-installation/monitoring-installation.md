---
description: Istruzioni per l’installazione del profilo di monitoraggio di Data Workbench.
title: Installazione del profilo di monitoraggio
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
exl-id: 368e489c-75c9-4402-a709-a4f5987459b6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---

# Installazione del profilo di monitoraggio{#installing-the-monitoring-profile}

Istruzioni per l’installazione del profilo di monitoraggio di Data Workbench.

## Passaggi di installazione {#section-d4355dbea8a447f48ab168db6ccff612}

1. Configura una nuova istanza Sensor come se venisse utilizzata per la raccolta di dati di pagine web con tag. Assicurati che il file zig.gif sia nella directory principale dei documenti del server web Sensor. Il sensore può essere eseguito sullo stesso host dei profili di monitor. (Questo non è un problema se si utilizza un file di testo a questo scopo.)

   >[!NOTE]
   >
   >Questa istanza del sensore deve essere dedicata alla ricezione solo del traffico dagli agenti di monitoraggio. Inoltre, il sensore può essere configurato per l&#39;esecuzione su una porta diversa se stai riutilizzando un server web per questa raccolta.

1. Nel file [!DNL txlogd.conf] è presente la riga predefinita:

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   Per l’applicazione del profilo di monitoraggio di Data Workbench (o qualsiasi implementazione di pagina con tag), il tipo di immagine deve essere rimosso per poter essere raccolto tramite un file GIF. La riga aggiornata è:

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. Copia il [!DNL insight_monitor.zip/insight_monitor_agent] in una posizione temporanea.
1. Aggiorna il file [!DNL insight_monitor_agent.cfg] per il tuo ambiente. Segui i commenti all’interno del file di configurazione:

   **Il file di configurazione di monitoraggio:**

   ![](assets/monitor_agent_cfg_sensor.png)

   Definisci dove stai raccogliendo tutte le informazioni e fornisci l’indirizzo URL. Questo deve essere un sensore dedicato e non deve ricevere traffico se non per questa applicazione.

   ![](assets/monitor_agent_cfg_dump.png)

   Ci sono percorsi che presuppongono un e: disco. È possibile modificare questo percorso per l&#39;ambiente.

   ![](assets/monitor_agent_cfg_quickcheck.png)

   A volte, quando si esegue un profilo di trasformazione, Data Workbench può non rispondere. Questo valore ti consente di inviare un avviso se il processo non risponde per tre volte di seguito. Questo è un modo per ridurre gli avvisi falsi positivi.

   ![](assets/monitor_agent_cfg_groups.png)

   In questo punto puoi impostare l’ambiente e le dimensioni del gruppo. Questo può essere diverso da host a host.

   Qui puoi vedere esattamente cosa sta facendo l&#39;agente di monitoraggio visualizzando i registri degli errori in questo percorso.![](assets/monitor_agent_cfg_debug.png)

   ![](assets/monitor_agent_cfg_tempdb.png)

   In questo modo si utilizza il database temp internamente. Può essere avvisato quando raggiunge la capacità. Questo è diverso dall&#39;utilizzo del disco fisico.

1. Copia la cartella *insight_monitor_agent* in ogni host DPU e FSU che esegue il server di Data Workbench. La posizione predefinita indicata nel file di configurazione è [!DNL e:\insight_monitor_agent], ma puoi modificare questa posizione.

1. Aggiungi un&#39;attività pianificata di Windows per richiamare l&#39;agente ogni 10 minuti (questo periodo viene considerato nei calcoli del tasso di elaborazione). Il programma è [!DNL e:insight_monitor/insight_monitor_agent.exe]. L&#39;argomento è config-file e:\insight_monitor\insight_monitor.cfg. Inizia da e:\insight_monitor. L’utente che esegue l’attività deve disporre dell’autorizzazione per leggere/scrivere [!DNL e:\insight_monitor] e leggere l’oggetto OLE Win32 [!DNL root\CIMV2] (necessario per verificare la modalità di avvio del servizio server di Data Workbench e per controllare la percentuale di spazio su dischi locali)

1. Conferma che il file VSL sta iniziando a crescere con l&#39;accumulo dei record del monitor. Questo richiederà del tempo in quanto il volume di traffico sarà estremamente basso in una piccola installazione (ogni 10 minuti l’agente invia un solo hit per i dati specifici dell’host, più un hit per profilo di elaborazione).
1. Decomprimi insight_monitor.zip\profiles\Insight Historic to a temporary location.
1. Aggiorna il nome host in [!DNL profile.cfg], [!DNL dataset\cluster.cfg] e in [!DNL dataset\segment export.cfg].

1. Aggiorna i file nella directory dei profili di Data Workbench.
1. Aggiorna il server di registro e il percorso in [!DNL dataset\log processing.cfg] nel percorso in cui si sta accumulando il VSL Sensor.
1. [] Facoltativamente, fai lo stesso con i profili  [!DNL Insight Profile Status] e  [!DNL Insight Server Status]. Inoltre, i profili di stato devono essere rielaborati di notte con una finestra finale di due giorni. Aggiungi un&#39;attività pianificata di Windows: Il programma è [!DNL e:\insight_monitor\insight_reprocess.exe]. L’argomento è [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Lascia [!DNL start in] vuoto. Aggiungi un&#39;altra attività pianificata per *&quot;insight server status&quot;*. *insight_reprocess.* richiede l&#39;accesso in lettura/scrittura al file  *log processing.* cfgto per aggiornare l&#39;ora di inizio.

1. Inoltre, i profili di stato devono essere rielaborati di notte con una finestra finale di due giorni. Aggiungi un&#39;attività pianificata di Windows: Il programma è *e:\insight_monitor\insight_reprocess.exe*. L&#39;argomento è - [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Lascia vuoto *start in* . Aggiungi un&#39;altra attività pianificata per [!DNL "insight server status"]. [!DNL insight_reprocess.exe] richiede l&#39;accesso in lettura/scrittura a  [!DNL log processing.cfg] per aggiornare l&#39;ora di inizio. Verificare che ogni profilo stia leggendo il VSL del monitor durante l&#39;accumulo. Anche in questo caso, ci vorrà un po&#39; di tempo, probabilmente ore, a causa del volume estremamente basso.

## Note di installazione {#section-17722441ab0046fcbcb46b957d56230a}

* **Configurazione del profilo di monitoraggio in un ambiente** di test con licenza. Il pacchetto dell’ambiente di test è incluso con l’implementazione di Data Workbench, che consente di installare e configurare l’applicazione. Se si esegue l&#39;installazione su un server FSU o DPU di produzione, sarà necessario configurare il server per l&#39;esecuzione su una porta separata.
* **Distribuzione di un nuovo sensore specifico per il profilo** di monitoraggio. Sarà necessario installare una nuova istanza di Sensor sul server che esegue il Profilo di monitoraggio. Questo si aggiunge all&#39;istanza di produzione di Sensor. (Non esiste alcun costo aggiuntivo per l&#39;installazione di Sensor su un server di produzione o non di produzione specifico per il profilo di monitoraggio).
* **Disattiva l’agente di monitoraggio durante la manutenzione** di Data Workbench. Per evitare di inquinare le metriche del tempo di attività e delle prestazioni, è possibile impostare la modalità di avvio del servizio su manuale per il servizio InsightServer (Omniture Insight Server). Un comodo comando PowerShell è *set-service -name insightserver -startuptype manual*. Ripristinare l&#39;impostazione automatica dopo la manutenzione: *set-service -name insightserver -startuptype automatico*. Un&#39;altra opzione consiste nel disattivare temporaneamente l&#39;attività pianificata dell&#39;agente di monitoraggio.
* **I profili di stato devono disporre di una** finestra finale per eliminare host e profili precedenti e le mappature dei profili host precedenti. Tuttavia, se la quantità di dati dell’evento è così piccola che Data Workbench non esegue il buffer in, potrebbe essere necessario estendere leggermente la dimensione della finestra per consentirne l’elaborazione.
* **L’agente raccoglie lo stato** dettagliato complessivo e meno recente da Data Workbench, riportato nell’ora host locale supponendo che i timestamp del log dei dati dell’evento siano in formato UTC (come nei file VSL). Se le marche temporali dei dati dell’evento si trovano in un fuso orario non UTC, l’offset a partire dall’ora verrà effettuato nel profilo dello stato del profilo di Insight risultante. Se **tutti** i timestamp dei dati dell&#39;evento si trovano nello stesso fuso orario, è possibile aggiungere tale offset a *Profilo di Insight Status\metrics\as of delay minutes.metric*.

* **Sono state introdotte due nuove dimensioni per aiutare il gruppo di clienti con i propri server se si trovano in stati** diversi, ad esempio produzione, staging, server di test e server in altri stati. Ad esempio, se stai cercando &quot;uptime&quot;, guarda i server solo in modalità di produzione. Di conseguenza, la dimensione Gruppo è solo un altro modo per raggruppare arbitrariamente i server in base alle tue esigenze. Ad esempio, nel file di configurazione di monitoraggio è possibile impostare quale host del reparto sta servendo, ad esempio Operazioni, Sviluppo o Marketing.
