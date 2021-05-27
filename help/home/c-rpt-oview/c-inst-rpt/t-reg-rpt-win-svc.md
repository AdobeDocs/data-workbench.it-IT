---
description: Passaggi per registrare ed eseguire il server di rapporto.
title: Registrazione del server di rapporto come servizio Windows
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Registrazione del server di rapporto come servizio Windows{#registering-report-server-as-a-windows-service}

Passaggi per registrare ed eseguire il server di rapporto.

Prima di eseguire questa procedura, identificare l&#39;account Windows in cui verrà eseguito il servizio [!DNL Report Server]. Assicurati che questo account disponga delle autorizzazioni appropriate per accedere alla posizione in cui vengono archiviati i report generati (ovvero, non utilizzare [!DNL Local System Account]).

Utilizza la procedura seguente per avviare [!DNL Report Server]. Quando si avvia [!DNL Report Server] per la prima volta, si registra automaticamente come servizio Windows.

Quando si avvia [!DNL Report Server] per la prima volta, si connette automaticamente al server licenze Adobe per registrare il certificato digitale. Per completare correttamente il processo di registrazione, è necessario che il computer sia connesso a Internet quando si eseguono i seguenti passaggi.

1. In Windows, accedi alla directory in cui hai installato [!DNL Report Server].

   Esempio: D:\Adobe\Report

1. Fare doppio clic su **[!UICONTROL ReportServer.exe]**.
1. Per confermare che [!DNL Report Server] è in esecuzione correttamente, fai clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Questa sequenza di comandi può variare a seconda della versione di Windows in uso.
1. Nell&#39;elenco dei servizi, individuare la voce relativa a [!DNL Report Server] e confermare che il relativo stato è Avviato e che il relativo tipo di avvio è Automatico.
1. Per specificare l&#39;account utente in cui verrà eseguito [!DNL Report Server], procedi come segue:

   1. Fare doppio clic su **[!UICONTROL Report Server]** per aprire la finestra [!DNL Properties].

   1. Seleziona la scheda **[!UICONTROL Log On]** .
   1. Selezionare il pulsante di scelta **[!UICONTROL This account]**.
   1. Digitare o cercare il nome dell&#39;account. Questo account deve disporre dell’autorizzazione per accedere alla posizione in cui vengono memorizzati i rapporti generati.

      >[!NOTE]
      >
      >Se [!DNL Report Server] distribuisce i rapporti come file di Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx]), assicurati che l&#39;account disponga anche delle autorizzazioni necessarie per eseguire Microsoft Excel.

   1. Immetti e conferma la password dell&#39;account.
   1. Fai clic su **[!UICONTROL OK]**.

1. Fai clic con il pulsante destro del mouse sul servizio [!DNL Report Server] e seleziona **[!UICONTROL Restart]** per riavviare il servizio nell&#39;account specificato.
1. Per verificare se [!DNL Report Server] ha riscontrato errori durante l&#39;avvio, fai clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

   1. Nel riquadro a sinistra della finestra [!DNL Event Viewer], selezionare il registro Applicazioni.
   1. Nel riquadro a destra, cerca gli eventi con Adobe nella colonna [!DNL Source] .
   1. Se trovi un errore dall&#39;Adobe, fai doppio clic sull&#39;errore per visualizzare la finestra [!DNL Event Properties]. Questa finestra fornisce informazioni dettagliate sull’errore.

      >[!NOTE]
      >
      >Dopo l&#39;avvio del servizio [!DNL Report Server], il file [!DNL ReportServer.log] viene creato nella directory del server di rapporto [!DNL Trace]. Questo file è utile anche per la risoluzione dei problemi relativi a [!DNL Report Server].

Installazione di [!DNL Report Server] completata. [!DNL Report Server] è progettato per funzionare continuamente. Se si riavvia il computer, [!DNL Report Server] si riavvia automaticamente. Se è necessario avviare e arrestare manualmente [!DNL Report Server], è possibile farlo utilizzando il pannello di controllo [!DNL Services] in Windows.
