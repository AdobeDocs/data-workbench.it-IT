---
description: Informazioni sulle unità del file server Insight Server e sul processo di configurazione del file server.
title: Configurazione di un’unità del file server di Data Workbench
uuid: ccb65952-f017-4434-b2f8-74c274450834
exl-id: 19b8c08a-e9f2-47ab-ad9f-1fddfbd9d249
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1784'
ht-degree: 1%

---

# Configurazione di un’unità del file server di Data Workbench{#configuring-a-data-workbench-server-file-server-unit}

Informazioni sulle unità del file server Insight Server e sul processo di configurazione del file server.

<!--
c_abt_file_svr_units.xml
-->

È possibile configurare il server di Data Workbench (InsightServer64.exe) per l’esecuzione come File Server Unit (FSU) completando i parametri nel nodo **[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]** del file [!DNL Log Processing.cfg]. Quando il server di Data Workbench è configurato per l’esecuzione come FSU, memorizza i file di origine ( [!DNL .vsl] file, file di testo o file XML) a cui è possibile accedere rapidamente da più server di elaborazione (DPU). Quando le DPU in un cluster di server di Data Workbench accede alla FSU per leggere i file di registro, dividono i file di registro tra loro e garantiscono che lo stesso file non venga elaborato più di una volta.

>[!NOTE]
>
>Quando si imposta una FSU che serve un cluster di server di Data Workbench composto da cinque a dieci DPU, è necessario rendere FSU il server master del cluster.

Per informazioni sull’installazione di un cluster di server di Data Workbench, consulta la *Guida all’installazione e all’amministrazione dei prodotti server*.

<!--
c_file_svr_config_proc.xml
-->

Se la posizione è remota, il computer server di Data Workbench che elabora i dati si connette al computer remoto designato per leggere i registri.

Nel computer server di Data Workbench designato per essere eseguito come FSU, il file [!DNL Access Control.cfg] consente alle DPU di connettersi alla FSU e il file [!DNL Communications.cfg] mappa la posizione dei file di dati remoti. I passaggi del processo per configurare una FSU sono i seguenti:

