---
description: Per eseguire l’aggiornamento a Data Workbench v6.1 dall’installazione di Insight v5.5x, effettua le seguenti operazioni.
title: Aggiornamento a Data Workbench da 5.5 a 6.1
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
exl-id: c730f6d5-2171-4d97-a967-509dc2517c86,3f25917b-b929-4e3b-84f0-1a81b30ba641
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 1%

---

# Aggiornamento a Data Workbench da 5.5 a 6.1{#data-workbench-to-upgrade}

{{eol}}

Per eseguire l’aggiornamento a Data Workbench v6.1 dall’installazione di Insight v5.5x, effettua le seguenti operazioni.

**Passaggio 1**: [Aggiornamento server](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**Passaggio 2**: [Aggiornamento del server di rapporto](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Passaggio 3**: [Aggiornamento client](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>I componenti server, server di report e client vengono aggiornati per l&#39;esecuzione su sistemi operativi Windows a 64 bit.

## Aggiornamento server {#section-08bd6fe3da8740fcb19688e8cac6f223}

Segui questi passaggi per aggiornare **[!UICONTROL Server v6.1]** componenti:

1. Utilizzo della **[!UICONTROL Software and Docs]** profilo, apri **[!UICONTROL Start Here]** e scarica tutti i pacchetti server necessari in una cartella locale.

   * Scarica **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip cartelle ed estrai tutti i file.

      La **[!UICONTROL Server]** include **[!UICONTROL Lookup]** e **[!UICONTROL Profile]** cartelle con **[!UICONTROL Base]** e **[!UICONTROL Transform]** file di ricerca da aggiungere e sostituire per aggiornare il server.

   * Scarica nuovo **[!UICONTROL Profiles]** cartelle.
   * Scarica aggiornato **[!UICONTROL Lookup]** cartelle.
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
1. Imposta [!DNL Directories] in [!DNL Profile.cfg] per garantire che il vettore venga aggiornato in modo da riflettere il numero di elementi per ciascun profilo.

   Ad esempio, per abilitare il **[!UICONTROL Predictive Analytics]** profilo dovrai aggiornare questa impostazione.

   ```
   Directories = vector: 5 items
       0 = string: Base\\
       1 = string: Geography\\
       2 = string: Predictive Analytics\\
       3 = string: Adobe SC\\
       4 = string: Profile Name\\
   ```

1. Configura e salva il [!DNL PAServer.cfg] per aggiornare la funzione Predictive Analytics.

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

1. (facoltativo) Modifica il file di configurazione del server di report per supportare i caratteri a doppio byte.

   Data Workbench supporta attualmente le lingue inglese (-en-us) e cinese (-zh-cn). È necessario impostare un font per supportare i caratteri a byte singolo e doppio:

   ```
   Report Server.cfg - Add Fonts
      Fonts = vector: 2 items
      0 = string: SimSun
      1 = string: Arial
   ```

   Nel sistema operativo Windows devono essere installati anche i font elencati.

1. Configura [!DNL Report Server v6.1].

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
>Prima dell’aggiornamento a **[!UICONTROL Client v6.1]**, l&#39;amministratore deve prima eseguire l&#39;aggiornamento a **[!UICONTROL Server v6.1.]**

1. Launch [!DNL Insight.exe] ma NON connetterti ad alcun profilo.
1. Modifica le [!DNL Insight.cfg] file per non aggiornare automaticamente il software.

   ```
   Update Software = bool: false
   ```

1. Connetti a **[!UICONTROL Software and Docs]** profilo (softdocs).
1. Scarica [!DNL Software\Insight Client\v6.10].
1. (facoltativo) Modifica [!DNL insight.cfg] per supportare i caratteri a doppio byte.

   Data Workbench supporta attualmente sia l’inglese che il cinese semplificato. Selezionare i font per supportare entrambe le lingue:

   ```
   Fonts = vector: 2 items
   0 = string: SimSun
   1 = string: Arial
   ```

1. Esci dal client.
1. Copia i file nel download **v6.1** pacchetto client al [!DNL Install] cartella.

   >[!NOTE]
   >
   >La [!DNL Insight.zbin] il file nella cartella di installazione è un file di backup utilizzato per la localizzazione e deve essere presente nella directory di installazione. Questo file o altro [!DNL .zbin] I file verranno utilizzati a seconda delle impostazioni della riga di comando passate all&#39;avvio.
   >
   >Ad esempio, per avviare il cinese semplificato, crea una scelta rapida che passa nell’impostazione della riga di comando.
   >
   >
   ```
   >Insight.exe -zh-cn
   >```
   >
   >Se si desidera avviare in inglese (impostazione predefinita), non è necessaria alcuna modifica della riga di comando.

1. Launch [!DNL Insight.exe] per l&#39;inglese o la scelta rapida creata per un&#39;altra lingua.
1. Connettiti al tuo profilo e consenti al client di sincronizzarsi con il server.
1. (facoltativo) Per utilizzare l&#39;IME, apporta le seguenti modifiche al [!DNL Insight.cfg] file:

   ```
   Localized IME = bool: true
   ```

   L&#39;IME (Input Method Editor) consente di immettere caratteri internazionali.

1. (facoltativo) Modifica il [!DNL Insight.cfg] file per aggiornare automaticamente il software:

   ```
   Update Software = bool: true
   ```

   Vedere le istruzioni per l&#39;implementazione dell&#39;IME.
1. Riavvia dopo la sincronizzazione del profilo per utilizzare il più recente [!DNL .zbin] file.

Installazione client completata.
