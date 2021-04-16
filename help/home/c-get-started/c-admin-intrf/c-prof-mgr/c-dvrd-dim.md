---
description: Le nuove dimensioni create con Data Workbench (definite dimensioni derivate) sono dimensioni lato client.
title: Operazioni con dimensioni derivate
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
exl-id: 5b7e3a2a-ac61-4186-ad6c-234edf68af3e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 1%

---

# Operazioni con dimensioni derivate{#work-with-derived-dimensions}

Le nuove dimensioni create con Data Workbench (definite dimensioni derivate) sono dimensioni lato client.

Invece di definire queste dimensioni durante la costruzione e il processo di aggiornamento del set di dati (nel file [!DNL Transformation.cfg]) sui computer del server di Data Workbench, le dimensioni derivate vengono create e memorizzate singolarmente come file [!DNL .dim] in un profilo. Di conseguenza, puoi modificare le dimensioni esistenti e creare nuove dimensioni derivate senza rielaborare il set di dati.

>[!NOTE]
>
>Per ulteriori informazioni sulle dimensioni rispetto a quelle fornite in questa sezione, consulta la guida all’applicazione Data Workbench appropriata.

Per ulteriori informazioni sul processo di configurazione e aggiornamento del set di dati, consulta la *Guida alla configurazione del set di dati*.

## Creare dimensioni derivate {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Per creare una dimensione derivata, puoi copiare e modificare una dimensione esistente oppure salvare una dimensione da una visualizzazione.

## Creare dimensioni derivate da una dimensione esistente {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Gli utenti più spesso desiderano creare nuove dimensioni temporali da quelle esistenti. Ad esempio, puoi creare una nuova dimensione &quot;Ultimi 5 giorni&quot; dalla dimensione &quot;Ultimi 7 giorni&quot; esistente.

1. Nella colonna [!DNL Profile Manager], nella colonna *nome profilo* fare clic con il pulsante destro del mouse sul segno di spunta per una dimensione simile a quella che si desidera creare, quindi fare clic su **[!UICONTROL Copy]**.

   Ad esempio, per copiare il [!DNL Last 7 Days.dim] dalla cartella Reporting del profilo [!DNL Traffic], fai clic con il pulsante destro del mouse sul segno di spunta relativo al nome del file nella colonna [!DNL Traffic] e fai clic su **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Fare clic con il pulsante destro del mouse nella colonna [!DNL User] relativa alla cartella in cui si desidera memorizzare la dimensione copiata e fare clic su **[!UICONTROL Paste]**.

   La dimensione viene visualizzata nella cartella dei Dimension selezionati con un segno di spunta nella colonna [!DNL User].

1. Per rinominare la nuova dimensione, fai clic con il pulsante destro del mouse sul relativo segno di spunta nella colonna [!DNL User] e digita il nuovo nome nel campo [!DNL File] .
1. Dal menu di scelta rapida, fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Vengono visualizzati i parametri di definizione della dimensione.
1. Modifica i parametri in base alle esigenze per definire la nuova dimensione.

   Per le dimensioni temporali, molto probabilmente è necessario modificare solo i parametri Count e Range.

1. Per salvare il file, fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   Se desideri che tutti gli utenti di un profilo utilizzino la dimensione creata, devi caricarla nel profilo utilizzando [!DNL Profile Manager]. Per ulteriori informazioni, consulta [Pubblicazione di file sul profilo di lavoro](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

Ora puoi utilizzare la nuova dimensione in tutto il profilo corrente selezionandola come faresti con una dimensione incorporata.

## Salvare una dimensione da una visualizzazione {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Puoi salvare dimensioni estese da mappe di processo e segmenti. Per i passaggi necessari per salvare una dimensione da una mappa del processo, consulta [Salvataggio di Dimension da Process Maps](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). Per i passaggi necessari per salvare una dimensione di segmento, consulta [Creazione di Dimension di segmento](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) a pagina 82.

## Salvataggio di un segmento come dimensione {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

Puoi anche salvare come dimensione segmenti definiti. Per i passaggi, consulta [Riutilizzo di una visualizzazione segmento](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## Modificare una dimensione derivata esistente {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   Nella colonna [!DNL Profile Manager], nella colonna *nome profilo* fare clic con il pulsante destro del mouse sul segno di spunta del file di dimensione che si desidera modificare e fare clic su **[!UICONTROL Make Local]**.
1. Fai clic con il pulsante destro del mouse sul segno di spunta per il file di dimensione nella colonna [!DNL User] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Completa i parametri in base alle esigenze. Per ulteriori informazioni, contattare Adobe Consulting Services.
1. Per salvare il file, fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   Se desideri che tutti gli utenti di un profilo utilizzino la dimensione modificata, devi caricarla nel profilo utilizzando [!DNL Profile Manager]. Per ulteriori informazioni, consulta [Pubblicazione di file sul profilo di lavoro](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
