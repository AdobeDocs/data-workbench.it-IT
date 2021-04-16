---
description: Informazioni sul monitoraggio dei set di dati e sull’aggiunta di nuove posizioni per l’archiviazione dei dati dei set di dati.
title: Monitoraggio dello spazio dei dati del set di dati
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---

# Monitoraggio dello spazio dei dati del set di dati{#monitoring-dataset-data-space}

Informazioni sul monitoraggio dei set di dati e sull’aggiunta di nuove posizioni per l’archiviazione dei dati dei set di dati.

**Frequenza consigliata:** ogni 5-10 minuti

Per impostazione predefinita, [!DNL Insight Server] scrive il relativo set di dati nel file [!DNL temp.db] sulla stessa unità dei file di programma [!DNL Insight Server] sull’unità di elaborazione dati. La quantità di dati del set di dati per [!DNL Insight Server] computer è limitata ai seguenti, a seconda di quale dei due eventi si verifica per primo:

* Cinquecento (500) milioni di record di dati immessi in quel set di dati
* Cinquecento (500) GB di dati di set di dati memorizzati
* Una (1) MB di dati di set di dati memorizzati per ogni dimensione a livello di radice (ad esempio, 5.000 record per visitatore a una media di 200 byte per record)

Se si desidera che [!DNL Insight Server] mantenga il set di dati su un&#39;unità diversa o se la quantità di dati che si prevede di raccogliere richiede l&#39;utilizzo di più unità, è necessario aggiornare il file di configurazione dei file di disco ( [!DNL Disk Files.cfg]) per specificare dove si desidera che [!DNL Insight Server] scriva i file [!DNL temp.db]. Il file [!DNL Disk Files.cfg] elenca i file del disco (un vettore di stringhe) e specifica la posizione dei dati del set di dati utilizzati da [!DNL Insight Server] durante la rielaborazione e il funzionamento. Di solito c&#39;è un file per unità fisica.

>[!NOTE]
>
>È possibile che il contenuto del file [!DNL Disk Files.cfg] sia stato modificato durante l&#39;installazione di [!DNL Insight Server]. Per ulteriori informazioni, consulta [Configurazione della posizione del set di dati (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Aggiunta di nuove posizioni per l’archiviazione dei dati dei set di dati**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.
1. Fai clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] da configurare e fai clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. Il file [!DNL Disk Files.cfg] si trova all&#39;interno di questa directory.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* per [!DNL Disk Files.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella colonna [!DNL Temp] per [!DNL Disk Files.cfg].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Nella finestra [!DNL Disk Files.cfg] fare clic su **[!UICONTROL component]** per visualizzarne il contenuto.

   ![Informazioni sul passaggio](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Il parametro Rileva la corruzione del disco è impostato su true per impostazione predefinita. Il parametro Dimensione cache disco (MB) controlla la quantità di memoria utilizzata da [!DNL Insight Server] per aumentare la velocità di accesso al disco ed è impostato su 128 per impostazione predefinita. Contatta l&#39;Adobe prima di modificare uno di questi parametri.

1. Per modificare i file del disco sul computer [!DNL Insight Server], fare clic con il pulsante destro del mouse su **[!UICONTROL Disk Files]** e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Per eliminare un file disco, fare clic con il pulsante destro del mouse sul numero del file disco e fare clic su **[!UICONTROL Remove]**.

1. Per il nuovo file disco, immettere la directory e il nome del file da utilizzare [!DNL Insight Server] durante la rielaborazione e il funzionamento.

   ![Informazioni sul passaggio](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Il parametro Rileva la corruzione del disco è impostato su true per impostazione predefinita. Il parametro Dimensione cache disco (MB) controlla la quantità di memoria utilizzata da [!DNL Insight Server] per aumentare la velocità di accesso al disco ed è impostato su 128 per impostazione predefinita. Contatta l&#39;Adobe prima di modificare uno di questi parametri.

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
