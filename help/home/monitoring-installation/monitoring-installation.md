---
description: Indicazioni per l'installazione del profilo di monitoraggio workbench dati.
solution: Analytics
title: Installazione del profilo di monitoraggio
topic: Data workbench
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installazione del profilo di monitoraggio{#installing-the-monitoring-profile}

Indicazioni per l&#39;installazione del profilo di monitoraggio workbench dati.

## Passaggi di installazione {#section-d4355dbea8a447f48ab168db6ccff612}

1. Configura una nuova istanza Sensor come se venisse utilizzata per la raccolta di dati di pagine Web con tag. Accertatevi che il file zig.gif sia nella directory principale del documento del server Web Sensor. Il sensore può essere eseguito sullo stesso host dei profili del monitor. (Questo non è un problema se si utilizza un file di testo a tal fine.)

   >[!NOTE]
   >
   >Questa istanza Sensor deve essere dedicata alla ricezione del solo traffico dagli agenti di monitoraggio. Inoltre, il sensore può essere configurato per l&#39;esecuzione su una porta diversa se si sta riutilizzando un server Web per questa raccolta.

1. Nel [!DNL txlogd.conf] file è presente la riga predefinita:

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   Per l&#39;applicazione Data Workbench Monitoring Profile (o qualsiasi implementazione di pagina con tag), il tipo di immagine deve essere rimosso per poter essere raccolto tramite un file GIF. La riga aggiornata è:

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. Copiare la posizione [!DNL insight_monitor.zip/insight_monitor_agent] in una posizione temporanea.
1. Aggiornare [!DNL insight_monitor_agent.cfg] il file per l&#39;ambiente. Seguite i commenti all&#39;interno del file di configurazione:

   **Il file di configurazione del monitoraggio:**

   ![](assets/monitor_agent_cfg_sensor.png)

   Definite dove state raccogliendo tutte le informazioni e fornite l’indirizzo URL. Deve essere un sensore dedicato e non deve ricevere traffico se non per questa applicazione.

   ![](assets/monitor_agent_cfg_dump.png)

   Ci sono percorsi che presuppongono che ci sia una e: disco. Potrebbe essere utile modificare questo percorso per l&#39;ambiente.

   ![](assets/monitor_agent_cfg_quickcheck.png)

   Talvolta, quando si esegue un profilo di trasformazione, il workbench dati potrebbe non essere reattivo. Questo valore consente di inviare un avviso se il processo non risponde per tre volte nella riga. Questo è un modo per ridurre i falsi allarmi positivi.

   ![](assets/monitor_agent_cfg_groups.png)

   Qui si definiscono l’ambiente e le dimensioni del gruppo. Può essere diverso da host a host.

   Qui ![](assets/monitor_agent_cfg_debug.png)potete vedere esattamente cosa sta facendo l&#39;agente di monitoraggio visualizzando i registri degli errori in questo percorso.

   ![](assets/monitor_agent_cfg_tempdb.png)

   In questo modo si utilizza il database temp internamente. Può essere avvisato quando raggiunge la capacità. Questo è diverso dall&#39;utilizzo del disco fisico.

1. Copiate la cartella *insight_monitor_agent* in ciascun host DPU e FSU che esegue il server workbench dati. Il percorso predefinito indicato nel file di configurazione è [!DNL e:\insight_monitor_agent] ma è possibile modificarlo.

1. Aggiungere un&#39;attività pianificata di Windows per richiamare l&#39;agente ogni 10 minuti (questo periodo viene considerato nei calcoli del tasso di elaborazione). Il programma è [!DNL e:insight_monitor/insight_monitor_agent.exe]. L’argomento è config-file e:\insight_monitor\insight_monitor.cfg. Iniziate da e:\insight_monitor. L&#39;utente che esegue l&#39;attività deve disporre dell&#39;autorizzazione di lettura/scrittura [!DNL e:\insight_monitor] e lettura dell&#39;oggetto OLE Win32 [!DNL root\CIMV2] (necessaria per verificare la modalità di avvio del servizio del server workbench dati e per controllare la percentuale di spazio su dischi locali)

1. Verificare che il file VSL inizi a crescere con l&#39;accumulo dei record del monitor. Questo richiederà del tempo in quanto il volume di traffico sarà estremamente basso in una piccola installazione (ogni 10 minuti l&#39;agente invia solo un hit per i dati specifici dell&#39;host, più un hit per profilo di elaborazione).
1. Decomprimete insight_monitor.zip\profiles\Insight Historic to a temporary location.
1. Aggiorna nome host in [!DNL profile.cfg], [!DNL [!DNL dataset\cluster.cfg]] e [!DNL [!DNL dataset\segment export.cfg]].

1. Aggiornare i file alla directory dei profili del workbench dati.
1. Aggiornate il server di registro e il percorso [!DNL dataset\log processing.cfg] alla posizione in cui si stanno accumulando le VSL Sensor.
1. [Facoltativamente] , effettuate le stesse operazioni con i profili [!DNL Insight Profile Status] e [!DNL Insight Server Status]. Inoltre, i profili di stato devono essere rielaborati ogni notte con una finestra finale di due giorni. Aggiungere un&#39;attività pianificata di Windows: Il programma è [!DNL e:\insight_monitor\insight_reprocess.exe]. L&#39;argomento è [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Lascia [!DNL start in] vuoto. Aggiungi un&#39;altra attività pianificata per *&quot;stato del server di analisi&quot;*. *insight_reprocess.exe* richiede l&#39;accesso in lettura/scrittura al file *log processing.cfg* per aggiornare l&#39;ora di inizio.

1. Inoltre, i profili di stato devono essere rielaborati ogni notte con una finestra finale di due giorni. Aggiungere un&#39;attività pianificata di Windows: Il programma è *e:\insight_monitor\insight_reprocess.exe*. L&#39;argomento è - [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Lasciate *iniziare* da zero. Aggiungere un&#39;altra attività pianificata per [!DNL "insight server status"]. [!DNL insight_reprocess.exe] richiede l&#39;accesso in lettura/scrittura per [!DNL log processing.cfg] aggiornare l&#39;ora di inizio. Verificare che ciascun profilo stia leggendo le VSL del monitor durante l&#39;accumulo. Anche in questo caso, ci vorranno un po&#39; di tempo, probabilmente ore, a causa del volume estremamente basso.

## Note di installazione {#section-17722441ab0046fcbcb46b957d56230a}

* **Configurazione del profilo di monitoraggio in un ambiente** di test con licenza. Il pacchetto ambiente di test è incluso con l&#39;implementazione del workbench dati, che consente di installare e configurare l&#39;applicazione. Se si esegue l&#39;installazione su un server FSU o DPU di produzione, sarà necessario configurare il server per l&#39;esecuzione su una porta separata.
* **Implementazione di un nuovo sensore specifico per il profilo** di monitoraggio. Sarà necessario installare una nuova istanza di Sensor sul server che esegue il Profilo di Monitoraggio. Questo è in aggiunta all&#39;istanza di produzione del sensore. (Non è previsto alcun costo aggiuntivo per l&#39;installazione del sensore su un server di produzione o non di produzione specifico per il profilo di monitoraggio.)
* **Disattivare l&#39;agente di monitoraggio durante la manutenzione** del workbench dati. Per evitare di inquinare le metriche relative a tempi di attività e prestazioni, potete impostare la modalità di avvio del servizio su manuale per il servizio InsightServer (Omniture Insight Server). Un comodo comando PowerShell è *set-service -name insightserver -startuptype manuale*. Dopo la manutenzione, reimpostarla su Automatico: *set-service -name insightserver -startuptype automatico*. Un&#39;altra opzione consiste nel disattivare temporaneamente l&#39;attività pianificata dell&#39;agente di monitoraggio.
* **I profili di stato devono disporre di una finestra** finale per rilasciare host e profili precedenti nonché mappature dei profili host precedenti. Tuttavia, se la quantità di dati dell&#39;evento è così ridotta che il workbench dati non esegue il buffer, potrebbe essere necessario estendere leggermente la dimensione della finestra per consentirne l&#39;elaborazione.
* **L&#39;agente raccoglie lo stato** complessivo e meno recente del workbench dati, che viene riportato nell&#39;ora host locale, presumendo che i timestamp del log dati dell&#39;evento siano in UTC (come nei file VSL). Se le marche temporali dei dati dell’evento si trovano in un fuso orario non UTC, l’indicazione di ora verrà offset nel profilo di stato del profilo di Insight risultante. Se **tutti** i timestamp dei dati dell’evento si trovano nello stesso fuso orario, potete aggiungere tale offset a *Insight Profile Status\metrics\as of delay minutes.metric*.

* **Sono state introdotte due nuove dimensioni per aiutare il cliente a raggruppare i propri server in stati** diversi, come ad esempio server di produzione, pre-produzione, test e server in altri stati. Ad esempio, se cercate &quot;tempi di attività&quot;, i server vengono guardati solo in modalità di produzione. Di conseguenza, la dimensione Gruppo è solo un altro modo per raggruppare arbitrariamente i server per le vostre esigenze. Ad esempio, nel file Configurazione di monitoraggio è possibile impostare l&#39;host del reparto che esegue la manutenzione, ad esempio Operazioni, Sviluppo o Marketing.

