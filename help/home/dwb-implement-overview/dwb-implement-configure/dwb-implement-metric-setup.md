---
description: Questa sezione spiega come creare metriche in Data Workbench.
title: Impostazione delle metriche
uuid: 57c1410b-c09c-4a59-b3a1-575323e1b8e3
exl-id: a60c08d3-f708-43be-a14f-8b7f129f3ee5
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Impostazione delle metriche{#metrics-setup}

Questa sezione spiega come creare metriche in Data Workbench.

## Informazioni sulle metriche {#section-f0412e851fcb4ac9886dca4003d42cec}

Le metriche sono informazioni quantitative sull’attività del cliente come visualizzazioni, ordini, numero di chiamate effettuate e ricavi. Le metriche sono alla base dei rapporti e ti aiutano a visualizzare e comprendere le relazioni tra i dati.

Il Dimension della metrica consente di raggruppare i conteggi delle metriche per un livello specifico. Consente inoltre di raggruppare i conteggi delle metriche per un livello specifico.

## Creazione di nuove metriche {#section-60a413899d1b4707965e06fb5ef7fc4e}

Per creare una nuova metrica, effettua le seguenti operazioni:

1. Fai clic su **Strumento** > **Editor metriche**.

1. Nell’editor delle metriche, immetti il nuovo nome e la nuova formula della metrica. ![](assets/dwb_impl_metrics1.png)

1. Salvarlo nella cartella Metriche. ![](assets/dwb_impl_metrics2.png)

## Creazione e modifica di metriche derivate {#section-ebdcd3ec652f485e90e001d694eab6d0}

Utilizza un editor metriche per definire una nuova metrica per nome, formula e formato, che viene salvata nella cartella [!DNL User\profile_name\Metrics] per un utilizzo successivo.

1. Apri un nuovo editor di metriche utilizzando l&#39;opzione di menu **Amministratore > Profilo** oppure facendo clic con il pulsante destro del mouse sulla colonna Utente relativa alla cartella in cui desideri creare la metrica e facendo clic su **Crea > Nuova metrica**. Viene visualizzato un Editor metriche.

1. Nel parametro *Name* , digita un nome per la nuova metrica.

   >[!NOTE]
   >
   >Gli spazi ( ) sono consentiti quando i caratteri di sottolineatura (_) non lo sono. Inoltre, non è possibile utilizzare i seguenti simboli: + - * /

   ![](assets/dwb_impl_metrics3.png)

1. Nel parametro *Formula* , digita un’espressione per la nuova metrica.

   >[!NOTE]
   I filtri devono essere definiti tra parentesi [ ] nell&#39;espressione. Per ulteriori regole di sintassi delle espressioni metriche, consulta [Sintassi delle espressioni metriche.](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

   Questa tabella fornisce espressioni di esempio per metriche estese. ![](assets/dwb_impl_metrics4.png)

   >[!NOTE]
   Quando immetti un’espressione appropriata, la riga di anteprima visualizza il valore della nuova metrica. Se l’espressione contiene un errore, nella riga di anteprima viene visualizzato un messaggio di errore.

1. Fai clic con il pulsante destro del mouse e seleziona **Salva**. Quando salvi la metrica, nel computer viene creato un file che rappresenta la nuova metrica nella cartella DWB *Directory di installazione \User\profile name\Metrics*.

## Modifica delle metriche derivate esistenti {#section-4b5b7baf885b45cc8b358d1bd774e925}

1. Nel Profile Manager (Gestore profilo) o Metrics Manager (Gestore metriche), nella colonna del nome del profilo, fate clic con il pulsante destro del mouse sul segno di spunta per il file della metrica da modificare e fate clic su **Make Local** (Rendi locale).
1. Fai clic con il pulsante destro del mouse sul segno di spunta per il file della metrica nella colonna Utente e fai clic su **Apri** dal workbench.

   >[!NOTE]
   Per aprire un editor di metriche, fai clic con il pulsante destro del mouse su un’area correlata alle metriche all’interno di una visualizzazione per visualizzare il menu delle metriche.

1. In **Editor metriche**, modifica e salva la definizione della metrica secondo necessità utilizzando i passaggi 2-4 in *Creazione di nuove metriche derivate*.

   Se desideri che tutti gli utenti del profilo utilizzino la metrica modificata, devi pubblicarla nel profilo di lavoro utilizzando Gestione profili.

Per ulteriore assistenza, consulta la documentazione:

[Sintassi delle espressioni metriche](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

[Creazione e modifica di metriche derivate](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/profile-mgr/c-drvd-mtrcs.html)
