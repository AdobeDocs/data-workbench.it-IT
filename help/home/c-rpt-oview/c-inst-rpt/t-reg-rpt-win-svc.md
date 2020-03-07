---
description: Passaggi per registrare ed eseguire il server di report.
solution: Analytics
title: Registrazione del server di report come servizio Windows
topic: Data workbench
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Registrazione del server di report come servizio Windows{#registering-report-server-as-a-windows-service}

Passaggi per registrare ed eseguire il server di report.

Prima di eseguire questa procedura, identificare l&#39;account di Windows in cui verrà eseguito il [!DNL Report Server] servizio. Accertatevi che questo account disponga delle autorizzazioni adeguate per accedere al percorso in cui sono memorizzati i rapporti generati (ovvero, non utilizzate i rapporti [!DNL Local System Account]).

Utilizzare la procedura seguente per iniziare [!DNL Report Server]. Quando si avvia [!DNL Report Server] per la prima volta, si registra automaticamente come servizio Windows.

Quando si avvia [!DNL Report Server] per la prima volta, si connette automaticamente al server delle licenze Adobe per registrare il certificato digitale. Per completare correttamente il processo di registrazione, è necessario che il computer sia connesso a Internet quando si eseguono i seguenti passaggi.

1. In Windows, andate alla directory in cui avete installato [!DNL Report Server].

   Esempio: D:\Adobe\Report

1. Double-click **[!UICONTROL ReportServer.exe]**.
1. Per confermare che [!DNL Report Server] l&#39;esecuzione è corretta, fate clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Questa sequenza di comandi può variare a seconda della versione di Windows in uso.
1. Nell&#39;elenco dei servizi, individuare la voce [!DNL Report Server] e confermare che il relativo stato è Avviato e che il tipo di avvio è Automatico.
1. Effettuate le seguenti operazioni per specificare l&#39;account utente in base al quale [!DNL Report Server] verrà eseguito:

   1. Fate doppio clic **[!UICONTROL Report Server]** per aprire la [!DNL Properties] finestra.

   1. Selezionate la **[!UICONTROL Log On]** scheda.
   1. Selezionare il **[!UICONTROL This account]** pulsante di scelta.
   1. Digitate o cercate il nome account. Questo account deve disporre dell&#39;autorizzazione per accedere al percorso in cui vengono memorizzati i rapporti generati.

      >[!NOTE]
      >
      >Se [!DNL Report Server] distribuisce i rapporti come file di Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx]), accertatevi che l&#39;account disponga anche dell&#39;autorizzazione per eseguire Microsoft Excel.

   1. Immettete e confermate la password dell&#39;account.
   1. Fai clic su **[!UICONTROL OK]** (Fine).

1. Fare clic con il pulsante destro del mouse sul [!DNL Report Server] servizio e selezionare **[!UICONTROL Restart]** per riavviare il servizio nell&#39;account specificato.
1. Per verificare se [!DNL Report Server] si sono verificati errori durante l&#39;avvio, fate clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

   1. Nel riquadro a sinistra della [!DNL Event Viewer] finestra, selezionare il registro Applicazioni.
   1. Nel riquadro a destra, cercate gli eventi con Adobe nella [!DNL Source] colonna.
   1. Se si verifica un errore da Adobe, fare doppio clic sull&#39;errore per visualizzare la [!DNL Event Properties] finestra. Questa finestra fornisce informazioni dettagliate sull&#39;errore.

      >[!NOTE]
      >
      >Dopo l&#39;avvio del [!DNL Report Server] servizio, il file [!DNL ReportServer.log] viene creato nella directory del server di report [!DNL Trace] . Questo file è utile anche per la risoluzione di problemi con [!DNL Report Server].

L&#39;installazione di [!DNL Report Server]. [!DNL Report Server] è progettato per essere eseguito in modo continuo. Se si riavvia il computer, [!DNL Report Server] si riavvia automaticamente. Se è necessario avviare e arrestare [!DNL Report Server] manualmente, è possibile utilizzare il pannello di [!DNL Services] controllo in Windows.