1. Nel file [!DNL Log Processing.cfg] sul server di Data Workbench principale, specifica il tipo di origine dati e la posizione dell’origine. Vedere [Specifica dell&#39;origine dati](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383).

1. Nel file [!DNL Access Control.cfg] della FSU, modifica le autorizzazioni per consentire alle DPU di connettersi alla FSU per leggere i dati di registro. Vedere [Modifica delle autorizzazioni sull&#39;unità File Server](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef).

1. Nel file [!DNL Communications.cfg] della FSU, modifica le impostazioni delle voci [!DNL LoggingServer] e [!DNL FileServer] per specificare il percorso dei file di registro. Vedere [Specifica della posizione dei file di registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0).

1. Se stai configurando il profilo di set di dati da eseguire su un cluster di server di Data Workbench, devi anche impostare la FSU del cluster come server in cui sono create tutte le dimensioni del profilo:
(Solo per i cluster di server di Data Workbench) Nei file [!DNL Communications.cfg] e [!DNL cluster.cfg] nella FSU, aggiungere voci per un &quot;server di normalizzazione&quot; per rendere la FSU il server all’interno del cluster in cui sono costruite tutte le dimensioni. Vedere [Creazione di un server di normalizzazione centralizzato per un cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28).

Per istruzioni su come configurare un profilo di set di dati da elaborare da un cluster di server di Data Workbench, consulta la *Guida all’installazione e all’amministrazione dei prodotti server*.

>[!NOTE]
>
>Le istruzioni seguenti presuppongono che tutti i file di registro risiedano nella directory predefinita. Se desideri memorizzare i registri in un’altra directory o creare più percorsi di registro, contatta Adobe Consulting Services per discutere della configurazione specifica.

## Specifica dell&#39;origine dati {#section-d2b545db7ab142ffb4be32e040395383}

Quando si specificano le origini dati remote per un set di dati, è necessario specificare il tipo di origine dati e la posizione dei file di registro sul server di Data Workbench principale.

**Specifica dell’origine dati e della relativa posizione**

1. Apri il file [!DNL Log Processing.cfg] . Vedere [Modifica del file di configurazione dell&#39;elaborazione del registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

1. Aggiungi un&#39;origine dati [!DNL Sensor], un file di registro o XML. Vedere [File di registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e).

1. Completa il parametro Log Paths (Percorsi di registro). Vedere [File di sensore](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009), [File di registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e) o [Sorgenti di registro XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887). Assicurarsi di specificare un URI valido.

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
   <td colname="col2"> <p> <span class="wintitle"> Server comune </span> con nome nel certificato SSL del file server. </p> <p> Questo parametro è facoltativo se <span class="wintitle"> Use SSL</span> è impostato su false. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo </td> 
   <td colname="col2"> <p>Indirizzo del file server. Può essere lasciato vuoto se <span class="wintitle"> Name</span> corrisponde a <span class="wintitle"> SSL Server Common Name</span>. </p> <p> Ad esempio: <span class="filepath"> visual.mycompany.com</span> o 192.168.1.90. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta </td> 
   <td colname="col2"> Porta attraverso la quale il computer server di Data Workbench comunica con il file server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificato client SSL </td> 
   <td colname="col2"> Nome del file <span class="wintitle"> Certificato SSL</span> per il server di Data Workbench (<span class="filepath"> server_cert.pem</span>). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usa SSL </td> 
   <td colname="col2"> True o false. True indica che il file server utilizza <span class="wintitle"> SSL</span>. </td> 
  </tr> 
 </tbody> 
</table>

Se è necessario un server proxy per la connessione delle DPU alla FSU, è necessario completare i seguenti parametri:

| Parametro | Descrizione |
|---|---|
| Indirizzo proxy | Indirizzo di un server proxy che il server di Data Workbench deve utilizzare per accedere al file server. |
| Password proxy | Facoltativo. Password del server proxy. |
| Porta proxy | La porta del server proxy. Il valore predefinito è 8080. |
| Nome utente proxy | Facoltativo. Nome utente del server proxy. |

Di seguito è riportato un esempio di un [!DNL Log Server] definito nel file [!DNL Log Processing.cfg]. Origine log n. 1 è un&#39;origine LogFile che punta a una directory denominata Logs (notare l&#39;URI specificato nel parametro Log Paths ) sulla macchina denominata FSU01.

![](assets/cfg_LogProcessing_LogServer.png)

## Modifica delle autorizzazioni sull&#39;unità del file server {#section-b4a54b591b4e4435a728a67f194057ef}

Nel processo precedente, hai configurato un profilo per un dato set di dati per leggere i file di registro da una FSU. Ora è necessario modificare le autorizzazioni sulla FSU per consentire le connessioni dalle DPU che eseguono il profilo. La procedura seguente illustra come modificare il file delle autorizzazioni [!DNL Access Control.cfg].

**Per modificare le autorizzazioni sulla FSU**

1. Apri [!DNL Server Files Manager] per il server di Data Workbench che stai impostando come FSU e fai clic su **[!UICONTROL Access Control]** per visualizzarne il contenuto.

   Per informazioni sull&#39;apertura e l&#39;utilizzo di [!DNL Server Files Manager], vedere la *Guida utente alla Data Workbench*.

1. Nella finestra [!DNL Server Files Manager], fai clic su **[!UICONTROL Access Control]** per visualizzarne il contenuto. Il file [!DNL Access Control.cfg] si trova all&#39;interno di questa directory.

1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Access Control.cfg], quindi fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella colonna [!DNL Temp] per [!DNL Access Control.cfg].

1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Nella finestra [!DNL Access Control], fai clic su **[!UICONTROL Access Control Groups]** per visualizzarne il contenuto.

1. Fare clic con il pulsante destro del mouse sull&#39;etichetta numerica dell&#39;ultima [!DNL AccessGroup] nell&#39;elenco e fare clic su **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

1. Immetti un [!DNL Name] per il nuovo [!DNL AccessGroup]. Esempio: Connessione dei server in corso.

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Member]** sotto il nuovo [!DNL AccessGroup], quindi fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Immettere l’indirizzo IP della DPU del server di Data Workbench che si connette a questo file server.
1. Ripetere i passaggi 4 e 5 per tutte le altre DPU del server di Data Workbench che si connettono a questa FSU, incluse le DPU del server di Data Workbench in un cluster che deve accedere ai file di registro.
1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Read-Only Access]** sotto il nuovo [!DNL AccessGroup], quindi fai clic su **[!UICONTROL Add new]** > **[!UICONTROL URI]**.

1. Immettere il percorso dei file di registro memorizzati nel computer del file server. Utilizza le barre (/) nella specifica del percorso. Il percorso predefinito è /Logs/.
1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra, quindi fai clic su **[!UICONTROL Save]**.

1. Nella finestra [!DNL Server Files Manager] fare clic con il pulsante destro del mouse sul segno di spunta per [!DNL Access Control.cfg] nella colonna [!DNL Temp], quindi fare clic su **[!UICONTROL Save to]** > **[!UICONTROL server name]** per salvare le modifiche apportate localmente alla FSU del server di Data Workbench.

## Specifica della posizione dei file di registro {#section-f9a649bf1b2544feb10ad8820384edb0}

È necessario modificare il file [!DNL Communications.cfg] nella FSU per specificare il percorso dei file di registro.

**Per specificare il percorso dei file di registro**

1. Nella finestra [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. Il file [!DNL Communications.cfg] si trova all&#39;interno di questa directory.

1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Communications.cfg], quindi fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella colonna [!DNL Temp] per [!DNL Communications.cfg].

1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**.

1. Nella finestra [!DNL Communications.cfg], fai clic su **[!UICONTROL component]** per visualizzarne il contenuto.

1. Nella finestra [!DNL Communications.cfg], fai clic su **[!UICONTROL Servers]** per visualizzarne il contenuto. Possono essere visualizzati diversi server: File server, server di registrazione, Init Server, server di stato, server di invio o server di replica.

