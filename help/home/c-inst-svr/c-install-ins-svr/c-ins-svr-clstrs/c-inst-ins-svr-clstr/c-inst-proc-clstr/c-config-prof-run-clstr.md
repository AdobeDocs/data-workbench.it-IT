---
description: Quando configurate un profilo di set di dati da eseguire su un cluster di Insight Server, tutti i computer del cluster condividono tutti i file di configurazione del set di dati per tale profilo.
solution: Analytics
title: Configurazione di un profilo da eseguire su un cluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---


# Configurazione di un profilo da eseguire su un cluster{#configuring-a-profile-to-run-on-a-cluster}

Quando configurate un profilo di set di dati da eseguire su un cluster di Insight Server, tutti i computer del cluster condividono tutti i file di configurazione del set di dati per tale profilo.

Di conseguenza, le voci dei parametri in questi file devono essere applicabili a tutti [!DNL Insight Servers] nel cluster. Ad esempio, le posizioni dei file di registro da leggere, i file di ricerca da utilizzare [!DNL Insight Server]e la posizione dell&#39;output dei dati da parte di [!DNL Insight Server] devono essere le stesse su tutti i computer del cluster.

Tutte le attività di configurazione vengono eseguite sul master del cluster [!DNL Insight Server], ovvero [!DNL Insight Server] per modificare i file di configurazione. Tutte le modifiche salvate apportate al file di configurazione principale [!DNL Insight Server] vengono sincronizzate automaticamente con i file di elaborazione del [!DNL Insight Servers] cluster.

Per eseguire un profilo di dataset su un [!DNL Insight Server] cluster, è necessario eseguire i seguenti processi nell&#39;ordine indicato:

1. [Determinazione Dei Server Insight Che Elaborano I Dati Dell’Evento](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Specifica dei server di elaborazione in Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Se necessario) [Modifica dei file di configurazione del set di dati per il profilo](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Determinazione Dei Server Insight Che Elaborano I Dati Dell’Evento {#section-59b8e3f2b34f49739d544c8740a62fba}

Non è necessario che tutti i dati [!DNL Insight Servers] dell&#39;evento del processo cluster siano inclusi nel processo. È possibile designare una [!DNL Insight Server] unità del cluster come File Server Unit che memorizza i file di origine (VSL e file di registro) e distribuisce i file a tutte le unità di elaborazione dati (server di elaborazione) del cluster. Questa configurazione offre il vantaggio di un unico archivio dati evento e sfrutta la potenza di elaborazione di tutti i server di elaborazione del cluster. I server di elaborazione dividono i file di dati tra di essi e garantiscono che lo stesso file non venga elaborato più di una volta.

Per ulteriori informazioni sulla designazione di un&#39;unità [!DNL Insight Server] da eseguire come unità del file server, vedere il capitolo File di configurazione dell&#39;elaborazione del registro della Guida alla configurazione del *set di dati*.

Se si decide di archiviare i file di dati di origine su ciascuno dei server di elaborazione anziché su una singola unità File Server, è necessario suddividere i file in modo uniforme tra i server di elaborazione. Non memorizzare tutti i file sorgente del dataset su ciascuno dei server di elaborazione. Se più copie dello stesso file sono disponibili su più server di elaborazione, i dati vengono letti più volte (una per ogni computer) e distorcono i dati.

Per informazioni sull&#39; [!DNL Insight Servers] elaborazione dei file di registro, contattare  Consulenza del Adobe.

## Specifica dei server di elaborazione in Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

Nel [!DNL profile.cfg] file, specificare i server di elaborazione che elaborano i dati per il profilo.

**Per accedere al file profile.cfg**

Potete accedere al file di configurazione del profilo utilizzando il [!DNL Profile Manager] componente in [!DNL Insight].

1. Quando lavori nel profilo del set di dati, apri il modulo facendo clic con il pulsante destro del mouse all’interno di un’area di lavoro e facendo clic su [!DNL Profile Manager] > **[!UICONTROL Admin]** > **[!UICONTROL Profile]** , oppure aprendo l’area di lavoro Gestione profilo nella **[!UICONTROL Profile Manager]**[!DNL Admin] scheda.

1. Fare [!DNL Profile Manager]clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e quindi scegliere **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.

1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Viene visualizzata la finestra di configurazione del profilo.

**Per aggiungere i server di elaborazione**

1. Nel [!DNL profile.cfg] file, fare clic **[!UICONTROL Profile]**, quindi fare clic **[!UICONTROL Processing Servers]** per visualizzarne il contenuto.

1. Fare clic con il pulsante destro del mouse **[!UICONTROL Processing Servers]** e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. Nel parametro Nome comune, digitate il nome comune per il primo server di elaborazione del cluster. Ad esempio: [!DNL server1.mycompany.com]
1. Ripetere i passaggi 2 e 3 fino a quando non vengono aggiunti i nomi comuni di tutti i server di elaborazione del cluster.

   >[!NOTE]
   >
   >Se il master [!DNL Insight Server] elabora i dati, è necessario aggiungerli.

1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

1. Fare clic con il pulsante destro del mouse sul segno di spunta nella [!DNL User] colonna accanto a [!DNL profile.cfg]. Fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Modifica dei file di configurazione del set di dati per il profilo {#section-99bf9248e4e5483cb518f453b0a2f278}

**Per modificare i file di configurazione del dataset**

Se è necessario apportare modifiche ai file di configurazione del set di dati ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], i set di dati includono file [!DNL Log Processing Mode.cfg], e così via), farlo solo sul master [!DNL Insight Server].

1. Accedete ai file che desiderate modificare:

   Per istruzioni su come accedere ai file, vedere la Guida alla configurazione del *set di dati*.
1. Apporta le modifiche. Per informazioni dettagliate sui parametri all&#39;interno dei file di configurazione, vedere la Guida *alla configurazione del set di* dati.
1. Salvate il file.

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta nella [!DNL User] colonna accanto al nome del file.
   1. Fate clic su **[!UICONTROL Save to]** e selezionate il profilo desiderato.

>[!NOTE]
>
>[!DNL Insight] gli utenti che accedono a un profilo di set di dati in esecuzione su un cluster identificano solo il master [!DNL Insight Server] nel file di [!DNL Insight] configurazione ( [!DNL insight.cfg]). Dal punto di vista dell&#39; [!DNL Insight] utente, il profilo è accessibile solo su un [!DNL Insight Server] (il master [!DNL Insight Server]); tuttavia, le richieste di query degli analisti possono essere indirizzate a qualsiasi [!DNL Insight Servers] nel cluster.

Un [!DNL Insight Server] cluster consente la memorizzazione centralizzata dei file di [!DNL .vsl] registro (da [!DNL Sensor]) su un singolo [!DNL Insight Server] computer, denominato File Server Unit (FSU). Per informazioni sull&#39;installazione di un FSU, vedere Procedure di [installazione per un FSU](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)di Insight Server. Per informazioni sulla configurazione di un FSU, vedere la Guida alla configurazione del *set di dati*.
