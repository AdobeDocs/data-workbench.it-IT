---
description: Informazioni sulle unità del file server Insight Server e sul processo di configurazione del file server.
solution: Analytics
title: Configurazione di un'unità del file server Workbench dati
topic: Data workbench
uuid: ccb65952-f017-4434-b2f8-74c274450834
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Configurazione di un&#39;unità del file server Workbench dati{#configuring-a-data-workbench-server-file-server-unit}

Informazioni sulle unità del file server Insight Server e sul processo di configurazione del file server.

<!--
c_abt_file_svr_units.xml
-->

È possibile configurare il server workbench dati (InsightServer64.exe) per l&#39;esecuzione come unità File Server (FSU) completando i parametri nel nodo **[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]** del [!DNL Log Processing.cfg] file. Quando il server workbench dati è configurato per l&#39;esecuzione come FSU, memorizza i file sorgente ( [!DNL .vsl] file, file di testo o file XML) a cui è possibile accedere rapidamente da più server di elaborazione (DPU). Quando i DPU in un cluster di server workbench dati accedono all&#39;FSU per leggere i file di registro, dividono i file di registro tra di essi e garantiscono che lo stesso file non venga elaborato più di una volta.

>[!NOTE]
>
>Quando si configura un FSU che serve un cluster di server workbench di dati composto da cinque o dieci unità di elaborazione dati, è necessario rendere FSU il server master del cluster.

Per informazioni sull&#39;installazione di un cluster di server workbench dati, vedere la Guida all&#39;installazione e all&#39;amministrazione dei prodotti *server*.

<!--
c_file_svr_config_proc.xml
-->

Se la posizione è una posizione remota, il computer del server del workbench dati che elabora i dati si connette al computer remoto designato per leggere i registri.

Nel computer server workbench dati designato per l&#39;esecuzione come FSU, il [!DNL Access Control.cfg] file consente alle DPU di connettersi alla FSU, e il [!DNL Communications.cfg] file mappa la posizione dei file di dati remoti. La procedura per configurare un FSU è la seguente:

1. Nel [!DNL Log Processing.cfg] file sul server workbench dati principale, specificare il tipo di origine dati e la posizione dell&#39;origine. Vedere [Specifica dell&#39;origine](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383)dati.

1. Nel [!DNL Access Control.cfg] file sull&#39;FSU, modificare le autorizzazioni per consentire agli UDE di connettersi all&#39;FSU per leggere i dati di registro. Consultate [Modifica delle autorizzazioni nell&#39;unità](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef)del file server.

1. Nel [!DNL Communications.cfg] file dell&#39;FSU, modificare le impostazioni per le [!DNL LoggingServer] voci e [!DNL FileServer] specificare la posizione dei file di registro. Vedere [Specifica del percorso dei file](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0)di registro.

1. Se si sta configurando il profilo del set di dati per l&#39;esecuzione su un cluster di server workbench dati, è inoltre necessario fare in modo che il server FSU del cluster in cui sono costruite tutte le dimensioni del profilo:
(Solo per i cluster di server workbench di dati) Nei [!DNL Communications.cfg] file e [!DNL cluster.cfg] nei file dell&#39;FSU, aggiungere voci per un &quot;server di normalizzazione&quot; per fare dell&#39;FSU il server all&#39;interno del cluster in cui sono costruite tutte le dimensioni. Vedere [Creazione di un server di normalizzazione centralizzato per un cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28).

Per istruzioni su come configurare un profilo di dataset da elaborare da un cluster di server workbench dati, vedere la Guida all&#39;installazione e all&#39;amministrazione dei prodotti *server*.

>[!NOTE]
>
>Le seguenti istruzioni presuppongono che tutti i file di registro risiedano nella directory predefinita. Se desiderate memorizzare i registri in un’altra directory o creare più percorsi di registro, contattate Adobe Consulting Services per discutere della configurazione specifica.

## Specifica dell&#39;origine dati {#section-d2b545db7ab142ffb4be32e040395383}

Quando si specificano le origini dati remote per un dataset, è necessario specificare il tipo di origine dati e la posizione dei file di registro nel server workbench dati master.

