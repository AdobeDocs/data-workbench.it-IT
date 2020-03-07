---
description: Effettuare le seguenti operazioni per eseguire l'aggiornamento al workbench dati v6.1 dall'installazione del workbench dati v6.0x.
solution: Analytics
title: Aggiornamento di Workbench dati da 6.0 a 6.1
topic: Data workbench
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Aggiornamento di Workbench dati da 6.0 a 6.1{#data-workbench-to-upgrade}

Effettuare le seguenti operazioni per eseguire l&#39;aggiornamento al workbench dati v6.1 dall&#39;installazione del workbench dati v6.0x.

**Passaggio 1**: Aggiornamento [server](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Passaggio 2**: Aggiornamento [del server di report](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Passaggio 3**: Aggiornamento [client](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>I componenti server, server di report e client vengono aggiornati per essere eseguiti sui sistemi operativi Windows a 64 bit.

## Aggiornamento server {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Per aggiornare i **[!UICONTROL Server v6.1]** componenti, effettuate le seguenti operazioni:

1. Utilizzando il **[!UICONTROL Software and Docs]** profilo, aprite l’ **[!UICONTROL Start Here]** area di lavoro e scaricate tutti i pacchetti server necessari in una cartella locale.

   * Scaricate **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** le cartelle zip ed estraete tutti i file.

      Il pacchetto Server include **[!UICONTROL Lookup]** e **[!UICONTROL Profile]** cartelle con **[!UICONTROL Base]** e **[!UICONTROL Transform]** profili per aggiornare il server.

      * Scaricate le **[!UICONTROL Profiles]** cartelle.
      * Scaricate le **[!UICONTROL Lookup]** cartelle.
      * Scaricate il **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** pacchetto.
      * Scaricate **[!UICONTROL Sensor]** file aggiuntivi **[!UICONTROL Documentation]** e **[!UICONTROL Dashboard]** file in base alle esigenze del sistema.

1. Arrestate il **[!UICONTROL Adobe Insight Server]** servizio.

   ![](assets/install_server_download1.png)

1. Dal pacchetto scaricato **[!UICONTROL Server]** :

   1. Sostituite la [!DNL Server\Bin] cartella per aggiornare i file [!DNL InsightServer64.exe] e di supporto.

   1. Sostituite la [!DNL Server\Profiles] cartella. Potete sovrascrivere tutti i file.
   1. Aggiornate la [!DNL Server\Lookups] cartella. Aggiungete i file scaricati di recente ai file personalizzati già presenti nella cartella.
   1. Sostituisci la [!DNL Server\Software] cartella da aggiornare [!DNL Insight.exe] e [!DNL ReportServer.exe]
   1. Aggiornate la [!DNL Server\Scripts] cartella per aggiornarla [!DNL TnTSend.exe].

1. Se utilizzi **[!UICONTROL DeviceAtlas]**, dovrai [aggiornare il bundle](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) che si trova nella [!DNL Server\Lookups] cartella.

1. Configurate il [!DNL Profile.cfg] file in modo che il vettore venga aggiornato per riflettere il numero di elementi per ciascun profilo.

   Ad esempio, per abilitare il **[!UICONTROL Predictive Analytics]** profilo sarà necessario aggiornare questa impostazione.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configurate e salvate il file PAServer.cfg per la funzione Predictive Analytics.

   Se desiderate inviare i processi Predictive Analytics ai server, dovrete configurare il [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] file per gestire gli invii del clustering lato server.

   Il profilo personalizzato deve ereditare le impostazioni dal profilo di configurazione Predictive Analytics, consentendo di configurare e salvare il [!DNL PAServer.cfg] file in base all&#39;implementazione del sito.

1. Definite il **[!UICONTROL Log Source ID]**.

   L’elemento **[!UICONTROL Recording of Rows per Log Source]** è stato aggiunto in **[!UICONTROL v6.04]** e definito nel [!DNL Log Processing.cfg] file del profilo personalizzato aggiungendo un nome univoco **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Se non hai definito l&#39;ID origine registro, verrà visualizzato il seguente errore:

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. Poiché l’aggiornamento [!DNL EventMessages.dll] è stato eseguito, è necessario annullare la registrazione e quindi registrarla **[!UICONTROL Adobe Insight Server]** in tutto il cluster.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Avviate il **[!UICONTROL Adobe Insight Server]** servizio nel cluster.

Installazione del server completata.

## Aggiornamento del server di report {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Prima di eseguire l&#39;aggiornamento a **[!UICONTROL Report Server v6.1]**, è necessario prima eseguire l&#39;aggiornamento a **[!UICONTROL Server v6.1]**.

1. Usando il **[!UICONTROL Software and Docs]** profilo, scaricate **[!UICONTROL v6.1]** il **[!UICONTROL Report Server]** pacchetto in una cartella locale.

1. Copiate **[!UICONTROL Report Server 6.1]** dal pacchetto scaricato e sostituite i pacchetti di profilo.

   >[!NOTE]
   >
   >Il [!DNL Insight.zbin] file nella [!DNL install] cartella è un file di backup utilizzato per la localizzazione e deve essere presente nella [!DNL install] directory. Questo file o altri [!DNL .zbin] file verranno utilizzati a seconda delle impostazioni della riga di comando passate all&#39;avvio.

1. (Facoltativo) Il workbench dati supporta attualmente l&#39;inglese (-en-us) e il cinese (-zh-cn). È necessario impostare un font per supportare i caratteri a byte singolo e doppio:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   Nel sistema operativo Windows devono essere installati anche i font elencati.

1. Configurare [!DNL Report Server v6.1] per la localizzazione.

   1. Arrestate il **[!UICONTROL Adobe Insight Report Server]** servizio.
   1. Avviate un prompt dei comandi come &quot;Amministratore&quot;.
   1. Andate alla [!DNL install] cartella del server di report.
   1. Eliminate il servizio Report Server utilizzando il comando seguente:

      ```
      ReportServer.exe /unregserver
      ```

   1. Avviate il servizio in base alle impostazioni della lingua:

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)  
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Per verificare che il server di report sia in esecuzione con le impostazioni corrette, aprite **[!UICONTROL Windows Service Manager]** e fate clic con il pulsante destro del mouse **[!UICONTROL Adobe Insight Report Server - Properties]**. Nel percorso dell&#39;eseguibile vengono visualizzate le impostazioni aggiornate della riga di comando.

L&#39;installazione del server di report ora è completa.

## Aggiornamento client {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Prima di eseguire l&#39;aggiornamento a **[!UICONTROL Client v6.1]**, l&#39;amministratore deve prima effettuare l&#39;aggiornamento a **[!UICONTROL Insight Server v6.1.]**

1. Avviate [!DNL Insight.exe] ma non collegatevi ad alcun profilo.
1. Modificate il [!DNL Insight.cfg] file.

   ```
   Update Software = bool: true
   ```

1. Connettiti al tuo profilo.

   Consentite al client di effettuare la sincronizzazione con il server e il client verrà aggiornato con i profili client v6.1, gli eseguibili e i file di configurazione più recenti.

   >[!NOTE]
   >
   >Il [!DNL Insight.zbin] file nella [!DNL install] cartella è un file di backup utilizzato per la localizzazione e deve essere presente. Questo file o altri [!DNL .zbin] file verranno utilizzati a seconda delle impostazioni della riga di comando passate all&#39;avvio.

   Consultate [Impostazione delle lingue](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) localizzate per aggiungere un [!DNL insight.zbin] file necessario per le impostazioni localizzate.

**Impostazioni client aggiuntive**

Prima di configurare [!DNL Insight.exe] e supportare i file, è necessario uscire dall&#39;applicazione client.

Per installare il cinese semplificato:

1. Creare una scelta rapida che consenta di passare l&#39;impostazione della riga di comando al [!DNL Insight.exe] file.

   ```
   Insight.exe -zh-cn
   ```

1. Configurare [!DNL Insight.cfg] per supportare i caratteri di font a byte singolo e doppio.

   Data Workbench supporta attualmente sia l&#39;inglese che il cinese semplificato. È possibile selezionare i font per supportare entrambe le lingue:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

   Nel sistema operativo Windows devono essere installati anche i font richiesti.

1. Avviate la scelta rapida creata per sincronizzare i profili e l&#39;aggiornamento. [!DNL zbin] file.

Per utilizzare l&#39;IME (Input Method Editor).

L&#39;IME consente di inserire caratteri internazionali.

1. Aggiornate il [!DNL Insight.cfg] file con le seguenti impostazioni:

   ```
   Localized IME = bool: true
   ```

1. Avviate la scelta rapida creata per sincronizzare i profili e il [!DNL .zbin] file aggiornato.

L&#39;installazione client è stata completata.