1. (Solo per le [!DNL Sensor] origini di registro) Trova il [!DNL LoggingServer], che è il punto in cui [!DNL Sensor] scrive i file di registro da elaborare dal server di Data Workbench, quindi fai clic sul numero corrispondente per visualizzare il menu. Modificare il parametro della directory di registro per riflettere la posizione desiderata dei file di registro. La directory di registro predefinita è la cartella Logs all’interno della directory di installazione del server di Data Workbench.

   Non modificare altri parametri per il parametro [!DNL LoggingServer].

   ![](assets/cfg_Communications_LoggingServer.png)

1. Individuare il FileServer che specifica il percorso dei file di log. Ci possono essere diversi File Server elencati sotto Server, quindi potrebbe essere necessario visualizzare il contenuto per molti di loro (facendo clic sul numero del server) per trovare il server desiderato.
1. Modificare i parametri [!DNL Local Path] e URI per FileServer in modo che riflettano la posizione dei file di log. L’esempio seguente mostra che i file di registro si trovano nella cartella Logs all’interno della directory di installazione del server di Data Workbench:

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >Se i parametri [!DNL Local Path] e URI vengono compilati come mostrato, è possibile accedere ai file di registro sulla FSU da qualsiasi server di Data Workbench facendo clic su [!DNL Logs] in [!DNL Server Files Manager].

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra di configurazione, quindi fai clic su **[!UICONTROL Save]**.

1. Nella finestra [!DNL Server Files Manager] fare clic con il pulsante destro del mouse sul segno di spunta per [!DNL Communications.cfg] nella colonna [!DNL Temp], quindi fare clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]*** per salvare le modifiche apportate localmente alla FSU del server di Data Workbench.

## Creazione di un server di normalizzazione centralizzato per un cluster {#section-2c1f57b683f94cc193bc069e886bba28}

Se stai configurando il profilo del set di dati da eseguire su un cluster di server di Data Workbench, devi rendere la FSU del cluster il server in cui sono create tutte le dimensioni del profilo.

L&#39;Adobe consiglia vivamente che la FSU del cluster funga da server master del cluster e da server di normalizzazione centralizzato.

Per rendere la FSU il server di normalizzazione centralizzato, è necessario aprire e modificare i file [!DNL Communications.cfg] e [!DNL Cluster.cfg] sulla FSU.

**Per fare della FSU il server di normalizzazione centralizzato**

1. Aggiungi una voce [!DNL NormalizeServer] al file [!DNL Communications.cfg] nella FSU.

   >[!NOTE]
   >
   >Se hai installato il pacchetto di versione completo per il server di Data Workbench v5.0 o versione successiva, il file [!DNL Communications.cfg] nella FSU deve avere già una voce [!DNL NormalizeServer]. Puoi seguire i passaggi seguenti per confermare che la voce esiste.

   1. Apri il file [!DNL Communications.cfg] in Data Workbench come descritto in [Specifica della posizione dei file di registro](#section-f9a649bf1b2544feb10ad8820384edb0).

   1. Fai clic su **[!UICONTROL component]** per visualizzarne il contenuto.
   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Servers]** e fai clic su **[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**.

   1. Nel parametro URI per [!DNL NormalizeServer], digita [!DNL /Cluster/].

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. Nella finestra [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL Communications.cfg] nella colonna [!DNL Temp], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server]**>* per salvare le modifiche apportate localmente alla FSU del server di Data Workbench.

1. Definire il server di normalizzazione centralizzata nel file [!DNL Cluster.cfg] sul server master nel cluster di server di Data Workbench.

   >[!NOTE]
   >
   >Se la FSU su cui si sta impostando il server di normalizzazione centralizzato non è il server di Data Workbench principale nel cluster, è necessario aggiungere gli indirizzi IP delle DPU nel cluster al gruppo di accesso [!DNL Cluster Servers] nel file [!DNL Access Control.cfg] della FSU. Per istruzioni su come aggiungere server al gruppo [!DNL Cluster Servers], vedere Aggiornamento del file di controllo di accesso per un cluster nella sezione *Guida all&#39;installazione e all&#39;amministrazione dei prodotti server.*

   1. Apri il [!DNL Profile Manager] nel profilo del set di dati, quindi fai clic su **[!UICONTROL Dataset]** per visualizzarne il contenuto. Il file [!DNL Cluster.cfg] si trova all&#39;interno di questa directory.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Cluster.cfg], quindi fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].

   1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.

   1. Aggiungere il testo evidenziato nel seguente frammento di file:

      [!DNL Cluster = ClusterConfig:]

      [!DNL Normalize Server = serverInfo:]

      [!DNL Address = string:]

      [!DNL Port = int: 80]

      [!DNL SSL Server Common Name = string: server common name]

      [!DNL Use SSL = bool: false]

      >[!NOTE]
      >
      >Quando si immette il nome comune di FSU per il parametro Nome comune del server SSL, la FSU utilizza il file [!DNL .address] per risolvere il nome comune. Per informazioni sul file [!DNL .address], vedere la *Guida all&#39;installazione e all&#39;amministrazione dei prodotti server*.

   1. Salvate il file.
   1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL Cluster.cfg] nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]*** per salvare le modifiche apportate localmente al profilo di set di dati.
