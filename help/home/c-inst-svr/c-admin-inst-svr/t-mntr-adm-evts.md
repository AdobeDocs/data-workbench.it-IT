---
description: È necessario monitorare regolarmente i file di registro eventi per tenere traccia dei messaggi evento di sistema di Insight Server, che vengono registrati nei file <YYYMMDD>-event.txt per impostazione predefinita nella cartella Eventi all'interno della directory di installazione di Insight Server.
title: Monitoraggio degli eventi amministrativi
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 2%

---

# Monitoraggio degli eventi amministrativi{#monitoring-administrative-events}

È necessario monitorare regolarmente i file di registro eventi per tenere traccia dei messaggi evento di sistema di Insight Server, registrati nei file `<YYYYMMDD>-event.txt` che si trovano per impostazione predefinita nella cartella Eventi all&#39;interno della directory di installazione di Insight Server.

**Frequenza consigliata:** ogni 5-10 minuti

È possibile monitorare questi eventi utilizzando [!DNL Server Files Manager] in [!DNL Insight], lo strumento di gestione automatizzata, i file [!DNL *-event.txt] o il Visualizzatore eventi di Windows.

>[!NOTE]
>
>I registri eventi amministrativi sono completamente separati dal registro eventi di Windows, ma contengono alcuni degli stessi eventi. I registri degli eventi amministrativi contengono solo informazioni sugli eventi [!DNL Insight Server].

**Per visualizzare i file events.txt tramite il comando[!DNL Server Files Manager]**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.
1. Fai clic con il pulsante destro del mouse sull&#39;icona di un elemento attivo [!DNL Insight Server] e fai clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Events]** per visualizzarne il contenuto.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* accanto al file desiderato e fai clic su **[!UICONTROL Make Local]**. Accanto al nome del file nella colonna [!DNL Temp] viene visualizzato un segno di spunta.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il file dell&#39;evento viene visualizzato in una nuova finestra Blocco note di Microsoft Windows.

   ![Informazioni sul passaggio](assets/vis_FileManager_eventfile.png)

   Il file [!DNL Server.log] nella cartella [!DNL Trace] all&#39;interno della directory di installazione [!DNL Insight Server] contiene informazioni di registrazione più dettagliate.

**Per visualizzare gli eventi tramite il Visualizzatore eventi di Windows**

* Fai clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Per modificare la directory Registro eventi amministrativi**

Il file di configurazione dei registri degli eventi amministrativi, [!DNL Administrative Events Log.cfg], specifica la directory in cui viene eseguita la registrazione degli eventi.

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.

1. Fai clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] da configurare e fai clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. Il file [!DNL Administrative Event Logs.cfg] si trova all&#39;interno di questa directory.

1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* per [!DNL Administrative Event Logs.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella colonna [!DNL Temp] per [!DNL Administrative Event Logs.cfg].

1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Nella finestra [!DNL Administrative Event Logs.cfg] fare clic su **[!UICONTROL component]** per visualizzarne il contenuto. Il percorso predefinito è la cartella [!DNL Events] all&#39;interno della directory di installazione [!DNL Insight Server].

   ![](assets/cfg_adminevents_examplevalues.png)

1. Nel parametro Path digitare il nome della directory in cui si desidera generare i dati di registrazione degli eventi.
1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL Temp] e seleziona **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
