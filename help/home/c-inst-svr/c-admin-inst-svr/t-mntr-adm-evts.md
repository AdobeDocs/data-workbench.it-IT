---
description: È necessario monitorare regolarmente i file di registro eventi per tenere traccia dei messaggi evento di sistema di Insight Server registrati nella <yyyymmdd>I file -event.txt si trovano per impostazione predefinita nella cartella Eventi all'interno della directory di installazione di Insight Server.
title: Monitoraggio degli eventi amministrativi (Insight Server)
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 1%

---

# Monitoraggio degli eventi amministrativi{#monitoring-administrative-events}

{{eol}}

È necessario monitorare regolarmente i file di registro eventi per tenere traccia dei messaggi evento di sistema di Insight Server registrati nella `<YYYYMMDD>-event.txt` i file che si trovano per impostazione predefinita nella cartella Eventi all&#39;interno della directory di installazione di Insight Server.

**Frequenza consigliata:** Ogni 5-10 minuti

Puoi monitorare questi eventi utilizzando [!DNL Server Files Manager] in [!DNL Insight], lo strumento di gestione automatizzata, [!DNL *-event.txt] o il Visualizzatore eventi di Windows.

>[!NOTE]
>
>I registri eventi amministrativi sono completamente separati dal registro eventi di Windows, ma contengono alcuni degli stessi eventi. I registri degli eventi amministrativi contengono solo informazioni su [!DNL Insight Server] eventi.

**Per visualizzare i file events.txt tramite il comando[!DNL Server Files Manager]**

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.
1. Fai clic con il pulsante destro del mouse sull’icona di un attivo [!DNL Insight Server] e fai clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Events]** per visualizzarne il contenuto.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nel *nome server* accanto al file desiderato e fai clic su **[!UICONTROL Make Local]**. Accanto al nome del file nel [!DNL Temp] colonna.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nel [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il file dell&#39;evento viene visualizzato in una nuova finestra del Blocco note di Microsoft Windows.

   ![Informazioni sul passaggio](assets/vis_FileManager_eventfile.png)

   La [!DNL Server.log] nel [!DNL Trace] nella cartella [!DNL Insight Server] la directory di installazione contiene informazioni di registrazione più dettagliate.

**Per visualizzare gli eventi tramite il Visualizzatore eventi di Windows**

* Fai clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Per modificare la directory Registro eventi amministrativi**

Il file di configurazione Registri eventi amministrativi, [!DNL Administrative Events Log.cfg], specifica la directory in cui viene eseguita la registrazione degli eventi.

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.

1. Fai clic con il pulsante destro del mouse sull’icona [!DNL Insight Server] si desidera configurare e fare clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. La [!DNL Administrative Event Logs.cfg] il file si trova all&#39;interno di questa directory.

1. Fai clic con il pulsante destro del mouse sul segno di spunta nel *nome server* colonna per [!DNL Administrative Event Logs.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nel [!DNL Temp] colonna per [!DNL Administrative Event Logs.cfg].

1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nel [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. In [!DNL Administrative Event Logs.cfg] finestra, fai clic su **[!UICONTROL component]** per visualizzarne il contenuto. Il percorso predefinito è il [!DNL Events] nella cartella [!DNL Insight Server] directory di installazione.

   ![](assets/cfg_adminevents_examplevalues.png)

1. Nel parametro Path digitare il nome della directory in cui si desidera generare i dati di registrazione degli eventi.
1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL Temp] e seleziona **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
