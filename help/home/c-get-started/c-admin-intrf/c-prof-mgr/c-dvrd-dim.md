---
description: Le nuove dimensioni create con Data Workbench (definite dimensioni derivate) sono dimensioni lato client.
title: Operazioni con dimensioni derivate
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
exl-id: 5b7e3a2a-ac61-4186-ad6c-234edf68af3e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 1%

---

# Operazioni con dimensioni derivate{#work-with-derived-dimensions}

{{eol}}

Le nuove dimensioni create con Data Workbench (definite dimensioni derivate) sono dimensioni lato client.

Invece di definire queste dimensioni durante la costruzione del set di dati e il processo di aggiornamento (nel [!DNL Transformation.cfg] nei computer del server di Data Workbench, le dimensioni derivate vengono create e memorizzate singolarmente come [!DNL .dim] file in un profilo. Di conseguenza, puoi modificare le dimensioni esistenti e creare nuove dimensioni derivate senza rielaborare il set di dati.

>[!NOTE]
>
>Per ulteriori informazioni sulle dimensioni rispetto a quelle fornite in questa sezione, consulta la guida all’applicazione Data Workbench appropriata.

Per ulteriori informazioni sul processo di configurazione e aggiornamento del set di dati, consulta la sezione *Guida alla configurazione del set di dati*.

## Creare dimensioni derivate {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Per creare una dimensione derivata, puoi copiare e modificare una dimensione esistente oppure salvare una dimensione da una visualizzazione.

## Creare dimensioni derivate da una dimensione esistente {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Gli utenti più spesso desiderano creare nuove dimensioni temporali da quelle esistenti. Ad esempio, puoi creare una nuova dimensione &quot;Ultimi 5 giorni&quot; dalla dimensione &quot;Ultimi 7 giorni&quot; esistente.

1. In [!DNL Profile Manager], nella *nome profilo* fare clic con il pulsante destro del mouse sul segno di spunta per una dimensione simile a quella che si desidera creare e fare clic su **[!UICONTROL Copy]**.

   Ad esempio, per copiare il [!DNL Last 7 Days.dim] dalla cartella Reporting del [!DNL Traffic] fai clic con il pulsante destro del mouse sul segno di spunta per il nome del file nel [!DNL Traffic] e fai clic su **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Fai clic con il pulsante destro del mouse nel [!DNL User] colonna relativa alla cartella in cui si desidera memorizzare la dimensione copiata e fare clic su **[!UICONTROL Paste]**.

   La dimensione viene visualizzata nella cartella dei Dimension selezionati con un segno di spunta nel [!DNL User] colonna.

1. Per rinominare la nuova dimensione, fai clic con il pulsante destro del mouse sul relativo segno di spunta nella [!DNL User] e digita il nuovo nome nella colonna [!DNL File] campo .
1. Dal menu di scelta rapida, fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Vengono visualizzati i parametri di definizione della dimensione.
1. Modifica i parametri in base alle esigenze per definire la nuova dimensione.

   Per le dimensioni temporali, molto probabilmente è necessario modificare solo i parametri Count e Range.

1. Per salvare il file, fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   Se desideri che tutti gli utenti di un profilo utilizzino la dimensione creata, caricala nel profilo utilizzando la [!DNL Profile Manager]. Per ulteriori informazioni, consulta [Pubblicazione di file nel profilo di lavoro](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

Ora puoi utilizzare la nuova dimensione in tutto il profilo corrente selezionandola come faresti con una dimensione incorporata.

## Salvataggio di una dimensione da una visualizzazione {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Puoi salvare dimensioni estese da mappe di processo e segmenti. Per i passaggi necessari per salvare una dimensione da una mappa del processo, vedi [Salvataggio di Dimension da mappe di processo](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). Per i passaggi necessari per salvare una dimensione di segmento, vedi [Creazione di Dimension di segmenti](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) a pagina 82.

## Salvataggio di un segmento come dimensione {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

Puoi anche salvare come dimensione segmenti definiti. Per i passaggi, vedi [Riutilizzo di una visualizzazione segmento](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## Modificare una dimensione derivata esistente {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   n [!DNL Profile Manager], nella *nome profilo* fare clic con il pulsante destro del mouse sul segno di spunta del file di dimensione che si desidera modificare e fare clic su **[!UICONTROL Make Local]**.
1. Fai clic con il pulsante destro del mouse sul segno di spunta per il file di dimensione nel [!DNL User] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Completa i parametri in base alle esigenze. Per ulteriori informazioni, contattare Adobe Consulting Services.
1. Per salvare il file, fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   Se desideri che tutti gli utenti di un profilo utilizzino la dimensione modificata, caricala nel profilo utilizzando la [!DNL Profile Manager]. Per ulteriori informazioni, consulta [Pubblicazione di file nel profilo di lavoro](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
