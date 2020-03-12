---
description: Segui questi passaggi per eseguire l'aggiornamento al workbench dati v6.1 dall'installazione di Insight v5.5x.
solution: Analytics
title: Aggiornamento a Workbench dati da 5.5 a 6.1
topic: Data workbench
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Aggiornamento a Workbench dati da 5.5 a 6.1{#data-workbench-to-upgrade}

Segui questi passaggi per eseguire l&#39;aggiornamento al workbench dati v6.1 dall&#39;installazione di Insight v5.5x.

**Passaggio 1**: Aggiornamento [server](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**Passaggio 2**: Aggiornamento server [report](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Passaggio 3**: Aggiornamento [client](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>I componenti server, server di report e client vengono aggiornati per essere eseguiti sui sistemi operativi Windows a 64 bit.

## Aggiornamento server {#section-08bd6fe3da8740fcb19688e8cac6f223}

Per aggiornare i **[!UICONTROL Server v6.1]** componenti, effettuate le seguenti operazioni:

1. Utilizzando il **[!UICONTROL Software and Docs]** profilo, aprite l’ **[!UICONTROL Start Here]** area di lavoro e scaricate tutti i pacchetti server necessari in una cartella locale.

   * Scaricate **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** le cartelle zip ed estraete tutti i file.

      Il **[!UICONTROL Server]** pacchetto include **[!UICONTROL Lookup]** e **[!UICONTROL Profile]** cartelle con i file **[!UICONTROL Base]** e **[!UICONTROL Transform]** di ricerca da aggiungere e sostituire per aggiornare il server.

   * Scaricate nuove **[!UICONTROL Profiles]** cartelle.
   * Scaricate **[!UICONTROL Lookup]** le cartelle aggiornate.
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
1. Impostato [!DNL Directories] nel [!DNL Profile.cfg] file in modo che il vettore venga aggiornato per riflettere il numero di elementi per ciascun profilo.

   Ad esempio, per abilitare il **[!UICONTROL Predictive Analytics]** profilo sarà necessario aggiornare questa impostazione.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configurate e salvate il [!DNL PAServer.cfg] file per aggiornare la funzione Predictive Analytics.

   Se desiderate inviare i processi Predictive Analytics ai server, dovrete configurare il [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] file per gestire gli invii del clustering lato server.

   Il profilo personalizzato deve ereditare le impostazioni dal profilo di configurazione Predictive Analytics, consentendo di configurare e salvare le impostazioni [!DNL PAServer.cfg] in base all&#39;implementazione del sito.

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

1. (Facoltativo) Modificate il file di configurazione del server di report per supportare i caratteri a doppio byte.

   Workbench dati supporta attualmente inglese (-en-us) e cinese (-zh-cn). È necessario impostare un font per supportare i caratteri a byte singolo e doppio:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   Nel sistema operativo Windows devono essere installati anche i font elencati.

1. Configura [!DNL Report Server v6.1].

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
>Prima di eseguire l&#39;aggiornamento a **[!UICONTROL Client v6.1]**, l&#39;amministratore deve prima effettuare l&#39;aggiornamento a **[!UICONTROL Server v6.1.]**

1. Avviate [!DNL Insight.exe] ma NON connettetevi ad alcun profilo.
1. Modificate il [!DNL Insight.cfg] file per non aggiornare automaticamente il software.

   ```
   Update Software = bool: false
   ```

1. Connettersi al **[!UICONTROL Software and Docs]** profilo (softdocs).
1. Scarica [!DNL Software\Insight Client\v6.10].
1. (Facoltativo) Modificare [!DNL insight.cfg] per supportare i caratteri a doppio byte.

   Data Workbench supporta attualmente sia l&#39;inglese che il cinese semplificato. Selezionate i font per supportare entrambe le lingue:

   ```
   Fonts = vector: 2 items  
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Uscire dal client.
1. Copiate i file nel pacchetto client **v6.1** scaricato nella [!DNL Install] cartella.

   >[!NOTE]
   >
   >Il [!DNL Insight.zbin] file nella cartella di installazione è un file di backup utilizzato per la localizzazione e deve essere presente nella directory di installazione. Questo file o altri [!DNL .zbin] file verranno utilizzati a seconda delle impostazioni della riga di comando passate all&#39;avvio.
   >
   >Ad esempio, per avviare il cinese semplificato, creare una scelta rapida che passi all&#39;impostazione della riga di comando.
   >
   >```
   >Insight.exe -zh-cn
   >```
   >
   >Se si desidera eseguire l&#39;avvio in inglese (impostazione predefinita), non è necessaria alcuna modifica della riga di comando.

1. Avviate [!DNL Insight.exe] l&#39;inglese o la scelta rapida creata per un&#39;altra lingua.
1. Connettiti al tuo profilo e consenti al client di effettuare la sincronizzazione con il server.
1. (Facoltativo) Per utilizzare l&#39;IME, apportare le seguenti modifiche al [!DNL Insight.cfg] file:

   ```
   Localized IME = bool: true
   ```

   L&#39;IME (Input Method Editor) consente di inserire caratteri internazionali.

1. (facoltativo) Modificate il [!DNL Insight.cfg] file per aggiornare automaticamente il software:

   ```
   Update Software = bool: true
   ```

   Vedere le istruzioni per l&#39;implementazione dell&#39;IME.
1. Riavviate nuovamente dopo la sincronizzazione del profilo per utilizzare il [!DNL .zbin] file più recente.

L&#39;installazione client è stata completata.
