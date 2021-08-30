---
description: Per eseguire l’aggiornamento a Data Workbench v6.1 dall’installazione di Data Workbench v6.0x, effettua le seguenti operazioni.
title: Aggiornamento a Data Workbench da 6.0 a 6.1
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
exl-id: 559e1942-561c-4270-9670-550177730cdb,2a337d2e-c70e-4f35-a6c2-c3a7f50a0800
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 1%

---

# Aggiornamento a Data Workbench da 6.0 a 6.1{#data-workbench-to-upgrade}

Per eseguire l’aggiornamento a Data Workbench v6.1 dall’installazione di Data Workbench v6.0x, effettua le seguenti operazioni.

**Passaggio 1**:  [Aggiornamento del server](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Passaggio 2**:  [Aggiornamento del server di rapporto](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Passaggio 3**:  [Aggiornamento client](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>I componenti server, server di report e client vengono aggiornati per l&#39;esecuzione su sistemi operativi Windows a 64 bit.

## Aggiornamento server {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Segui questi passaggi per aggiornare i componenti **[!UICONTROL Server v6.1]** :

1. Utilizzando il profilo **[!UICONTROL Software and Docs]**, apri l&#39;area di lavoro **[!UICONTROL Start Here]** e scarica tutti i pacchetti server necessari in una cartella locale.

   * Scarica le cartelle zip **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** ed estrai tutti i file.

      Il pacchetto Server include le cartelle **[!UICONTROL Lookup]** e **[!UICONTROL Profile]** con profili **[!UICONTROL Base]** e **[!UICONTROL Transform]** per aggiornare il server.

      * Scarica le cartelle **[!UICONTROL Profiles]** .
      * Scarica le cartelle **[!UICONTROL Lookup]** .
      * Scarica il pacchetto **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** .
      * Scarica ulteriori file **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]** e **[!UICONTROL Dashboard]** in base alle esigenze del sistema.

1. Arresta il servizio **[!UICONTROL Adobe Insight Server]**.

   ![](assets/install_server_download1.png)

1. Dal pacchetto **[!UICONTROL Server]** scaricato:

   1. Sostituisci la cartella [!DNL Server\Bin] per aggiornare [!DNL InsightServer64.exe] e i file di supporto.

   1. Sostituisci la cartella [!DNL Server\Profiles]. È possibile sovrascrivere tutti i file.
   1. Aggiorna la cartella [!DNL Server\Lookups] . Aggiungere i file appena scaricati ai file personalizzati già presenti nella cartella.
   1. Sostituisci la cartella [!DNL Server\Software] per aggiornare [!DNL Insight.exe] e [!DNL ReportServer.exe]
   1. Aggiorna la cartella [!DNL Server\Scripts] per aggiornare [!DNL TnTSend.exe].

1. Se utilizzi **[!UICONTROL DeviceAtlas]**, dovrai [aggiornare il bundle](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) che si trova nella cartella [!DNL Server\Lookups].

1. Configura il file [!DNL Profile.cfg] in modo che il vettore venga aggiornato per riflettere il numero di elementi per ciascun profilo.

   Ad esempio, per abilitare il profilo **[!UICONTROL Predictive Analytics]** dovrai aggiornare questa impostazione.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configura e salva il file PAServer.cfg per la funzione Predictive Analytics .

   Se desideri inviare i processi di Predictive Analytics ai server, dovrai configurare il file [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] per gestire gli invii dei clustering lato server.

   Il profilo personalizzato deve ereditare le impostazioni dal profilo di configurazione di Predictive Analytics, consentendoti di configurare e salvare il file [!DNL PAServer.cfg] in base all’implementazione del sito.

1. Definisci il **[!UICONTROL Log Source ID]**.

   Il **[!UICONTROL Recording of Rows per Log Source]** è stato aggiunto in **[!UICONTROL v6.04]** e definito nel file [!DNL Log Processing.cfg] del profilo personalizzato aggiungendo un nome univoco **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Se non hai definito l’ID di origine del registro, riceverai il seguente errore:

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. Poiché il [!DNL EventMessages.dll] è stato aggiornato, è necessario annullare la registrazione e quindi registrare il **[!UICONTROL Adobe Insight Server]** nel cluster.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Avvia il servizio **[!UICONTROL Adobe Insight Server]** nel cluster.

Installazione del server completata.

## Aggiornamento del server di rapporto {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Prima di eseguire l&#39;aggiornamento a **[!UICONTROL Report Server v6.1]**, è necessario prima eseguire l&#39;aggiornamento a **[!UICONTROL Server v6.1]**.

1. Utilizzando il profilo **[!UICONTROL Software and Docs]** , scarica **[!UICONTROL v6.1]** dal pacchetto **[!UICONTROL Report Server]** in una cartella locale.

1. Copia **[!UICONTROL Report Server 6.1]** dal pacchetto scaricato e sostituisci i pacchetti di profilo.

   >[!NOTE]
   >
   >Il file [!DNL Insight.zbin] nella cartella [!DNL install] è un file di backup utilizzato per la localizzazione e deve essere presente nella directory [!DNL install]. Questo file o altri file [!DNL .zbin] verranno utilizzati a seconda delle impostazioni della riga di comando passate all&#39;avvio.

1. (facoltativo) Data Workbench supporta attualmente le lingue inglese (-en-us) e cinese (-zh-cn). È necessario impostare un font per supportare i caratteri a byte singolo e doppio:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   Nel sistema operativo Windows devono essere installati anche i font elencati.

1. Configura [!DNL Report Server v6.1] per la localizzazione.

   1. Arresta il servizio **[!UICONTROL Adobe Insight Report Server]**.
   1. Avviare un prompt dei comandi come &quot;Amministratore&quot;.
   1. Passa alla cartella Server di rapporto [!DNL install] .
   1. Elimina il servizio Report Server utilizzando il seguente comando:

      ```
      ReportServer.exe /unregserver
      ```

   1. Avvia il servizio in base alle impostazioni della lingua:

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)  
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Per verificare che Report Server sia in esecuzione con le impostazioni corrette, apri **[!UICONTROL Windows Service Manager]** e fai clic con il pulsante destro del mouse su **[!UICONTROL Adobe Insight Report Server - Properties]**. Il percorso dell&#39;eseguibile visualizza le impostazioni aggiornate della riga di comando.

Installazione del server di report completata.

## Aggiornamento client {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Prima di eseguire l&#39;aggiornamento a **[!UICONTROL Client v6.1]**, l&#39;amministratore deve prima eseguire l&#39;aggiornamento a **[!UICONTROL Insight Server v6.1.]**

1. Avvia [!DNL Insight.exe] ma non ti connetti ad alcun profilo.
1. Modifica il file [!DNL Insight.cfg].

   ```
   Update Software = bool: true
   ```

1. Collegati al tuo profilo.

   Consenti la sincronizzazione del client con il server e il client verrà aggiornato con i profili client v6.1, i file eseguibili e i file di configurazione più recenti.

   >[!NOTE]
   >
   >Il file [!DNL Insight.zbin] nella cartella [!DNL install] è un file di backup utilizzato per la localizzazione e deve essere presente. Questo file o altri file [!DNL .zbin] verranno utilizzati a seconda delle impostazioni della riga di comando passate all&#39;avvio.

   Per aggiungere un file [!DNL insight.zbin] necessario per le impostazioni localizzate, consulta [configurazione delle lingue localizzate](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) .

**Impostazioni client aggiuntive**

Prima di configurare [!DNL Insight.exe] e i file di supporto, è necessario uscire dall&#39;applicazione client.

Per installare il cinese semplificato:

1. Crea una scelta rapida che passa l&#39;impostazione della riga di comando al file [!DNL Insight.exe].

   ```
   Insight.exe -zh-cn
   ```

1. Configura [!DNL Insight.cfg] per supportare i caratteri di font a byte singolo e doppio.

   Data Workbench supporta attualmente sia l’inglese che il cinese semplificato. È possibile selezionare i font per supportare entrambe le lingue seguenti:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

   Nel sistema operativo Windows devono essere installati anche i font richiesti.

1. Avvia la scelta rapida creata per sincronizzare i profili e la versione aggiornata . [!DNL zbin] file.

Per utilizzare l&#39;IME (Input Method Editor).

IME consente di inserire caratteri internazionali.

1. Aggiorna il file [!DNL Insight.cfg] con le seguenti impostazioni:

   ```
   Localized IME = bool: true
   ```

1. Avvia la scelta rapida creata per sincronizzare i profili e il file [!DNL .zbin] aggiornato.

Installazione client completata.
