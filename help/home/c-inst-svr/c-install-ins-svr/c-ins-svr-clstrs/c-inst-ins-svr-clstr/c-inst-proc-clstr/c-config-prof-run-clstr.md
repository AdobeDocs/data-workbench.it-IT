---
description: Quando configuri un profilo di set di dati da eseguire su un cluster Insight Server, tutti i computer del cluster condividono tutti i file di configurazione del set di dati per tale profilo.
title: Configurazione di un profilo da eseguire su un cluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# Configurazione di un profilo da eseguire su un cluster{#configuring-a-profile-to-run-on-a-cluster}

Quando configuri un profilo di set di dati da eseguire su un cluster Insight Server, tutti i computer del cluster condividono tutti i file di configurazione del set di dati per tale profilo.

Pertanto, le voci per i parametri in questi file devono essere applicabili a tutti [!DNL Insight Servers] nel cluster. Ad esempio, le posizioni dei file di registro da leggere, i file di ricerca da utilizzare per [!DNL Insight Server] e la posizione dell&#39;output di dati per [!DNL Insight Server] devono essere uguali su tutti i computer del cluster.

Esegui tutte le attività di configurazione sul master del cluster [!DNL Insight Server], ovvero la [!DNL Insight Server] utilizzata per modificare i file di configurazione. Tutte le modifiche apportate al file di configurazione salvato sul master [!DNL Insight Server] vengono sincronizzate automaticamente con i file presenti nell&#39;elaborazione [!DNL Insight Servers] nel cluster.

Per eseguire un profilo di set di dati su un cluster [!DNL Insight Server], è necessario eseguire i seguenti processi nell&#39;ordine elencato:

1. [Determinazione dei dati evento del processo di Insight Server](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Specifica dei server di elaborazione in Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Se necessario) [Modifica dei file di configurazione del set di dati per il profilo](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Determinazione dei dati evento del processo di Insight Server {#section-59b8e3f2b34f49739d544c8740a62fba}

Non è necessario che tutti i dati [!DNL Insight Servers] del processo cluster elaborino i dati dell&#39;evento. È possibile designare un [!DNL Insight Server] nel cluster come unità File Server che memorizza i file di origine (file di VSL e di registro) e li distribuisce a tutte le unità di elaborazione dati (server di elaborazione) nel cluster. Questa configurazione fornisce il vantaggio di un singolo archivio dati evento e sfrutta la potenza di elaborazione di tutti i server di elaborazione del cluster. I server di elaborazione suddividono i file di dati tra di essi e garantiscono che lo stesso file non venga elaborato più di una volta.

Per ulteriori informazioni sulla designazione di un [!DNL Insight Server] da eseguire come unità file server, vedere il capitolo File di configurazione dell&#39;elaborazione del registro della *Guida alla configurazione del set di dati*.

Se si decide di memorizzare i file di dati di origine su ciascuno dei server di elaborazione anziché su una singola unità File Server, è necessario suddividerli equamente tra i server di elaborazione. Non archiviare tutti i file di origine del set di dati su ciascuno dei server di elaborazione. Se più copie dello stesso file sono disponibili per più server di elaborazione, i dati vengono letti più volte (una volta per ogni computer) e i dati vengono distorti.

Per informazioni su come determinare quali [!DNL Insight Servers] devono elaborare i file di registro, contatta Adobe Consulting.

## Specifica dei server di elaborazione in Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

Nel file [!DNL profile.cfg] , specifica i server di elaborazione che elaborano i dati per il profilo.

**Per accedere al file profile.cfg**

Per accedere al file di configurazione del profilo, utilizza [!DNL Profile Manager] in [!DNL Insight].

1. Quando lavori nel profilo del set di dati, apri l’area di lavoro [!DNL Profile Manager] facendo clic con il pulsante destro del mouse all’interno di un’area di lavoro e scegliendo **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]** oppure aprendo l’area di lavoro Gestione profili nella scheda [!DNL Admin] .

1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].

1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Viene visualizzata la finestra di configurazione del profilo.

**Per aggiungere i server di elaborazione**

1. Nel file [!DNL profile.cfg], fai clic su **[!UICONTROL Profile]**, quindi fai clic su **[!UICONTROL Processing Servers]** per visualizzarne il contenuto.

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Processing Servers]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. Nel parametro Common Name digitare il nome comune per il primo server di elaborazione nel cluster. Ad esempio: [!DNL server1.mycompany.com]
1. Ripetere i passaggi 2 e 3 fino a quando non sono stati aggiunti i nomi comuni di tutti i server di elaborazione del cluster.

   >[!NOTE]
   >
   >Se il master [!DNL Insight Server] elabora i dati, è necessario aggiungerli anche.

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna [!DNL User] accanto a [!DNL profile.cfg]. Fare clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]***.

## Modifica dei file di configurazione del set di dati per il profilo {#section-99bf9248e4e5483cb518f453b0a2f278}

**Per modificare i file di configurazione del set di dati**

Se devi apportare modifiche ai file di configurazione del set di dati ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], i set di dati includono file [!DNL Log Processing Mode.cfg] e così via), fallo solo sul master [!DNL Insight Server].

1. Accedi ai file che desideri modificare:

   Per istruzioni su come accedere ai file, consulta la *Guida alla configurazione del set di dati*.
1. Apporta le modifiche. Per informazioni dettagliate sui parametri all&#39;interno dei file di configurazione, vedere la *Guida alla configurazione del set di dati* .
1. Salvate il file.

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna [!DNL User] accanto al nome del file.
   1. Fai clic su **[!UICONTROL Save to]** e seleziona il profilo desiderato.

>[!NOTE]
>
>[!DNL Insight] gli utenti che accedono a un profilo di set di dati in esecuzione su un cluster identificano solo il master  [!DNL Insight Server] nel file di  [!DNL Insight] configurazione (  [!DNL insight.cfg]). Dal punto di vista dell’ [!DNL Insight] utente, il profilo è accessibile su un solo [!DNL Insight Server] (il master [!DNL Insight Server]); tuttavia, le richieste di query degli analisti possono essere indirizzate a qualsiasi [!DNL Insight Servers] nel cluster.

Un cluster [!DNL Insight Server] consente la memorizzazione centralizzata dei file di registro [!DNL .vsl] (da [!DNL Sensor]) su un singolo computer [!DNL Insight Server] denominato File Server Unit (FSU). Per informazioni sull&#39;installazione di una FSU, vedere [Procedure di installazione per una FSU di Insight Server](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). Per informazioni sulla configurazione di una FSU, vedere la *Guida alla configurazione del set di dati*.