**Specifica dell&#39;origine dati e della relativa posizione**

1. Open the [!DNL Log Processing.cfg] file. Vedere [Modifica del file](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)di configurazione dell&#39;elaborazione del registro.

1. Aggiungere un&#39;origine dati [!DNL Sensor], un file di registro o XML. See [Log Files](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e).

1. Completate il parametro Log Paths (Percorsi di registro). Consultate File [](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)Sensor, File [di](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)registro o Sorgenti [di registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)XML. Accertatevi di specificare un URI valido.

1. Completare i parametri del server di registro definiti nella tabella seguente:

<table id="table_5881B8DEFF984BC7A620CEEA3A637912"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome che identifica il file server remoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome comune server SSL </td> 
   <td colname="col2"> <p> <span class="wintitle"> Nome</span> comune server elencato nel certificato SSL del file server. </p> <p> Questo parametro è facoltativo se <span class="wintitle"> Usa SSL</span> è impostato su false. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo </td> 
   <td colname="col2"> <p>Indirizzo del file server. Può essere lasciato vuoto se <span class="wintitle"> Name</span> corrisponde a <span class="wintitle"> SSL Server Common Name</span>. </p> <p> Ad esempio: visual.mycompany.com <span class="filepath"></span> o 192.168.1.90. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta </td> 
   <td colname="col2"> Porta attraverso la quale il computer server workbench dati comunica con il file server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificato client SSL </td> 
   <td colname="col2"> Nome del file del certificato <span class="wintitle"> SSL per il server workbench dati (</span> server_cert.pem<span class="filepath"></span>). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usa SSL </td> 
   <td colname="col2"> True o false. True indica che il file server utilizza <span class="wintitle"> SSL</span>. </td> 
  </tr> 
 </tbody> 
</table>

Se è necessario un server proxy per il collegamento delle unità DPU all&#39;unità FSU, è necessario completare i seguenti parametri:

| Parametro | Descrizione |
|---|---|
| Indirizzo proxy | Indirizzo di un server proxy che il server workbench dati deve utilizzare per accedere al file server. |
| Password proxy | Facoltativo. La password del server proxy. |
| Porta proxy | La porta del server proxy. Il valore predefinito è 8080. |
| Nome utente proxy | Facoltativo. Nome utente per il server proxy. |

Di seguito è riportato un esempio di una definizione [!DNL Log Server] nel [!DNL Log Processing.cfg] file. L&#39;origine di registro n. 1 è un&#39;origine LogFile che punta a una directory denominata Logs (notare l&#39;URI specificato nel parametro Log Paths) sul computer denominato FSU01.

![](assets/cfg_LogProcessing_LogServer.png)

## Modifica delle autorizzazioni nell&#39;unità del file server {#section-b4a54b591b4e4435a728a67f194057ef}

Nel processo precedente, era stato configurato un profilo per un dato dataset per leggere i file di registro da un FSU. Ora è necessario modificare le autorizzazioni sull&#39;FSU per consentire le connessioni dalle DPU che eseguono il profilo. La procedura seguente illustra come modificare il file delle autorizzazioni [!DNL Access Control.cfg].

**Per modificare le autorizzazioni sull&#39;FSU**

1. Aprire la [!DNL Server Files Manager] macchina del server workbench dati che si sta configurando come FSU e fare clic **[!UICONTROL Access Control]** per visualizzarne il contenuto.

   Per informazioni sull&#39;apertura e l&#39;utilizzo di [!DNL Server Files Manager], vedere la Guida *utente di Workbench* dati.

1. Nella [!DNL Server Files Manager] finestra, fate clic **[!UICONTROL Access Control]** per visualizzarne il contenuto. Il [!DNL Access Control.cfg] file si trova all&#39;interno di questa directory.

1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Access Control.cfg], quindi scegliere **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Access Control.cfg].

