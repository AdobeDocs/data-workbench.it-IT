---
description: Informazioni sul monitoraggio dello spazio dei dati dell'evento e sulla modifica della directory di registro per i dati Sensor.
solution: Analytics
title: Monitoraggio dello spazio dei dati degli eventi
uuid: e514e8fb-e735-4003-ab21-17470c73af37
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---


# Monitoraggio dello spazio dei dati degli eventi{#monitoring-event-data-space}

Informazioni sul monitoraggio dello spazio dei dati dell&#39;evento e sulla modifica della directory di registro per i dati Sensor.

**Frequenza consigliata:** Ogni 5-10 minuti

[!DNL Insight Server] memorizza un file di registro al [!DNL Sensor] giorno sull&#39;unità di elaborazione dati o sull&#39;unità del file server, a seconda della configurazione. Le dimensioni dei file di registro e la quantità di spazio di archiviazione dati necessaria dipendono da molte variabili, tra cui, ad esempio, il numero di siti Web registrati e il numero di richieste ricevute al secondo dai server Web.

Un&#39;installazione tipica di [!DNL Insight Server] (o un [!DNL Insight Server] cluster) è in grado di memorizzare più terabyte di dati, partendo dal presupposto che l&#39;implementazione utilizzi l&#39;hardware consigliato da  Adobe per i [!DNL Insight Server] computer.

In genere, tutti i dati del registro restano presenti nel [!DNL Insight Server] computer. Se diventa necessario rendere disponibile più spazio di archiviazione dati sul computer, è possibile spostare tutti i file di registro tranne il giorno più recente su un altro computer o supporto di memorizzazione dati (unità zip, nastro e così via). Lo spostamento dei dati non richiede l&#39;arresto [!DNL Insight Server]e non influisce sulle funzionalità disponibili in qualsiasi [!DNL Insights] connessione [!DNL Insight Server] e utilizzo di dati continui. Se non elabora o rielabora un set di dati di analisi, puoi continuare ad accedere a tutti i dati precedenti e i nuovi dati restano disponibili in [!DNL Insight]. Se si elabora o rielabora un dataset di analisi, non è possibile accedere ai dati fino al completamento dell&#39;elaborazione.

Per impostazione predefinita, i dati evento prodotti da [!DNL Sensor] e trasmessi a [!DNL Insight Server] vengono memorizzati nella [!DNL Logs] cartella all&#39;interno della directory di [!DNL Insight Server] installazione. Il file di configurazione Communications [!DNL Communications.cfg]specifica il percorso dei file di registro dei dati dell&#39;evento letti da [!DNL Insight Server].

**Per modificare la directory di registro per[!DNL Sensor]i dati**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.
1. Fare clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] file da configurare e fare clic su **[!UICONTROL Server Files]**.
1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL Communications.cfg] file si trova all&#39;interno di questa directory.
1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server per [!DNL Communications.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Communications.cfg].
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Nella [!DNL Communications.cfg] finestra, fate clic **[!UICONTROL component]** per visualizzarne il contenuto.
1. Nella [!DNL Communications.cfg] finestra, fate clic **[!UICONTROL Servers]** per visualizzarne il contenuto. Possono essere visualizzati diversi tipi di server: File server, server di registrazione, server Init, server di stato, server Send o server Replicate.
1. Individuare il server di registrazione, dove [!DNL Sensor] scrive i file di registro da elaborare, [!DNL Insight Server]quindi fare clic sul numero corrispondente per visualizzare il menu.

   ![Informazioni sul passaggio](assets/cfg_communications_examplevalues_logging.png)

   La directory di registro predefinita è la [!DNL Logs] cartella all’interno della directory di [!DNL Insight Server] installazione.

1. Modificate il parametro Directory di registro per riflettere la posizione desiderata dei file di registro.

   >[!NOTE]
   >
   >Non modificate altri parametri per LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Diversi FileServer possono essere elencati sotto il nodo Server, quindi potrebbe essere necessario visualizzare il contenuto di molti di essi (facendo clic sui relativi numeri nell&#39; [!DNL Servers] elenco) per trovare il server con un Percorso locale dei registri\ da modificare.

1. Modificate il Percorso locale per riflettere la posizione desiderata dei [!DNL .vsl] file.

   >[!NOTE]
   >
   >Non modificare altri parametri per FileServer.

   Anche se il percorso dei file di registro è stato modificato nel [!DNL Communications.cfg] file, è possibile mappare questi file alla directory Logs del file [!DNL Server Files Manager] specificando /Logs/ come URI per il fileServer.

1. Salvate le modifiche al server effettuando le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. Fare [!DNL Server Files Manager]clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL Temp] colonna e selezionare **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

