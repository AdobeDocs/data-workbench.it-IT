---
description: La funzionalità di trasformazione viene eseguita su un computer FSU di Insight Server per consentire l'esportazione dei dati di origine del registro da utilizzare in altre applicazioni.
solution: Insight
title: Configurazione della trasformazione
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Configurazione della trasformazione{#configuring-transform}

La funzionalità di trasformazione viene eseguita su un computer FSU di Insight Server per consentire l&#39;esportazione dei dati di origine del registro da utilizzare in altre applicazioni.

[!DNL Transform] è in grado di leggere [!DNL .vsl] file di registro, file XML e dati ODBC ed esportare i dati come [!DNL .vsl] file, file di testo o file di testo delimitati che possono essere utilizzati da routine di caricamento data warehouse, agenzie di controllo o altri target. L&#39;estrazione e la trasformazione dei dati possono essere eseguite in modo continuo o su altra base programmata. Ogni [!DNL Insight Server] FSU che fornisce l&#39;output dei dati dell&#39;evento alterati deve essere eseguito [!DNL Transform].

>[!NOTE]
>
>In genere [!DNL Transform] è installato su un [!DNL Insight Server] FSU. Tuttavia, l’implementazione potrebbe richiedere l’installazione su un [!DNL Insight Server] DPU. Per ulteriori informazioni, contattate Adobe.

Per informazioni sui requisiti di sistema per l’installazione, la configurazione e il funzionamento [!DNL Transform]consultate il documento sui requisiti *di sistema* minimi.

Adobe distribuisce la [!DNL Transform] funzionalità come profilo all&#39;interno del [!DNL .zip] file per il pacchetto di [!DNL Insight Server] rilascio. Il [!DNL Transform] profilo è un profilo interno che fornisce funzionalità aggiuntive a [!DNL Insight Server]. Come per tutti gli altri profili interni forniti da Adobe, il profilo non deve essere modificato. Tutta la personalizzazione deve avvenire nel dataset o nei profili specifici del ruolo o in altri profili creati.

Il profilo è costituito dai file seguenti:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* un set di dati di elaborazione del registro include un file

Tutti questi file si trovano nella [!DNL Dataset] cartella del profilo.

**Per installare il[!DNL Transform]profilo su[!DNL Insight Server]**

>[!NOTE]
>
>Le seguenti istruzioni di installazione presuppongono che sia stata installata [!DNL Insight] e stabilita una connessione tra [!DNL Insight] e l’ [!DNL Insight Server] in cui si sta installando [!DNL Transform]. Se non lo avete ancora fatto, consultate la * [!DNL Insight] User Guide*.

1. Aprite il [!DNL .zip] file per il pacchetto di [!DNL Insight Server] rilascio e aprite la [!DNL Profiles] cartella all’interno di tale [!DNL .zip] file.
1. Copiate la [!DNL Transform] cartella nella [!DNL Profiles] cartella della directory di [!DNL Insight Server] installazione. Desiderate finire con una [!DNL ...\Profiles\Transform] cartella sul vostro computer, [!DNL Insight Server] come illustrato nell&#39;esempio seguente.

   ![Informazioni sul passaggio](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Se avete seguito tutti i passaggi per l&#39;installazione [!DNL Insight Server] (consultate [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), potete già avere una [!DNL Transform] cartella nella directory Profili.

1. Per aggiornare il [!DNL profile.cfg] file per il profilo con il quale si desidera utilizzare i passaggi seguenti [!DNL Transform]. Il dataset viene rielaborato al completamento di questi passaggi.

   1. Aprite il [!DNL Profile Manager].
   1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Viene [!DNL profile.cfg] visualizzata la finestra.

   1. Nella [!DNL profile.cfg]finestra, fare clic con il pulsante destro del mouse **[!UICONTROL Directories]** e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Per aggiungere la nuova directory alla fine dell&#39;elenco di directory, fare clic con il pulsante destro del mouse sul numero o sul nome dell&#39;ultima directory dell&#39;elenco e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digitare il nome della nuova directory: [!DNL Transform]
   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. Fare [!DNL Profile Manager]clic con il pulsante destro del mouse sul segno di spunta [!DNL profile.cfg] nella [!DNL User] colonna, quindi scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe (incluso il profilo), in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti a tali profili.