1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato sotto la [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Nella [!DNL Access Control] finestra, fate clic **[!UICONTROL Access Control Groups]** per visualizzarne il contenuto.

1. Fare clic con il pulsante destro del mouse sull&#39;etichetta numerica per l&#39;ultima [!DNL AccessGroup] dell&#39;elenco e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

1. Immettete un valore [!DNL Name] per il nuovo [!DNL AccessGroup]. Esempio: Connessione dei server in corso.

1. Fare clic con il pulsante destro del mouse **[!UICONTROL Member]** sotto il nuovo [!DNL AccessGroup], quindi scegliere **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Immettere l&#39;indirizzo IP per il DPU del server workbench dati che si connette a questo file server.
1. Ripetere i passaggi 4 e 5 per qualsiasi altro DPU del server workbench dati che si connetta a questo FSU, inclusi i DPU del server workbench dati in un cluster che deve accedere ai file di registro.
1. Fare clic con il pulsante destro del mouse **[!UICONTROL Read-Only Access]** sotto il nuovo [!DNL AccessGroup], quindi scegliere **[!UICONTROL Add new]** > **[!UICONTROL URI]**.

1. Immettere il percorso dei file di registro memorizzati nel computer del file server. Utilizzate le barre (/) nella specifica del percorso. Il percorso predefinito è /Logs/.
1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra, quindi scegliere **[!UICONTROL Save]**.

1. Nella [!DNL Server Files Manager] finestra, fare clic con il pulsante destro del mouse sul segno di spunta [!DNL Access Control.cfg] nella [!DNL Temp] colonna, quindi fare clic su **[!UICONTROL Save to]** > **[!UICONTROL server name]** per salvare le modifiche locali apportate all&#39;FSU del server del workbench dati.

## Specifica della posizione dei file di registro {#section-f9a649bf1b2544feb10ad8820384edb0}

È necessario modificare il [!DNL Communications.cfg] file sull&#39;FSU per specificare il percorso dei file di registro.

**Per specificare il percorso dei file di registro**

1. Nella [!DNL Server Files Manager] finestra, fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL Communications.cfg] file si trova all&#39;interno di questa directory.

1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Communications.cfg], quindi scegliere **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Communications.cfg].

