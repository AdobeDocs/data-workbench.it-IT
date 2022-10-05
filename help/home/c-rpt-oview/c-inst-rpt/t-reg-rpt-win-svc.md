---
description: Passaggi per registrare ed eseguire il server di rapporto.
title: Registrazione del server di rapporto come servizio Windows
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Registrazione del server di rapporto come servizio Windows{#registering-report-server-as-a-windows-service}

{{eol}}

Passaggi per registrare ed eseguire il server di rapporto.

Prima di eseguire questa procedura, identificare l&#39;account Windows in cui [!DNL Report Server] verrà eseguito il servizio. Assicurati che questo account disponga delle autorizzazioni appropriate per accedere al percorso in cui vengono archiviati i report generati (ovvero, non utilizzare il [!DNL Local System Account]).

Utilizza la procedura seguente per iniziare [!DNL Report Server]. Quando si inizia [!DNL Report Server] per la prima volta, si registra automaticamente come servizio Windows.

Quando si inizia [!DNL Report Server] per la prima volta, si connette automaticamente al server licenze Adobe per registrare il certificato digitale. Per completare correttamente il processo di registrazione, è necessario che il computer sia connesso a Internet quando si eseguono i seguenti passaggi.

1. In Windows, passare alla directory in cui è stato installato [!DNL Report Server].

   Esempio: D:\Adobe\Report

1. Fare doppio clic **[!UICONTROL ReportServer.exe]**.
1. Confermare che [!DNL Report Server] è in esecuzione correttamente, fai clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Questa sequenza di comandi può variare a seconda della versione di Windows in uso.
1. Nell’elenco dei servizi, individua la voce per [!DNL Report Server] e confermare che il relativo stato è Avviato e che il relativo tipo di avvio è Automatico.
1. Effettua le seguenti operazioni per specificare l’account utente in cui si trova [!DNL Report Server] eseguirà:

   1. Fare doppio clic **[!UICONTROL Report Server]** per aprire [!DNL Properties] finestra.

   1. Seleziona la **[!UICONTROL Log On]** scheda .
   1. Seleziona la **[!UICONTROL This account]** pulsante di scelta.
   1. Digitare o cercare il nome dell&#39;account. Questo account deve disporre dell’autorizzazione per accedere alla posizione in cui vengono memorizzati i rapporti generati.

      >[!NOTE]
      >
      >Se [!DNL Report Server] distribuisce i rapporti come Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx]), assicurati che l&#39;account disponga anche dell&#39;autorizzazione per eseguire Microsoft Excel.

   1. Immetti e conferma la password dell&#39;account.
   1. Fai clic su **[!UICONTROL OK]**.

1. Fai clic con il pulsante destro del mouse sul pulsante [!DNL Report Server] servizio e seleziona **[!UICONTROL Restart]** per riavviare il servizio nell&#39;account specificato.
1. Per verificare se [!DNL Report Server] si sono verificati errori durante l&#39;avvio, fare clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

   1. Nel riquadro a sinistra del [!DNL Event Viewer] selezionare il registro Applicazioni.
   1. Nel riquadro a destra, cerca gli eventi con Adobe nel [!DNL Source] colonna.
   1. Se trovi un errore dall’Adobe, fai doppio clic sull’errore per visualizzare il [!DNL Event Properties] finestra. Questa finestra fornisce informazioni dettagliate sull’errore.

      >[!NOTE]
      >
      >Dopo la [!DNL Report Server] viene avviato il servizio, il file [!DNL ReportServer.log] viene creato nel server di rapporto [!DNL Trace] directory. Questo file è utile anche per la risoluzione dei problemi con [!DNL Report Server].

L&#39;installazione di [!DNL Report Server]. [!DNL Report Server] è progettato per funzionare continuamente. Se si riavvia il computer, [!DNL Report Server] si riavvia automaticamente. Se devi iniziare e fermarti [!DNL Report Server] manualmente, puoi farlo utilizzando il [!DNL Services] pannello di controllo in Windows.
