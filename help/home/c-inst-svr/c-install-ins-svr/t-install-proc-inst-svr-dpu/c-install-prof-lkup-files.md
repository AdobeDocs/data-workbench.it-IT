---
description: I profili e i file di ricerca sviluppati da Adobe per la vostra applicazione specifica sono profili interni che forniscono le metriche, le dimensioni e le aree di lavoro che consentono l'analisi del set di dati.
solution: Insight
title: Installazione di profili e file di ricerca
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Installazione di profili e file di ricerca{#installing-profiles-and-lookup-files}

I profili e i file di ricerca sviluppati da Adobe per la vostra applicazione specifica sono profili interni che forniscono le metriche, le dimensioni e le aree di lavoro che consentono l&#39;analisi del set di dati.

Come per tutti gli altri profili interni forniti da Adobe, tali profili non devono essere modificati. Tutta la personalizzazione deve avvenire nel dataset o nei profili specifici del ruolo o in altri profili creati.

Adobe distribuisce come [!DNL .zip] file il profilo e i file di ricerca dell’applicazione. Ogni file zip è denominato per l&#39;applicazione il cui profilo e file di ricerca contiene. Ad esempio, [!DNL Site52.zip] contiene i file di profilo per Site v5.2. Il [!DNL .zip] file contiene due cartelle ( [!DNL Lookups] e [!DNL Profiles]).

>[!NOTE]
>
>Se non disponete già del file di installazione che contiene i profili e i file di ricerca per la vostra applicazione, scaricateli dal sito Adobe FTP prima di iniziare.

È necessario installare il profilo e i relativi file di ricerca nel [!DNL Insight Server] computer in cui si elabora ed esegue il profilo del set di dati. Se si sta eseguendo un [!DNL Insight Server] cluster, è necessario installare i file sul server master. Per informazioni sui profili dei set di dati, consulta la Guida alla configurazione dei *set di dati*.

**Per installare i profili per la vostra applicazione Adobe**

1. Aprite la [!DNL Profiles] cartella dal [!DNL .zip] file fornito da Adobe.

1. Copiate tutte le cartelle all’interno della [!DNL Profiles] cartella del [!DNL .zip] file nella [!DNL Profiles] cartella della directory di [!DNL Insight Server] installazione. Vuoi finire con [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>* cartelle [!DNL Insight Server] come illustrato nell&#39;esempio seguente. I nomi effettivi dei profili potrebbero essere diversi.

   ![](assets/win_installprofiles.png)

1. Andate alla cartella [!DNL Profiles\]*&lt;[!DNL dataset profile name]>* nella directory in cui avete installato [!DNL Insight Server] e individuate il [!DNL profile.cfg] file in questa directory.

   >[!NOTE]
   >
   >Se state installando i profili per la prima volta, potete utilizzare il profilo di esempio fornito come profilo di set di dati. Potete trovare il [!DNL profile.cfg] file (potrebbe essere denominato come [!DNL profile.cfg.offline]) per il profilo Sample all&#39;interno della [!DNL Profiles\Sample] cartella nella directory di [!DNL Insight Server] installazione.

1. Aprite il [!DNL profile.cfg] file utilizzando un editor di testo come Blocco note ed effettuate le seguenti operazioni:

   1. Aggiungete voci per i profili interni nel vettore Directory. I nomi dei profili corrispondono ai nomi delle directory copiate nella [!DNL Profiles] cartella del [!DNL Insight Server] computer.

   1. Aggiornate il numero di directory in base alle necessità.
   1. Aggiungi il nome comune del server alla riga Nome comune del file, come evidenziato di seguito:

      ```
      Profile = profileInfo: 
      Directories = vector: n+1 items
        0 = string: Base\\
        1 = string: internal profile name 1\\
        2 = string: internal profile name 2\\
      . . .
        n = string: internal profile name n\\
      Processing Servers = vector: 1 items
        0 = ProfileServerInfo: 
          Common Name = string: serverCommonName
          Server = string: 
      ```

      >[!NOTE]
      >
      >Il *serverCommonName* specificato per il Nome comune nel [!DNL profile.cfg] file corrisponde al nome comune del server per il [!DNL Insight Server] computer in cui si sta elaborando ed eseguendo il profilo del dataset. Per istruzioni sull&#39;aggiornamento in [!DNL profile.cfg] modo che il profilo del set di dati venga eseguito su un [!DNL Insight Server] cluster, vedere [Cluster](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)di server Insight.

1. Salvate il file. Assicurarsi di salvare il file come [!DNL profile.cfg] se avesse un nome diverso.

**Per installare i file di ricerca per l&#39;applicazione Adobe**

1. Aprite la [!DNL Lookups] cartella dal [!DNL .zip] file fornito da Adobe.

1. Copiate tutte le cartelle all’interno della [!DNL Lookups] cartella del [!DNL .zip] file nella [!DNL Lookups] cartella della directory di [!DNL Insight Server] installazione. Vuoi finire con [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>* cartelle [!DNL Insight Server] come illustrato nell&#39;esempio seguente. I nomi effettivi dei profili potrebbero essere diversi.

   ![](assets/win_installLookups.png)

