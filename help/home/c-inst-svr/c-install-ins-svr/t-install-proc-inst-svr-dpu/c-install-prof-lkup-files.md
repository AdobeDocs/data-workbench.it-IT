---
description: I profili e i file di ricerca sviluppati da Adobe per una particolare applicazione sono profili interni che forniscono le metriche, le dimensioni e le aree di lavoro che consentono l’analisi del set di dati.
title: Installazione di profili e dei file di ricerca
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 2%

---

# Installazione di profili e dei file di ricerca{#installing-profiles-and-lookup-files}

{{eol}}

I profili e i file di ricerca sviluppati da Adobe per una particolare applicazione sono profili interni che forniscono le metriche, le dimensioni e le aree di lavoro che consentono l’analisi del set di dati.

Come per tutti gli altri profili interni forniti dall’Adobe, tali profili non devono essere modificati. Tutte le personalizzazioni devono verificarsi nel set di dati o nei profili specifici per il ruolo o in altri profili creati.

Adobe distribuisce il profilo e i file di ricerca per la tua applicazione come [!DNL .zip] file. Ogni file zip viene denominato per l’applicazione di cui sono contenuti il profilo e i file di ricerca. (Ad esempio, [!DNL Site52.zip] contiene i file di profilo per Site v5.2.) La [!DNL .zip] il file contiene due cartelle ( [!DNL Lookups] e [!DNL Profiles]).

>[!NOTE]
>
>Se non disponi già del file di installazione contenente i profili e i file di ricerca per la tua applicazione, scaricali dal sito FTP di Adobe prima di iniziare.

È necessario installare il profilo e i relativi file di ricerca nel [!DNL Insight Server] computer in cui elabora ed esegui il profilo del set di dati. Se esegui un [!DNL Insight Server] cluster, è necessario installare i file sul server master. Per informazioni sui profili di set di dati, consulta la sezione *Guida alla configurazione del set di dati*.

**Per installare profili per la tua applicazione Adobe**

1. Apri [!DNL Profiles] dalla cartella [!DNL .zip] file fornito dall’Adobe.

1. Copia tutte le cartelle all’interno di [!DNL Profiles] nella cartella [!DNL .zip] al [!DNL Profiles] nella cartella [!DNL Insight Server] directory di installazione. Vuoi finire con [!DNL ...\Profili\]*&lt; [!DNL internal profile name]>* cartelle [!DNL Insight Server] come illustrato nell’esempio seguente. I nomi dei profili effettivi possono essere diversi.

   ![](assets/win_installprofiles.png)

1. Passa a  [!DNL Profiles\]*&lt; [!DNL dataset profile name]>* nella directory in cui è stata installata [!DNL Insight Server] e individua le [!DNL profile.cfg] in questa directory.

   >[!NOTE]
   >
   >Se stai installando i profili per la prima volta, puoi utilizzare il profilo di esempio fornito come profilo di set di dati. È possibile trovare le [!DNL profile.cfg] file (potrebbe essere denominato come [!DNL profile.cfg.offline]) per il profilo di esempio all’interno di [!DNL Profiles\Sample] nella cartella [!DNL Insight Server] directory di installazione.

1. Apri [!DNL profile.cfg] utilizzando un editor di testo come Blocco note e procedi come segue:

   1. Aggiungi le voci per i profili interni nel vettore Directory. I nomi dei profili corrispondono ai nomi delle directory copiate nel [!DNL Profiles] nella cartella [!DNL Insight Server] macchina.

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
      >La *serverCommonName* che si specifica per il Nome comune nel [!DNL profile.cfg] il file corrisponde al nome comune del server per [!DNL Insight Server] computer in cui stai elaborando ed eseguendo il profilo del set di dati. Per istruzioni su come aggiornare [!DNL profile.cfg] in modo che il profilo del set di dati venga eseguito su un [!DNL Insight Server] cluster, vedi [Cluster di Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Salvate il file. Assicurati di salvare il file come [!DNL profile.cfg] se è stato denominato in modo diverso.

**Per installare i file di ricerca per la tua applicazione Adobe**

1. Apri [!DNL Lookups] dalla cartella [!DNL .zip] file fornito dall’Adobe.

1. Copia tutte le cartelle all’interno di [!DNL Lookups] nella cartella [!DNL .zip] al [!DNL Lookups] nella cartella [!DNL Insight Server] directory di installazione. Vuoi finire con [!DNL ...\Lookup\]*&lt; [!DNL internal profile name]>* cartelle [!DNL Insight Server] come illustrato nell’esempio seguente. I nomi dei profili effettivi possono essere diversi.

   ![](assets/win_installLookups.png)
