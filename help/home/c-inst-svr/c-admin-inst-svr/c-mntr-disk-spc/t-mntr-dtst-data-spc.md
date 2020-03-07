---
description: Informazioni sul monitoraggio dei dataset e l'aggiunta di nuove posizioni per l'archiviazione dei dati dei dataset.
solution: Insight
title: Monitoraggio dello spazio dei dati
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Monitoraggio dello spazio dei dati{#monitoring-dataset-data-space}

Informazioni sul monitoraggio dei dataset e l&#39;aggiunta di nuove posizioni per l&#39;archiviazione dei dati dei dataset.

**Frequenza consigliata:** Ogni 5-10 minuti

Per impostazione predefinita, [!DNL Insight Server] scrive il relativo dataset nel [!DNL temp.db] file sulla stessa unità dei file del [!DNL Insight Server] programma nell&#39;unità di elaborazione dati. La quantità di dati del dataset per [!DNL Insight Server] computer è limitata a quanto segue, a seconda di quale dei due dati si verifica per primo:

* Cinquecento (500) milioni di record di dati immessi in quel set di dati
* Cinquecento (500) GB di dati dataset memorizzati
* Uno (1) MB di dati dataset memorizzati per ogni dimensione a livello di radice (ad esempio, 5.000 record per visitatore a una media di 200 byte per record)

Se si desidera [!DNL Insight Server] mantenere il dataset su un&#39;unità diversa, o se la quantità di dati che si prevede di raccogliere richiede l&#39;uso di più unità, è necessario aggiornare il file di configurazione dei File disco ( [!DNL Disk Files.cfg]) per specificare dove si desidera [!DNL Insight Server] scrivere i [!DNL temp.db] file. Il [!DNL Disk Files.cfg] file elenca i file del disco (un vettore di stringhe) e specifica la posizione dei dati del dataset utilizzati da [!DNL Insight Server] durante la rielaborazione e l&#39;operazione. Di solito c&#39;è un file per unità fisica.

>[!NOTE]
>
>Il contenuto del [!DNL Disk Files.cfg] file potrebbe essere stato modificato durante l&#39;installazione [!DNL Insight Server]. Per ulteriori informazioni, vedere [Configurazione della posizione del set di dati (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Aggiunta di nuove posizioni per la memorizzazione dei dati dei dataset**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.
1. Fare clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] file da configurare e fare clic su **[!UICONTROL Server Files]**.
1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL Disk Files.cfg] file si trova all&#39;interno di questa directory.
1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server per [!DNL Disk Files.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Disk Files.cfg].
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Nella [!DNL Disk Files.cfg] finestra, fate clic **[!UICONTROL component]** per visualizzarne il contenuto.

   ![Informazioni sul passaggio](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Per impostazione predefinita, il parametro Rileva corruzione disco è impostato su true. Il parametro Dimensione cache disco (MB) controlla la quantità di memoria che [!DNL Insight Server] utilizza per aumentare la velocità di accesso al disco ed è impostato su 128 per impostazione predefinita. Contatta Adobe prima di modificare uno di questi parametri.

1. Per modificare i file del disco nel [!DNL Insight Server] computer, fare clic con il pulsante destro del mouse **[!UICONTROL Disk Files]** e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Per eliminare un file su disco, fare clic con il pulsante destro del mouse sul numero del file su disco e fare clic **[!UICONTROL Remove]**.

1. Per il nuovo file del disco, immettere la directory e il nome del file da utilizzare [!DNL Insight Server] durante la rielaborazione e l&#39;operazione.

   ![Informazioni sul passaggio](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Per impostazione predefinita, il parametro Rileva corruzione disco è impostato su true. Il parametro Dimensione cache disco (MB) controlla la quantità di memoria che [!DNL Insight Server] utilizza per aumentare la velocità di accesso al disco ed è impostato su 128 per impostazione predefinita. Contatta Adobe prima di modificare uno di questi parametri.

1. Salvate le modifiche al server effettuando le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. Fare [!DNL Server Files Manager]clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL Temp] colonna e selezionare **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

