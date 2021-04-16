---
description: Il profilo Geografia fornito con data workbenchGeography è un profilo interno che fornisce funzionalità aggiuntive all’applicazione Adobe.
title: Installazione del profilo geografico
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# Installazione del profilo geografico{#installing-the-geography-profile}

Il profilo Geografia fornito con data workbenchGeography è un profilo interno che fornisce funzionalità aggiuntive all’applicazione Adobe.

Come per tutti gli altri profili interni forniti dall’Adobe, il profilo [!DNL Geography] non deve essere modificato. Tutte le personalizzazioni devono verificarsi nel set di dati o nei profili specifici per il ruolo o in altri profili creati.

Il profilo [!DNL Geography] include diversi set di dati di trasformazione che definiscono le dimensioni geografiche, inclusi i file (che si trovano nella cartella [!DNL Dataset\Transformation\Geography] ). Di seguito è riportato un elenco del set di dati di trasformazione che include i file forniti con il profilo [!DNL Geography] :

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

A ogni file viene assegnato un nome per la dimensione estesa definita. Un file aggiuntivo, [!DNL IPLookup.cfg], definisce diversi campi di dati geografici utilizzati per definire dimensioni nell’altro set di dati di trasformazione che includono file.

Per informazioni sui file di inclusione dei set di dati di trasformazione, consulta la *Guida alla configurazione del set di dati*.

**Per installare il  [!DNL Geography] profilo sul server di Data Workbench**

>[!NOTE]
>
>Le istruzioni di installazione seguenti presuppongono l’installazione di Data Workbench e l’impostazione di una connessione tra Data Workbench e il server di Data Workbench sul quale si sta installando Data Workbench [!DNL Geography]. Se non lo hai fatto, consulta la *Data Workbench guida utente*.

1. Apri la cartella Profiles dal file [!DNL .zip] fornito in Adobe.
1. Copia la cartella [!DNL Geography] nella cartella Profiles nella directory di installazione del server di Data Workbench. Desideri ritrovarti con una cartella [!DNL ...\Profiles\Geography] sul server di Data Workbench come mostrato nell’esempio seguente. I nomi delle altre cartelle all’interno della cartella Profiles possono essere diversi da quelli visualizzati.

   ![Informazioni sul passaggio](assets/Geo_installProfiles_dir.png)

1. Utilizza i passaggi seguenti per aggiornare il file [!DNL profile.cfg] per ciascun profilo con cui desideri utilizzare Data Workbench [!DNL Geography].

   1. Apri [!DNL Profile Manager].
   1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].

   1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene visualizzata la finestra [!DNL profile.cfg].

   1. Nella finestra [!DNL profile.cfg], fai clic con il pulsante destro del mouse su **[!UICONTROL Directories]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Per aggiungere la nuova directory alla fine dell’elenco di directory, fare clic con il pulsante destro del mouse sul numero o sul nome dell’ultima directory nell’elenco e fare clic su **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digitare il nome della nuova directory: [!DNL Geography].
   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL profile.cfg] nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe (incluso il profilo [!DNL Geography] ), in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.
