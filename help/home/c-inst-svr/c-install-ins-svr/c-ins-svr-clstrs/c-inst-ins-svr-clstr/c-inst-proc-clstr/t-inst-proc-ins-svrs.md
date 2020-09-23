---
description: Un server Insight di elaborazione è identico a un server Insight master, ad eccezione del contenuto della directory Components.
solution: Analytics
title: Installazione e configurazione dell’elaborazione degli Insight Server
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---


# Installazione e configurazione dell’elaborazione degli Insight Server{#installing-and-configuring-the-processing-insight-servers}

Un server Insight di elaborazione è identico a un server Insight master, ad eccezione del contenuto della directory Components.

La directory Components (Componenti) di un&#39;elaborazione [!DNL Insight Server] contiene un set speciale di file configurati specificamente per l&#39;elaborazione [!DNL Insight Servers]. Questi file sono derivati dalla directory Components for Processing Servers del master [!DNL Insight Server].

Quando installate un&#39;elaborazione, [!DNL Insight Server]effettuate le seguenti operazioni per configurare la directory Components (Componenti):

1. Eliminate la directory Componenti originale nell&#39;elaborazione [!DNL Insight Server].
1. Rinominare la directory Components for Processing Servers in Components (Componenti per i server di elaborazione) in Components (Componenti).
1. Modificate il [!DNL Synchronize.cfg] contenuto nella directory Components in modo che punti al master [!DNL Insight Server].

**Per installare e configurare un&#39;elaborazione[!DNL Insight Server]**

1. Installate i file del [!DNL Insight Server] programma come descritto in [Installazione dei file](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)del programma Insight Server. Assicurarsi di duplicare la struttura di directory utilizzata sul master [!DNL Insight Server]. Ad esempio, se [!DNL Insight Server] è installato [!DNL C:\Adobe\Server] sul master [!DNL Insight Server], è necessario installarlo [!DNL C:\Adobe\Server] anche nell&#39;elaborazione [!DNL Insight Servers] .
1. Installate il certificato digitale emesso  Adobe per questa particolare elaborazione [!DNL Insight Server]. Per istruzioni, vedere [Download e installazione dei certificati](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) digitali.
1. In Esplora risorse, effettuare le seguenti operazioni durante l&#39;elaborazione [!DNL Insight Server]:

   1. Delete the **[!UICONTROL Components]** folder.
   1. Rinominare la [!DNL Components for Processing Servers] cartella in Componenti.

1. Utilizzando un editor di testo come Blocco note, aprire il [!DNL Synchronize.cfg] file nella directory Components (Componenti) dell&#39;elaborazione [!DNL Insight Server].
1. Aggiungere l&#39;indirizzo IP del master (primario) [!DNL Insight Server] alla seconda riga del file, come illustrato nel seguente frammento di file. Non modificate nient&#39;altro in questo file.

   ```
   component = SynchronizeComponent:
     Cluster Primary Server Address = string: PrimaryIPAddress
     Directories = vector: 7 items
       0 = SynchronizeDir:
         Local Path = string: Profiles\\
         Remote URI = string: /Profiles/
       1 = SynchronizeDir:
         Local Path = string: Lookups\\
         Remote URI = string: /Lookups/
       . . .
   ```

1. Salvate il file.
1. Avviate [!DNL Insight Server] la procedura descritta in [Registrazione di Insight Server come servizio](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)Windows.

   L&#39;installazione del [!DNL Insight Server] cluster è stata completata. Quindi, configurate il profilo del set di dati da eseguire sul cluster come descritto nella sezione seguente.

