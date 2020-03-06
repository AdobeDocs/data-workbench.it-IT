---
description: È necessario monitorare regolarmente i file del registro eventi per tenere traccia dei messaggi evento del sistema Insight Server, registrati nei file <YYYYMMDD>-event.txt, per impostazione predefinita, che si trovano nella cartella Eventi all'interno della directory di installazione di Insight Server.
solution: Insight
title: Monitoraggio degli eventi amministrativi
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Monitoraggio degli eventi amministrativi{#monitoring-administrative-events}

È necessario monitorare regolarmente i file del registro eventi per tenere traccia dei messaggi evento del sistema Insight Server registrati nei `<YYYYMMDD>-event.txt` file che per impostazione predefinita si trovano nella cartella Eventi all&#39;interno della directory di installazione di Insight Server.

**Frequenza consigliata:** Ogni 5-10 minuti

Potete monitorare questi eventi utilizzando [!DNL Server Files Manager] in, lo strumento di gestione automatizzata, i [!DNL Insight][!DNL *-event.txt] file o il visualizzatore eventi di Windows.

>[!NOTE]
>
>I registri eventi amministrativi sono completamente separati dal registro eventi di Windows, ma contengono alcuni degli stessi eventi. I registri degli eventi amministrativi contengono solo informazioni sugli [!DNL Insight Server] eventi.

**Per visualizzare i file events.txt tramite il pulsante[!DNL Server Files Manager]**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.
1. Fare clic con il pulsante destro del mouse sull&#39;icona di un elemento attivo [!DNL Insight Server] e fare clic **[!UICONTROL Server Files]**.
1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Events]** per visualizzarne il contenuto.
1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server accanto al file desiderato, quindi fare clic **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato accanto al nome del file nella [!DNL Temp] colonna.
1. Fare clic con il pulsante destro del mouse sul segno di spunta nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il file dell&#39;evento viene visualizzato in una nuova finestra Blocco note di Microsoft Windows.

   ![Informazioni sul passaggio](assets/vis_FileManager_eventfile.png)

   Il [!DNL Server.log] file nella [!DNL Trace] cartella all&#39;interno della directory di [!DNL Insight Server] installazione contiene informazioni di registrazione più dettagliate.

**Per visualizzare gli eventi mediante il visualizzatore eventi di Windows**

* Fai clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Per modificare la directory del registro eventi amministrativi**

Il file di configurazione Registri eventi amministrativi [!DNL Administrative Events Log.cfg]specifica la directory in cui viene eseguito il login all’evento.

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] file da configurare e fare clic su **[!UICONTROL Server Files]**.

1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL Administrative Event Logs.cfg] file si trova all&#39;interno di questa directory.

1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server per [!DNL Administrative Event Logs.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Administrative Event Logs.cfg].

1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Nella [!DNL Administrative Event Logs.cfg] finestra, fate clic **[!UICONTROL component]** per visualizzarne il contenuto. Il percorso predefinito è la [!DNL Events] cartella all’interno della directory di [!DNL Insight Server] installazione.

   ![](assets/cfg_adminevents_examplevalues.png)

1. Nel parametro Path digitare il nome della directory in cui si desidera inviare i dati di registrazione degli eventi.
1. Salvate le modifiche al server effettuando le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.
   1. Nella [!DNL Server Files Manager]colonna fare clic con il pulsante destro del mouse sul segno di spunta del file, quindi selezionare [!DNL Temp] > **[!UICONTROL Save to]** **[!UICONTROL server name]**.

