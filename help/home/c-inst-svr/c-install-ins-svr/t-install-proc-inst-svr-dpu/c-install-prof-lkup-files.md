---
description: I profili e i file di ricerca sviluppati da Adobe per una particolare applicazione sono profili interni che forniscono le metriche, le dimensioni e le aree di lavoro che consentono l’analisi del set di dati.
title: Installazione di profili e dei file di ricerca
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# Installazione di profili e dei file di ricerca{#installing-profiles-and-lookup-files}

I profili e i file di ricerca sviluppati da Adobe per una particolare applicazione sono profili interni che forniscono le metriche, le dimensioni e le aree di lavoro che consentono l’analisi del set di dati.

Come per tutti gli altri profili interni forniti dall’Adobe, tali profili non devono essere modificati. Tutte le personalizzazioni devono verificarsi nel set di dati o nei profili specifici per il ruolo o in altri profili creati.

Adobe distribuisce il profilo e i file di ricerca per la tua applicazione come file [!DNL .zip]. Ogni file zip viene denominato per l’applicazione di cui sono contenuti il profilo e i file di ricerca. (Ad esempio, [!DNL Site52.zip] contiene i file di profilo per Site v5.2.) Il file [!DNL .zip] contiene due cartelle ( [!DNL Lookups] e [!DNL Profiles]).

>[!NOTE]
>
>Se non disponi già del file di installazione contenente i profili e i file di ricerca per la tua applicazione, scaricali dal sito FTP di Adobe prima di iniziare.

Devi installare il profilo e i relativi file di ricerca nel computer [!DNL Insight Server] in cui elabora ed esegui il profilo del set di dati. Se si esegue un cluster [!DNL Insight Server], è necessario installare i file sul server master. Per informazioni sui profili dei set di dati, consulta la *Guida alla configurazione dei set di dati*.

**Per installare profili per la tua applicazione Adobe**

1. Apri la cartella [!DNL Profiles] dal file [!DNL .zip] fornito dall’Adobe.

1. Copia tutte le cartelle all&#39;interno della cartella [!DNL Profiles] nel file [!DNL .zip] nella cartella [!DNL Profiles] nella directory di installazione [!DNL Insight Server]. Vuoi finire con le cartelle  [!DNL ...\Profiles\]*&lt; [!DNL internal profile name]>* sul tuo [!DNL Insight Server] come mostrato nell&#39;esempio seguente. I nomi dei profili effettivi possono essere diversi.

   ![](assets/win_installprofiles.png)

1. Passa alla cartella  [!DNL Profiles\]*&lt; [!DNL dataset profile name]>* nella directory in cui hai installato [!DNL Insight Server] e individua il file [!DNL profile.cfg] in questa directory.

   >[!NOTE]
   >
   >Se stai installando i profili per la prima volta, puoi utilizzare il profilo di esempio fornito come profilo di set di dati. Puoi trovare il file [!DNL profile.cfg] (potrebbe essere denominato come [!DNL profile.cfg.offline]) per il profilo Sample all&#39;interno della cartella [!DNL Profiles\Sample] nella directory di installazione di [!DNL Insight Server].

1. Apri il file [!DNL profile.cfg] utilizzando un editor di testo come Blocco note ed effettua le seguenti operazioni:

   1. Aggiungi le voci per i profili interni nel vettore Directory. I nomi dei profili corrispondono ai nomi delle directory copiate nella cartella [!DNL Profiles] sul computer [!DNL Insight Server].

   1. Aggiorna il numero di directory appropriato.
   1. Aggiungi il nome comune del server alla riga Nome comune in questo file, come evidenziato di seguito:

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
      >Il *serverCommonName* specificato per il Nome comune nel file [!DNL profile.cfg] corrisponde al nome comune del server per il computer [!DNL Insight Server] in cui si sta elaborando ed eseguendo il profilo di set di dati. Per istruzioni su come aggiornare [!DNL profile.cfg] in modo che il profilo del set di dati venga eseguito su un cluster [!DNL Insight Server], consulta [Cluster di Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Salvate il file. Assicurati di salvare il file come [!DNL profile.cfg] se è stato denominato in modo diverso.

**Per installare i file di ricerca per la tua applicazione Adobe**

1. Apri la cartella [!DNL Lookups] dal file [!DNL .zip] fornito dall’Adobe.

1. Copia tutte le cartelle all&#39;interno della cartella [!DNL Lookups] nel file [!DNL .zip] nella cartella [!DNL Lookups] nella directory di installazione [!DNL Insight Server]. Vuoi finire con le cartelle  [!DNL ...\Lookups\]*&lt; [!DNL internal profile name]>* sul tuo [!DNL Insight Server] come mostrato nell&#39;esempio seguente. I nomi dei profili effettivi possono essere diversi.

   ![](assets/win_installLookups.png)
