---
description: Le nuove dimensioni create con Workbench dati (dette dimensioni derivate) sono dimensioni lato client.
solution: Analytics
title: Operazioni con dimensioni derivate
topic: Data workbench
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Operazioni con dimensioni derivate{#work-with-derived-dimensions}

Le nuove dimensioni create con Workbench dati (dette dimensioni derivate) sono dimensioni lato client.

Invece di definire queste dimensioni durante la creazione e il processo di aggiornamento del set di dati (nel [!DNL Transformation.cfg] file) sui computer server di Workbench dati, le dimensioni derivate vengono create e memorizzate singolarmente come [!DNL .dim] file in un profilo. Di conseguenza, potete modificare le dimensioni esistenti e creare nuove dimensioni derivate senza rielaborare il set di dati.

>[!NOTE]
>
>Per ulteriori informazioni sulle dimensioni rispetto a quelle fornite in questa sezione, vedere la guida dell&#39;applicazione Workbench dati appropriata.

Per ulteriori informazioni sulla configurazione e il processo di aggiornamento del set di dati, consulta la Guida alla configurazione del set di *dati*.

## Creare dimensioni derivate {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Per creare una dimensione derivata, puoi copiare e modificare una dimensione esistente oppure salvare una dimensione da una visualizzazione.

## Creare dimensioni derivate da una dimensione esistente {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Gli utenti più spesso desiderano creare nuove dimensioni temporali da quelle esistenti. Ad esempio, puoi creare una nuova dimensione &quot;Ultimi 5 giorni&quot; dalla dimensione &quot;Ultimi 7 giorni&quot; esistente.

1. Nella [!DNL Profile Manager]colonna del nome *del* profilo fare clic con il pulsante destro del mouse sul segno di spunta per una dimensione simile a quella da creare e fare clic su di essa **[!UICONTROL Copy]**.

   Ad esempio, per copiare il file [!DNL Last 7 Days.dim] dalla cartella Reporting del [!DNL Traffic] profilo, fare clic con il pulsante destro del mouse sul segno di spunta per il nome del file nella [!DNL Traffic] colonna e fare clic su **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Fare clic con il pulsante destro del mouse nella [!DNL User] colonna relativa alla cartella in cui si desidera memorizzare la dimensione copiata e fare clic su **[!UICONTROL Paste]**.

   La dimensione viene visualizzata nella cartella Dimensioni selezionata con un segno di spunta nella [!DNL User] colonna.

1. Per rinominare la nuova dimensione, fare clic con il pulsante destro del mouse sul segno di spunta nella [!DNL User] colonna e digitare il nuovo nome nel [!DNL File] campo.
1. Dal menu di scelta rapida, fate clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Vengono visualizzati i parametri di definizione per la quota.
1. Modificate i parametri in base alle esigenze per definire la nuova dimensione.

   Per le dimensioni temporali, molto probabilmente è necessario modificare solo i parametri Count e Range.

1. Per salvare il file, fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   Se desiderate che tutti gli utenti di un profilo utilizzino la dimensione creata, dovete caricarla nel profilo utilizzando il [!DNL Profile Manager]. Per ulteriori informazioni, consultate [Pubblicazione di file nel profilo](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)di lavoro.

Ora puoi usare la nuova dimensione in tutto il profilo corrente selezionandola come faresti per qualsiasi dimensione incorporata.

## Salvataggio di una dimensione da una visualizzazione {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Puoi salvare dimensioni estese da mappe di processo e segmenti. Per i passaggi per salvare una dimensione da una mappa di processo, consulta [Salvataggio di dimensioni da mappe](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051)di processo. Per i passaggi per salvare una dimensione del segmento, consulta [Creazione di dimensioni](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) segmento a pagina 82.

## Salvataggio di un segmento come dimensione {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

Puoi anche salvare segmenti definiti come una dimensione. Per i passaggi, consulta [Riutilizzo di una visualizzazione](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc)segmento.

## Modificare una dimensione derivata esistente {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   Nella [!DNL Profile Manager]colonna del nome *del* profilo fare clic con il pulsante destro del mouse sul segno di spunta del file di dimensione da modificare e fare clic su **[!UICONTROL Make Local]**.
1. Fare clic con il pulsante destro del mouse sul segno di spunta per il file di dimensione nella [!DNL User] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Completate i parametri come necessario. Per ulteriori informazioni, contattate i servizi di consulenza Adobe.
1. Per salvare il file, fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   Se desiderate che tutti gli utenti di un profilo utilizzino la dimensione modificata, dovete caricarla nel profilo utilizzando la [!DNL Profile Manager]. Per ulteriori informazioni, consultate [Pubblicazione di file nel profilo](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)di lavoro.

