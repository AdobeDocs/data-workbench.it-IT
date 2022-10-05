---
description: Informazioni sul monitoraggio dello spazio dei dati dell'evento e sulla modifica della directory di registro per i dati del sensore.
title: Monitoraggio dello spazio dei dati degli eventi
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# Monitoraggio dello spazio dei dati degli eventi{#monitoring-event-data-space}

{{eol}}

Informazioni sul monitoraggio dello spazio dei dati dell&#39;evento e sulla modifica della directory di registro per i dati del sensore.

**Frequenza consigliata:** Ogni 5-10 minuti

[!DNL Insight Server] memorizza un file di registro per [!DNL Sensor] al giorno sull&#39;unità di elaborazione dati o sull&#39;unità del file server, a seconda della configurazione. Le dimensioni dei file di registro e la quantità di spazio di archiviazione dei dati necessaria dipendono da molte variabili, tra cui, ad esempio, il numero di siti web registrati e il numero di richieste ricevute dai server web al secondo.

Installazione tipica di [!DNL Insight Server] o [!DNL Insight Server] cluster) è in grado di memorizzare più terabyte di dati, supponendo che l&#39;implementazione utilizzi l&#39;hardware consigliato dall&#39;Adobe per [!DNL Insight Server] macchine.

In genere, tutti i dati di registro rimangono presenti nel [!DNL Insight Server] macchina. Se si rende necessario rendere disponibile più spazio di archiviazione dei dati sul computer, è possibile spostare tutti i file di log del giorno, tranne il giorno più corrente, in un altro computer o supporto di archiviazione dei dati (unità zip, nastro e così via). Lo spostamento dei dati non richiede l’arresto [!DNL Insight Server]e non influisce sulle funzionalità disponibili in alcun [!DNL Insights] che può essere collegato a [!DNL Insight Server] e lavorare con dati continui. Se non elabora o rielabora un set di dati di analisi, mantieni l’accesso a tutti i dati precedenti e ai nuovi dati continua a essere disponibile in [!DNL Insight]. Se elabora o rielabora un set di dati di analisi, non puoi accedere ai dati fino al completamento dell’elaborazione.

Per impostazione predefinita, i dati evento generati da [!DNL Sensor] e trasmessi a [!DNL Insight Server] è memorizzato in [!DNL Logs] nella cartella [!DNL Insight Server] directory di installazione. Il file di configurazione delle comunicazioni, [!DNL Communications.cfg], specifica la posizione dei file di log dei dati dell&#39;evento letti da [!DNL Insight Server].

**Per modificare la directory di registro per [!DNL Sensor] dati**

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.
1. Fai clic con il pulsante destro del mouse sull’icona [!DNL Insight Server] si desidera configurare e fare clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. La [!DNL Communications.cfg] il file si trova all&#39;interno di questa directory.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nel *nome server* colonna per [!DNL Communications.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nel [!DNL Temp] colonna per [!DNL Communications.cfg].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nel [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In [!DNL Communications.cfg] finestra, fai clic su **[!UICONTROL component]** per visualizzarne il contenuto.
1. In [!DNL Communications.cfg] finestra, fai clic su **[!UICONTROL Servers]** per visualizzarne il contenuto. Possono essere visualizzati diversi tipi di server: File server, server di registrazione, Init Server, server di stato, server di invio o server di replica.
1. Individua LoggingServer, dove [!DNL Sensor] scrive i file di registro da elaborare da [!DNL Insight Server], quindi fai clic sul relativo numero per visualizzare il menu.

   ![Informazioni sul passaggio](assets/cfg_communications_examplevalues_logging.png)

   La directory di registro predefinita è la [!DNL Logs] nella cartella [!DNL Insight Server] directory di installazione.

1. Modificare il parametro della directory di registro per riflettere la posizione desiderata dei file di registro.

   >[!NOTE]
   >
   >Non modificare altri parametri di LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Diversi FileServer possono essere elencati sotto il nodo Server, quindi potrebbe essere necessario visualizzare il contenuto di molti di essi (cliccando i loro numeri nel [!DNL Servers] elenco) per trovare il server con un Percorso locale dei registri\ da modificare.

1. Modifica il Percorso locale per riflettere la posizione desiderata del [!DNL .vsl] file.

   >[!NOTE]
   >
   >Non modificare altri parametri per FileServer.

   Anche se il percorso dei file di registro è stato modificato nel [!DNL Communications.cfg] puoi mappare questi file nella directory Logs della [!DNL Server Files Manager] specificando /Logs/ come URI per FileServer.

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
