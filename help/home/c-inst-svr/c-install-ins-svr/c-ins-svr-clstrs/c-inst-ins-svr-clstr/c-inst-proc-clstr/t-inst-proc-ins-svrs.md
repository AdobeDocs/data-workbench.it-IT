---
description: L'elaborazione di Insight Server è identica a quella di un master Insight Server, ad eccezione del contenuto della directory Components.
title: Installazione e configurazione dell’elaborazione degli Insight Server
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# Installazione e configurazione dell’elaborazione degli Insight Server{#installing-and-configuring-the-processing-insight-servers}

{{eol}}

L&#39;elaborazione di Insight Server è identica a quella di un master Insight Server, ad eccezione del contenuto della directory Components.

Directory Componenti in un’elaborazione [!DNL Insight Server] contiene un set speciale di file configurati specificatamente per l&#39;elaborazione [!DNL Insight Servers]. Questi file sono derivati dalla directory Components for Processing Servers nel master [!DNL Insight Server].

Quando si installa un&#39;elaborazione [!DNL Insight Server], effettua le seguenti operazioni per configurare la relativa directory Componenti :

1. Elimina la directory Componenti originale nell’elaborazione [!DNL Insight Server].
1. Rinomina la directory Components for Processing Servers in Components (Componenti per server di elaborazione).
1. Modifica la [!DNL Synchronize.cfg] nella directory Components per puntare al master [!DNL Insight Server].

**Per installare e configurare un’elaborazione[!DNL Insight Server]**

1. Installa il [!DNL Insight Server] file di programma come descritto in [Installazione dei file del programma Insight Server](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). Assicurati di duplicare la struttura della directory utilizzata sul master [!DNL Insight Server]. Ad esempio, se [!DNL Insight Server] è installato in [!DNL C:\Adobe\Server] sul master [!DNL Insight Server], è necessario installarlo in [!DNL C:\Adobe\Server] sul trattamento [!DNL Insight Servers] anche.
1. Installa il certificato digitale rilasciato dall&#39;Adobe per questa particolare elaborazione [!DNL Insight Server]. Vedi [Download e installazione dei certificati digitali](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) per istruzioni.
1. Utilizzando Esplora risorse, effettuare le seguenti operazioni sull&#39;elaborazione [!DNL Insight Server]:

   1. Elimina **[!UICONTROL Components]** cartella.
   1. Rinomina il [!DNL Components for Processing Servers] su Componenti.

1. Utilizzando un editor di testo come Blocco note, apri la [!DNL Synchronize.cfg] nella directory Components dell&#39;elaborazione [!DNL Insight Server].
1. Aggiungi l’indirizzo IP del master (principale) [!DNL Insight Server] alla seconda riga del file, come illustrato nel frammento di file seguente. Non modificare altri elementi del file.

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
1. Avvia la [!DNL Insight Server] come descritto in [Registrazione di Insight Server come servizio Windows](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   È stata completata l&#39;installazione del [!DNL Insight Server] cluster. Quindi, configura il profilo di set di dati da eseguire sul cluster come descritto nella sezione seguente.
