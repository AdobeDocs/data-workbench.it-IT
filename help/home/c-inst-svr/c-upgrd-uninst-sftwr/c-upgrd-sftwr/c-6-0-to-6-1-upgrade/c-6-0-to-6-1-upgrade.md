---
description: Per eseguire l’aggiornamento a Data Workbench v6.1 dall’installazione di Data Workbench v6.0x, effettua le seguenti operazioni.
title: Aggiornamento a Data Workbench da 6.0 a 6.1
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
exl-id: 559e1942-561c-4270-9670-550177730cdb,2a337d2e-c70e-4f35-a6c2-c3a7f50a0800
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 1%

---

# Aggiornamento a Data Workbench da 6.0 a 6.1{#data-workbench-to-upgrade}

{{eol}}

Per eseguire l’aggiornamento a Data Workbench v6.1 dall’installazione di Data Workbench v6.0x, effettua le seguenti operazioni.

**Passaggio 1**: [Aggiornamento del server](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Passaggio 2**: [Aggiornamento del server di rapporto](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Passaggio 3**: [Aggiornamento client](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>I componenti server, server di report e client vengono aggiornati per l&#39;esecuzione su sistemi operativi Windows a 64 bit.

## Aggiornamento server {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Segui questi passaggi per aggiornare **[!UICONTROL Server v6.1]** componenti:

1. Utilizzo della **[!UICONTROL Software and Docs]** profilo, apri **[!UICONTROL Start Here]** e scarica tutti i pacchetti server necessari in una cartella locale.

   * Scarica **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip cartelle ed estrai tutti i file.

      Il pacchetto Server include **[!UICONTROL Lookup]** e **[!UICONTROL Profile]** cartelle con **[!UICONTROL Base]** e **[!UICONTROL Transform]** profili per aggiornare il server.

      * Scarica la **[!UICONTROL Profiles]** cartelle.
      * Scarica la **[!UICONTROL Lookup]** cartelle.
      * Scarica la **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** pacchetto.
      * Scarica ulteriori informazioni **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]** e **[!UICONTROL Dashboard]** file necessari per il sistema.

1. Interrompi **[!UICONTROL Adobe Insight Server]** servizio.

   ![](assets/install_server_download1.png)

1. Dal download **[!UICONTROL Server]** pacchetto:

   1. Sostituisci il [!DNL Server\Bin] per aggiornare la cartella [!DNL InsightServer64.exe] e i file di supporto.

   1. Sostituisci il [!DNL Server\Profiles] cartella. È possibile sovrascrivere tutti i file.
   1. Aggiorna [!DNL Server\Lookups] cartella. Aggiungere i file appena scaricati ai file personalizzati già presenti nella cartella.
   1. Sostituisci il [!DNL Server\Software] cartella da aggiornare [!DNL Insight.exe] e [!DNL ReportServer.exe]
   1. Aggiorna [!DNL Server\Scripts] cartella da aggiornare [!DNL TnTSend.exe].

1. Se utilizzi **[!UICONTROL DeviceAtlas]**, quindi dovrai [aggiorna il bundle](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md) situato nella [!DNL Server\Lookups] cartella.

1. Configura le [!DNL Profile.cfg] per garantire che il vettore venga aggiornato in modo da riflettere il numero di elementi per ciascun profilo.

   Ad esempio, per abilitare il **[!UICONTROL Predictive Analytics]** profilo dovrai aggiornare questa impostazione.

   ```
   Directories = vector: 5 items
       0 = string: Base\\
       1 = string: Geography\\
       2 = string: Predictive Analytics\\
       3 = string: Adobe SC\\
       4 = string: Profile Name\\
   ```

1. Configura e salva il file PAServer.cfg per la funzione Predictive Analytics .

   Se desideri inviare i processi di Predictive Analytics ai server, dovrai configurare la [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] file per gestire gli invii di clustering lato server.

   Il profilo personalizzato deve ereditare le impostazioni dal profilo di configurazione di Predictive Analytics, consentendoti di configurare e salvare il [!DNL PAServer.cfg] in base all’implementazione del sito.

1. Definisci la **[!UICONTROL Log Source ID]**.

   La **[!UICONTROL Recording of Rows per Log Source]** è stato aggiunto in **[!UICONTROL v6.04]** e definiti nel profilo personalizzato [!DNL Log Processing.cfg] aggiungendo un nome univoco **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Se non hai definito l’ID di origine del registro, riceverai il seguente errore:

   ```
   Missing Log Source ID in log processing.cfg.
   Log Source ID must be defined for all log sources.
   ```

1. Perché [!DNL EventMessages.dll] è stato aggiornato, è necessario annullare la registrazione e quindi registrare il **[!UICONTROL Adobe Insight Server]** nel cluster.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Avvia la **[!UICONTROL Adobe Insight Server]** servizio nel cluster.

Installazione del server completata.

## Aggiornamento del server di rapporto {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Prima dell’aggiornamento a **[!UICONTROL Report Server v6.1]**, devi prima effettuare l’aggiornamento a **[!UICONTROL Server v6.1]**.

1. Utilizzo della **[!UICONTROL Software and Docs]** profilo, download **[!UICONTROL v6.1]** dal **[!UICONTROL Report Server]** creare un pacchetto in una cartella locale.

1. Copia **[!UICONTROL Report Server 6.1]** dal pacchetto scaricato e sostituisci i pacchetti di profilo.

   >[!NOTE]
   >
   >La [!DNL Insight.zbin] nel [!DNL install] La cartella è un file di backup utilizzato per la localizzazione e deve essere presente nel [!DNL install] directory. Questo file o altro [!DNL .zbin] I file verranno utilizzati a seconda delle impostazioni della riga di comando passate all&#39;avvio.

1. (facoltativo) Data Workbench supporta attualmente le lingue inglese (-en-us) e cinese (-zh-cn). È necessario impostare un font per supportare i caratteri a byte singolo e doppio:

   ```
   Report Server.cfg - Add Fonts
      Fonts = vector: 2 items
      0 = string: SimSun
      1 = string: Arial
   ```

   Nel sistema operativo Windows devono essere installati anche i font elencati.

1. Configura [!DNL Report Server v6.1] per la localizzazione.

   1. Interrompi **[!UICONTROL Adobe Insight Report Server]** servizio.
   1. Avviare un prompt dei comandi come &quot;Amministratore&quot;.
   1. Passa al server di rapporto [!DNL install] cartella.
   1. Elimina il servizio Report Server utilizzando il seguente comando:

      ```
      ReportServer.exe /unregserver
      ```

   1. Avvia il servizio in base alle impostazioni della lingua:

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Per verificare che il server di rapporto sia in esecuzione con le impostazioni corrette, apri **[!UICONTROL Windows Service Manager]** e fai clic con il pulsante destro del mouse **[!UICONTROL Adobe Insight Report Server - Properties]**. Il percorso dell&#39;eseguibile visualizza le impostazioni aggiornate della riga di comando.

Installazione del server di report completata.

## Aggiornamento client {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Prima dell’aggiornamento a **[!UICONTROL Client v6.1]**, l&#39;amministratore deve prima eseguire l&#39;aggiornamento a **[!UICONTROL Insight Server v6.1.]**

1. Launch [!DNL Insight.exe] ma non connetterti ad alcun profilo.
1. Modifica le [!DNL Insight.cfg] file.

   ```
   Update Software = bool: true
   ```

1. Collegati al tuo profilo.

   Consenti la sincronizzazione del client con il server e il client verrà aggiornato con i profili client v6.1, i file eseguibili e i file di configurazione più recenti.

   >[!NOTE]
   >
   >La [!DNL Insight.zbin] nel [!DNL install] La cartella è un file di backup utilizzato per la localizzazione e deve essere presente. Questo file o altro [!DNL .zbin] I file verranno utilizzati a seconda delle impostazioni della riga di comando passate all&#39;avvio.

   Vedi [impostazione di lingue localizzate](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) per aggiungere un [!DNL insight.zbin] file necessario per le impostazioni localizzate.

**Impostazioni client aggiuntive**

Prima di configurare [!DNL Insight.exe] e i file di supporto, è necessario uscire dall&#39;applicazione client.

Per installare il cinese semplificato:

1. Crea una scelta rapida che passa l&#39;impostazione della riga di comando al [!DNL Insight.exe] file.

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

1. Avvia la scelta rapida creata per sincronizzare i profili e l’aggiornamento . [!DNL zbin] file.

Per utilizzare l&#39;IME (Input Method Editor).

IME consente di inserire caratteri internazionali.

1. Aggiorna [!DNL Insight.cfg] file con le seguenti impostazioni:

   ```
   Localized IME = bool: true
   ```

1. Avvia la scelta rapida creata per sincronizzare i profili e il [!DNL .zbin] file.

Installazione client completata.
