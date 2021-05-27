---
description: Informazioni sul monitoraggio dello spazio dei dati dell'evento e sulla modifica della directory di registro per i dati del sensore.
title: Monitoraggio dello spazio dei dati degli eventi
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# Monitoraggio dello spazio dei dati degli eventi{#monitoring-event-data-space}

Informazioni sul monitoraggio dello spazio dei dati dell&#39;evento e sulla modifica della directory di registro per i dati del sensore.

**Frequenza consigliata:** ogni 5-10 minuti

[!DNL Insight Server] memorizza un file di registro al  [!DNL Sensor] giorno sull&#39;unità di elaborazione dati o sull&#39;unità del file server, a seconda della configurazione. Le dimensioni dei file di registro e la quantità di spazio di archiviazione dei dati necessaria dipendono da molte variabili, tra cui, ad esempio, il numero di siti web registrati e il numero di richieste ricevute dai server web al secondo.

Un&#39;installazione tipica di [!DNL Insight Server] (o un cluster [!DNL Insight Server]) è in grado di memorizzare più terabyte di dati, partendo dal presupposto che l&#39;implementazione utilizzi l&#39;hardware consigliato dall&#39;Adobe per i computer [!DNL Insight Server].

In genere, tutti i dati di registro rimangono presenti sul computer [!DNL Insight Server]. Se si rende necessario rendere disponibile più spazio di archiviazione dei dati sul computer, è possibile spostare tutti i file di log del giorno, tranne il giorno più corrente, in un altro computer o supporto di archiviazione dei dati (unità zip, nastro e così via). Lo spostamento dei dati non richiede l’arresto di [!DNL Insight Server] e non influisce sulle funzionalità disponibili in qualsiasi [!DNL Insights] che può essere connesso a [!DNL Insight Server] e sull’utilizzo di dati continui. Se non elabora o rielabora un set di dati di analisi, mantieni l’accesso a tutti i dati precedenti e i nuovi dati continua a essere disponibile in [!DNL Insight]. Se elabora o rielabora un set di dati di analisi, non puoi accedere ai dati fino al completamento dell’elaborazione.

Per impostazione predefinita, i dati evento prodotti da [!DNL Sensor] e trasmessi a [!DNL Insight Server] vengono memorizzati nella cartella [!DNL Logs] all&#39;interno della directory di installazione [!DNL Insight Server]. Il file di configurazione delle comunicazioni [!DNL Communications.cfg] specifica la posizione dei file di registro dei dati dell&#39;evento letti da [!DNL Insight Server].

**Per modificare la directory di registro dei  [!DNL Sensor] dati**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.
1. Fai clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] da configurare e fai clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. Il file [!DNL Communications.cfg] si trova all&#39;interno di questa directory.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* per [!DNL Communications.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella colonna [!DNL Temp] per [!DNL Communications.cfg].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Nella finestra [!DNL Communications.cfg] fare clic su **[!UICONTROL component]** per visualizzarne il contenuto.
1. Nella finestra [!DNL Communications.cfg] fare clic su **[!UICONTROL Servers]** per visualizzarne il contenuto. Possono essere visualizzati diversi tipi di server: File server, server di registrazione, Init Server, server di stato, server di invio o server di replica.
1. Trova il LoggingServer, dove [!DNL Sensor] scrive i file di registro da elaborare da [!DNL Insight Server], quindi fai clic sul numero corrispondente per visualizzare il menu.

   ![Informazioni sul passaggio](assets/cfg_communications_examplevalues_logging.png)

   La directory di registro predefinita è la cartella [!DNL Logs] all&#39;interno della directory di installazione [!DNL Insight Server].

1. Modificare il parametro della directory di registro per riflettere la posizione desiderata dei file di registro.

   >[!NOTE]
   >
   >Non modificare altri parametri di LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Diversi FileServer possono essere elencati sotto il nodo Server, quindi potrebbe essere necessario visualizzare il contenuto di molti di essi (facendo clic sui loro numeri nell&#39;elenco [!DNL Servers]) per trovare il server con un Percorso locale dei Log\ da modificare.

1. Modifica il Percorso locale per riflettere la posizione desiderata dei file [!DNL .vsl].

   >[!NOTE]
   >
   >Non modificare altri parametri per FileServer.

   Sebbene la posizione dei file di registro sia stata modificata nel file [!DNL Communications.cfg], è possibile mappare questi file nella directory Logs del [!DNL Server Files Manager] specificando /Logs/ come URI per il FileServer.

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
