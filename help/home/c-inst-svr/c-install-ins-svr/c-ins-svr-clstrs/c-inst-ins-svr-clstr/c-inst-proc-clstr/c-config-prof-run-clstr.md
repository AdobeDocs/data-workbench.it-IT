---
description: Quando configuri un profilo di set di dati da eseguire su un cluster Insight Server, tutti i computer del cluster condividono tutti i file di configurazione del set di dati per tale profilo.
title: Configurazione di un profilo da eseguire su un cluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# Configurazione di un profilo da eseguire su un cluster{#configuring-a-profile-to-run-on-a-cluster}

{{eol}}

Quando configuri un profilo di set di dati da eseguire su un cluster Insight Server, tutti i computer del cluster condividono tutti i file di configurazione del set di dati per tale profilo.

Pertanto, le voci per i parametri in questi file devono essere applicabili a tutti [!DNL Insight Servers] nel cluster. Ad esempio, le posizioni dei file di log da leggere, i file di ricerca da utilizzare da [!DNL Insight Server]e la posizione dell&#39;output di dati da [!DNL Insight Server] deve essere lo stesso su tutte le macchine del cluster.

Esegui tutte le attività di configurazione sul master del cluster [!DNL Insight Server], che è [!DNL Insight Server] per modificare i file di configurazione. Tutte le modifiche apportate al file di configurazione salvato sul master [!DNL Insight Server] vengono sincronizzati automaticamente con i file in elaborazione [!DNL Insight Servers] nel cluster.

Per eseguire un profilo di set di dati su un [!DNL Insight Server] cluster, è necessario eseguire i seguenti processi nell&#39;ordine elencato:

1. [Determinazione dei dati evento del processo di Insight Server](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Specifica dei server di elaborazione in Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Se necessario) [Modifica dei file di configurazione del set di dati per il profilo](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Determinazione dei dati evento del processo di Insight Server {#section-59b8e3f2b34f49739d544c8740a62fba}

Non è necessario che tutti [!DNL Insight Servers] nei dati evento del processo cluster. Puoi specificarne uno [!DNL Insight Server] nel cluster come File Server Unit che memorizza i file di origine (VSL e file di registro) e li trasmette a tutte le unità di elaborazione dati (server di elaborazione) nel cluster. Questa configurazione fornisce il vantaggio di un singolo archivio dati evento e sfrutta la potenza di elaborazione di tutti i server di elaborazione del cluster. I server di elaborazione suddividono i file di dati tra di essi e garantiscono che lo stesso file non venga elaborato più di una volta.

Per ulteriori informazioni sulla designazione di un [!DNL Insight Server] per eseguire come unità file server, vedere il capitolo File di configurazione dell&#39;elaborazione del registro *Guida alla configurazione del set di dati*.

Se si decide di memorizzare i file di dati di origine su ciascuno dei server di elaborazione anziché su una singola unità File Server, è necessario suddividerli equamente tra i server di elaborazione. Non archiviare tutti i file di origine del set di dati su ciascuno dei server di elaborazione. Se più copie dello stesso file sono disponibili per più server di elaborazione, i dati vengono letti più volte (una volta per ogni computer) e i dati vengono distorti.

Per determinare quali [!DNL Insight Servers] se si desidera elaborare i file di registro, contattare Adobe Consulting.

## Specifica dei server di elaborazione in Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

In [!DNL profile.cfg] , specifica i server di elaborazione che elaborano i dati per il profilo.

**Per accedere al file profile.cfg**

Accedi al file di configurazione del profilo utilizzando [!DNL Profile Manager] in [!DNL Insight].

1. Quando lavori nel tuo profilo di set di dati, apri la [!DNL Profile Manager] facendo clic con il pulsante destro del mouse all’interno di un’area di lavoro e facendo clic su **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]** oppure aprendo l’area di lavoro Gestione profili in [!DNL Admin] scheda .

1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nel [!DNL User] colonna.

1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Viene visualizzata la finestra di configurazione del profilo.

**Per aggiungere i server di elaborazione**

1. In [!DNL profile.cfg] file, fai clic su **[!UICONTROL Profile]**, quindi fai clic su **[!UICONTROL Processing Servers]** per visualizzarne il contenuto.

1. Fai clic con il pulsante destro del mouse **[!UICONTROL Processing Servers]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. Nel parametro Common Name digitare il nome comune per il primo server di elaborazione nel cluster. Ad esempio: [!DNL server1.mycompany.com]
1. Ripetere i passaggi 2 e 3 fino a quando non sono stati aggiunti i nomi comuni di tutti i server di elaborazione del cluster.

   >[!NOTE]
   >
   >Se il master [!DNL Insight Server] elabora i dati, è necessario aggiungerli anche.

1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

1. Fai clic con il pulsante destro del mouse sul segno di spunta nel [!DNL User] accanto a [!DNL profile.cfg]. Fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Modifica dei file di configurazione del set di dati per il profilo {#section-99bf9248e4e5483cb518f453b0a2f278}

**Per modificare i file di configurazione del set di dati**

Se devi apportare modifiche ai file di configurazione del set di dati ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], i set di dati includono file, [!DNL Log Processing Mode.cfg], e così via), farlo solo sul master [!DNL Insight Server].

1. Accedi ai file che desideri modificare:

   Per istruzioni su come accedere ai file, vedi *Guida alla configurazione del set di dati*.
1. Apporta le modifiche. Consulta la sezione *Guida alla configurazione del set di dati* per informazioni dettagliate sui parametri all’interno dei file di configurazione.
1. Salvate il file.

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nel [!DNL User] accanto al nome del file.
   1. Fai clic su **[!UICONTROL Save to]** e seleziona il profilo desiderato.

>[!NOTE]
>
>[!DNL Insight] gli utenti che accedono a un profilo di set di dati in esecuzione su un cluster identificano solo il principale [!DNL Insight Server] in [!DNL Insight] file di configurazione ( [!DNL insight.cfg]). Dal punto di vista della [!DNL Insight] utente, il profilo è accessibile su un solo [!DNL Insight Server] (il comandante [!DNL Insight Server]); tuttavia, le richieste di query degli analisti possono essere indirizzate a uno qualsiasi dei [!DNL Insight Servers] nel cluster.

Un [!DNL Insight Server] cluster consente lo storage centralizzato [!DNL .vsl] file di registro (da [!DNL Sensor]) su un solo [!DNL Insight Server] computer denominato File Server Unit (FSU). Per informazioni sull&#39;installazione di una FSU, vedere [Procedure di installazione per una FSU di Insight Server](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). Per informazioni sulla configurazione di una FSU, consulta la *Guida alla configurazione del set di dati*.
