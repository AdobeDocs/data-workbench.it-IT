---
description: Il profilo Geografia fornito con workbenchGeography è un profilo interno che fornisce funzionalità aggiuntive all’applicazione Adobe.
solution: Analytics
title: Installazione del profilo geografico
topic: Data workbench
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installazione del profilo geografico{#installing-the-geography-profile}

Il profilo Geografia fornito con workbenchGeography è un profilo interno che fornisce funzionalità aggiuntive all’applicazione Adobe.

Come per tutti gli altri profili interni forniti da Adobe, il [!DNL Geography] profilo non deve essere modificato. Tutta la personalizzazione deve avvenire nel dataset o nei profili specifici del ruolo o in altri profili creati.

Il [!DNL Geography] profilo include diversi set di dati di trasformazione che includono file (che si trovano nella [!DNL Dataset\Transformation\Geography] cartella) che definiscono dimensioni geografiche. Di seguito è riportato un elenco dei set di dati di trasformazione che include i file forniti con il [!DNL Geography] profilo:

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

A ogni file viene assegnato un nome per la dimensione estesa definita. Un file aggiuntivo, [!DNL IPLookup.cfg], definisce diversi campi di dati geografici utilizzati per definire le dimensioni nell&#39;altro set di dati di trasformazione include i file.

Per informazioni sui set di dati di trasformazione e sui file di inclusione, vedere la Guida alla configurazione del set di *dati*.

**Per installare il[!DNL Geography]profilo sul server workbench dati**

>[!NOTE]
>
>Le seguenti istruzioni di installazione presuppongono l&#39;installazione del workbench dati e la creazione di una connessione tra il workbench dati e il server workbench dati su cui si sta installando il workbench dati [!DNL Geography]. In caso contrario, vedere la Guida *utente di Workbench* dati.

1. Aprite la cartella Profili dal [!DNL .zip] file fornito da Adobe.
1. Copiare la [!DNL Geography] cartella nella cartella Profili nella directory di installazione del server workbench dati. Si desidera finire con una [!DNL ...\Profiles\Geography] cartella sul server workbench dati, come illustrato nell&#39;esempio seguente. I nomi delle altre cartelle all’interno della cartella Profili possono essere diversi da quelli mostrati.

   ![Informazioni sul passaggio](assets/Geo_installProfiles_dir.png)

1. Utilizzare i passaggi seguenti per aggiornare il [!DNL profile.cfg] file per ciascun profilo con il quale si desidera utilizzare il workbench dati [!DNL Geography].

   1. Aprite il [!DNL Profile Manager].
   1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene [!DNL profile.cfg] visualizzata la finestra.

   1. Nella [!DNL profile.cfg] finestra fare clic con il pulsante destro del mouse **[!UICONTROL Directories]** e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Per aggiungere la nuova directory alla fine dell&#39;elenco di directory, fare clic con il pulsante destro del mouse sul numero o sul nome dell&#39;ultima directory dell&#39;elenco e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digitare il nome della nuova directory: [!DNL Geography].
   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. Fare [!DNL Profile Manager]clic con il pulsante destro del mouse sul segno di spunta [!DNL profile.cfg] nella [!DNL User] colonna, quindi scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe (incluso il [!DNL Geography] profilo), in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti a tali profili.

