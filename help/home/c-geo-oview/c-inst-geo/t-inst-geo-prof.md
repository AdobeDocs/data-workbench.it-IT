---
description: Il profilo Geografia fornito con data workbenchGeography è un profilo interno che fornisce funzionalità aggiuntive all’applicazione Adobe.
title: Installazione del profilo geografico
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# Installazione del profilo geografico{#installing-the-geography-profile}

{{eol}}

Il profilo Geografia fornito con data workbenchGeography è un profilo interno che fornisce funzionalità aggiuntive all’applicazione Adobe.

Come per tutti gli altri profili interni forniti dall’Adobe, il [!DNL Geography] profilo non deve essere modificato. Tutte le personalizzazioni devono verificarsi nel set di dati o nei profili specifici per il ruolo o in altri profili creati.

La [!DNL Geography] Il profilo include diversi set di dati di trasformazione che includono file (che si trovano in [!DNL Dataset\Transformation\Geography] che definiscono le dimensioni geografiche. Di seguito è riportato un elenco del set di dati di trasformazione che include i file forniti con [!DNL Geography] profilo:

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

A ogni file viene assegnato un nome per la dimensione estesa definita. Un file aggiuntivo, [!DNL IPLookup.cfg], definisce diversi campi di dati geografici utilizzati per definire le dimensioni nell’altro set di dati di trasformazione che includono file.

Per informazioni sui file di inclusione dei set di dati di trasformazione, consulta la sezione *Guida alla configurazione del set di dati*.

**Per installare [!DNL Geography] profilo sul server di Data Workbench**

>[!NOTE]
>
>Le istruzioni di installazione seguenti presuppongono l’installazione di Data Workbench e l’impostazione di una connessione tra Data Workbench e il server di Data Workbench sul quale si sta installando Data Workbench [!DNL Geography]. Se non lo hai fatto, consulta la sezione *Guida utente di Data Workbench*.

1. Apri la cartella Profiles dal [!DNL .zip] file fornito dall’Adobe.
1. Copia il [!DNL Geography] nella cartella Profiles della directory di installazione del server di Data Workbench. Vuoi finire con un [!DNL ...\Profiles\Geography] sul server di Data Workbench, come illustrato nell’esempio seguente. I nomi delle altre cartelle all’interno della cartella Profiles possono essere diversi da quelli visualizzati.

   ![Informazioni sul passaggio](assets/Geo_installProfiles_dir.png)

1. Utilizza i seguenti passaggi per aggiornare il [!DNL profile.cfg] file per ogni profilo con cui desideri utilizzare Data Workbench [!DNL Geography].

   1. Apri [!DNL Profile Manager].
   1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nel [!DNL User] colonna.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La [!DNL profile.cfg] viene visualizzata la finestra .

   1. In [!DNL profile.cfg] finestra, clic con il pulsante destro del mouse **[!UICONTROL Directories]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Per aggiungere la nuova directory alla fine dell’elenco delle directory, fare clic con il pulsante destro del mouse sul numero o sul nome dell’ultima directory dell’elenco e fare clic su **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digitare il nome della nuova directory: [!DNL Geography].
   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta [!DNL profile.cfg] in [!DNL User] , quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe (tra cui [!DNL Geography] (profilo), in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a questi profili.
