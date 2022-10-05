---
description: Informazioni sul monitoraggio dei set di dati e sull’aggiunta di nuove posizioni per l’archiviazione dei dati dei set di dati.
title: Monitoraggio dello spazio dei dati del set di dati
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---

# Monitoraggio dello spazio dei dati del set di dati{#monitoring-dataset-data-space}

{{eol}}

Informazioni sul monitoraggio dei set di dati e sull’aggiunta di nuove posizioni per l’archiviazione dei dati dei set di dati.

**Frequenza consigliata:** Ogni 5-10 minuti

Per impostazione predefinita, [!DNL Insight Server] scrive il relativo set di dati in [!DNL temp.db] file nella stessa unità [!DNL Insight Server] file di programma sull&#39;unità di elaborazione dati. Quantità di dati di set di dati per [!DNL Insight Server] la macchina è limitata al seguente, a seconda di quale dei due si verifica per primo:

* Cinquecento (500) milioni di record di dati immessi in quel set di dati
* Cinquecento (500) GB di dati di set di dati memorizzati
* Una (1) MB di dati di set di dati memorizzati per ogni dimensione a livello di radice (ad esempio, 5.000 record per visitatore a una media di 200 byte per record)

Se vuoi [!DNL Insight Server] per mantenere il set di dati su un&#39;unità diversa, o se la quantità di dati che si prevede di raccogliere richiede l&#39;uso di più unità, è necessario aggiornare il file di configurazione File disco ( [!DNL Disk Files.cfg]) per specificare la posizione desiderata [!DNL Insight Server] per scrivere [!DNL temp.db] file. La [!DNL Disk Files.cfg] il file elenca i file del disco (un vettore di stringhe) e specifica la posizione dei dati del set di dati utilizzati da [!DNL Insight Server] durante la rielaborazione e il funzionamento. Di solito c&#39;è un file per unità fisica.

>[!NOTE]
>
>Contenuto della [!DNL Disk Files.cfg] è possibile che il file sia stato modificato durante l&#39;installazione [!DNL Insight Server]. Per ulteriori informazioni, consulta [Configurazione della posizione del set di dati (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Aggiunta di nuove posizioni per l’archiviazione dei dati dei set di dati**

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.
1. Fai clic con il pulsante destro del mouse sull’icona [!DNL Insight Server] si desidera configurare e fare clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. La [!DNL Disk Files.cfg] il file si trova all&#39;interno di questa directory.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nel *nome server* colonna per [!DNL Disk Files.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nel [!DNL Temp] colonna per [!DNL Disk Files.cfg].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nel [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In [!DNL Disk Files.cfg] finestra, fai clic su **[!UICONTROL component]** per visualizzarne il contenuto.

   ![Informazioni sul passaggio](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Il parametro Rileva la corruzione del disco è impostato su true per impostazione predefinita. Il parametro Dimensione cache disco (MB) controlla la quantità di memoria che [!DNL Insight Server] utilizza per aumentare la velocità di accesso al disco ed è impostato su 128 per impostazione predefinita. Contatta l&#39;Adobe prima di modificare uno di questi parametri.

1. Per modificare i file del disco nel [!DNL Insight Server] computer, clic con il pulsante destro del mouse **[!UICONTROL Disk Files]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Per eliminare un file disco, fare clic con il pulsante destro del mouse sul numero del file disco e fare clic su **[!UICONTROL Remove]**.

1. Per il nuovo file disco, immettere la directory e il nome del file da utilizzare [!DNL Insight Server] durante la rielaborazione e il funzionamento.

   ![Informazioni sul passaggio](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Il parametro Rileva la corruzione del disco è impostato su true per impostazione predefinita. Il parametro Dimensione cache disco (MB) controlla la quantità di memoria che [!DNL Insight Server] utilizza per aumentare la velocità di accesso al disco ed è impostato su 128 per impostazione predefinita. Contatta l&#39;Adobe prima di modificare uno di questi parametri.

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