1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato sotto la [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**.

1. Nella [!DNL Communications.cfg] finestra, fate clic **[!UICONTROL component]** per visualizzarne il contenuto.

1. Nella [!DNL Communications.cfg] finestra, fate clic **[!UICONTROL Servers]** per visualizzarne il contenuto. Potrebbero essere visualizzati diversi server: File server, server di registrazione, server Init, server di stato, server Send o server Replicate.

1. (Solo per le origini [!DNL Sensor] di registro) Trovare il [!DNL LoggingServer], che è dove [!DNL Sensor] scrive i file di registro da elaborare dal server workbench dati, quindi fare clic sul relativo numero per visualizzare il menu. Modificate il parametro Directory di registro per riflettere la posizione desiderata dei file di registro. La directory di registro predefinita è la cartella Logs all&#39;interno della directory di installazione del server workbench dati.

   Non modificate nessun altro parametro per il [!DNL LoggingServer].

   ![](assets/cfg_Communications_LoggingServer.png)

1. Individuare il FileServer che specifica il percorso dei file di registro. Potrebbero essere presenti diversi file server elencati in Server, quindi potrebbe essere necessario visualizzare il contenuto per molti di essi (facendo clic sul numero del server) per trovare il server desiderato.
1. Modificare i parametri [!DNL Local Path] e URI di FileServer in modo che riflettano il percorso dei file di registro. L’esempio seguente mostra che i file di registro risiedono nella cartella Logs all’interno della directory di installazione del server workbench dati:

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >Se i parametri [!DNL Local Path] e URI sono popolati come mostrato, è possibile accedere ai file di registro sull&#39;FSU da qualsiasi server workbench dati facendo clic [!DNL Logs] nel [!DNL Server Files Manager].

1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra di configurazione, quindi fare clic su **[!UICONTROL Save]**.

1. Nella [!DNL Server Files Manager] finestra fare clic con il pulsante destro del mouse sul segno di spunta [!DNL Communications.cfg] nella [!DNL Temp] colonna, quindi fare clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>* per salvare le modifiche locali apportate all&#39;FSU del server workbench dati.

## Creazione di un server di normalizzazione centralizzato per un cluster {#section-2c1f57b683f94cc193bc069e886bba28}

Se si sta configurando il profilo del set di dati per l&#39;esecuzione su un cluster di server workbench dati, è necessario fare in modo che il server FSU del cluster sia quello in cui sono costruite tutte le dimensioni del profilo.

Adobe consiglia vivamente di utilizzare l&#39;FSU del cluster come server master del cluster e come server di normalizzazione centralizzato.

Per rendere il FSU il server di normalizzazione centralizzato, è necessario aprire e modificare i file [!DNL Communications.cfg] e [!DNL Cluster.cfg] i file sull&#39;FSU.

**Per rendere FSU il server di normalizzazione centralizzato**

1. Aggiungere una [!DNL NormalizeServer] voce al [!DNL Communications.cfg] file sull&#39;FSU.

   >[!NOTE]
   >
   >Se avete installato il pacchetto di rilascio completo per il server workbench dati v5.0 o versione successiva, il [!DNL Communications.cfg] file sul FSU deve già avere una [!DNL NormalizeServer] voce. Per confermare l’esistenza della voce, effettuate le seguenti operazioni.

   1. Aprire il [!DNL Communications.cfg] file in workbench dati come descritto in [Specifica della posizione dei file](#section-f9a649bf1b2544feb10ad8820384edb0)di registro.

   1. Fate clic **[!UICONTROL component]** per visualizzarne il contenuto.
   1. Fare clic con il pulsante destro del mouse **[!UICONTROL Servers]** e scegliere **[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**.

   1. Nel parametro URI per il [!DNL NormalizeServer], digitate [!DNL /Cluster/].

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra, quindi fare clic **[!UICONTROL Save]**.

   1. Nella [!DNL Server Files Manager] finestra fare clic con il pulsante destro del mouse sul segno di spunta [!DNL Communications.cfg] nella [!DNL Temp] colonna, quindi fare clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server]**>* nome per salvare le modifiche locali apportate al server FSU del workbench dati.

1. Definire il server di normalizzazione centralizzato nel [!DNL Cluster.cfg] file sul server master nel cluster di server workbench dati.

   >[!NOTE]
   >
   >Se l&#39;FSU su cui si sta configurando il server di normalizzazione centralizzato non è il server workbench dati master nel cluster, è necessario aggiungere gli indirizzi IP delle DPU nel cluster al gruppo di [!DNL Cluster Servers] accesso nel [!DNL Access Control.cfg] file dell&#39;FSU. Per istruzioni sull&#39;aggiunta di server al [!DNL Cluster Servers] gruppo, vedere Aggiornamento del file di controllo dell&#39;accesso per un cluster nella sezione Installazione e amministrazione dei prodotti *server.*

   1. Aprite il [!DNL Profile Manager] profilo del set di dati, quindi fate clic **[!UICONTROL Dataset]** per visualizzarne il contenuto. Il [!DNL Cluster.cfg] file si trova all&#39;interno di questa directory.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Cluster.cfg], quindi scegliere **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.

   1. Aggiungere il testo evidenziato nel seguente frammento di file:

      [!DNL Cluster = ClusterConfig:]

      [!DNL Normalize Server = serverInfo:]

      [!DNL Address = string:]

      [!DNL Port = int: 80]

      [!DNL SSL Server Common Name = string: server common name]

      [!DNL Use SSL = bool: false]

      >[!NOTE]
      >
      >Quando si immette il nome comune di FSU per il parametro Nome comune del server SSL, il FSU utilizza il [!DNL .address] file per risolvere il nome comune. Per informazioni sul [!DNL .address] file, vedere la Guida all&#39;installazione e all&#39;amministrazione dei prodotti *server*.

   1. Salvate il file.
   1. Nella [!DNL Profile Manager], fare clic con il pulsante destro del mouse sul segno di spunta [!DNL Cluster.cfg] nella [!DNL User] colonna, quindi fare clic su **[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]*** per salvare le modifiche locali apportate al profilo del dataset.
