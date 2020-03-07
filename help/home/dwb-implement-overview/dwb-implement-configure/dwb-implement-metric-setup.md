---
description: In questa sezione viene illustrato come creare metriche in Workbench dati.
title: Impostazione metriche
uuid: 57c1410b-c09c-4a59-b3a1-575323e1b8e3
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Impostazione metriche{#metrics-setup}

In questa sezione viene illustrato come creare metriche in Workbench dati.

## Informazioni sulle metriche {#section-f0412e851fcb4ac9886dca4003d42cec}

Le metriche sono informazioni quantitative sull&#39;attività del cliente, come visualizzazioni, ordini, numero di chiamate effettuate e entrate. Le metriche sono alla base dei report e consentono di visualizzare e comprendere le relazioni dei dati.

Dimensione metrica consente di raggruppare i conteggi delle metriche per un livello specifico. Consente inoltre di raggruppare i conteggi delle metriche per un livello specifico.

## Creazione di nuove metriche {#section-60a413899d1b4707965e06fb5ef7fc4e}

Per creare una nuova metrica, effettuate le operazioni seguenti:

1. Fate clic su **Strumento** > Editor **** metrica.

1. Nell’editor delle metriche, immetti il nuovo nome e la nuova formula della metrica. ![](assets/dwb_impl_metrics1.png)

1. Salvatelo nella cartella Metrics (Metriche). ![](assets/dwb_impl_metrics2.png)

## Creazione e modifica di metriche derivate {#section-ebdcd3ec652f485e90e001d694eab6d0}

Utilizza un Editor metrica per definire una nuova metrica per nome, formula e formato, che verrà salvata nella [!DNL User\profile_name\Metrics] cartella per un uso successivo.

1. Aprite un nuovo Editor metriche utilizzando l&#39;opzione di menu **Amministratore > Profilo** oppure facendo clic con il pulsante destro del mouse sulla colonna Utente relativa alla cartella in cui desiderate creare la metrica e facendo clic su **Crea > Nuova metrica**. Viene visualizzato un editor di metriche.

1. Nel parametro *Nome* , digita un nome per la nuova metrica.

   >[!NOTE]
   >
   >Si noti che gli spazi ( ) sono consentiti mentre i caratteri di sottolineatura (_) non lo sono. Inoltre, non è possibile utilizzare i seguenti simboli: + - * /

   ![](assets/dwb_impl_metrics3.png)

1. Nel parametro *Formula* digitare un&#39;espressione per la nuova metrica.

   >[!NOTE]
   I filtri devono essere definiti tra parentesi [ ] nell&#39;espressione. Per ulteriori regole di sintassi delle espressioni metriche, consultate [Sintassi delle espressioni metriche.](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

   Questa tabella fornisce espressioni di esempio per le metriche estese. ![](assets/dwb_impl_metrics4.png)

   >[!NOTE]
   Quando viene immessa un&#39;espressione appropriata, la riga di anteprima mostra il valore della nuova metrica. Se si verifica un errore nell&#39;espressione, la riga di anteprima visualizza un messaggio di errore.

1. Fare clic con il pulsante destro del mouse e selezionare **Salva**. Quando si salva la metrica, nel computer viene creato un file che rappresenta la nuova metrica nella cartella \User\profile name\Metrics *della directory di* installazione DWB.

## Modifica delle metriche derivate esistenti {#section-4b5b7baf885b45cc8b358d1bd774e925}

1. In Gestione profili o Gestione metriche, nella colonna del nome del profilo, fai clic con il pulsante destro del mouse sul segno di spunta per il file della metrica da modificare e fai clic su **Rendi locale**.
1. Fare clic con il pulsante destro del mouse sul segno di spunta per il file della metrica nella colonna Utente e scegliere **Apri** dal workbench.

   >[!NOTE]
   Puoi anche aprire un Editor metriche facendo clic con il pulsante destro del mouse su un’area correlata alle metriche all’interno di una visualizzazione per visualizzare il menu delle metriche.

1. Nell’Editor **** metriche, modifica e salva la definizione della metrica secondo necessità utilizzando i passaggi da 2 a 4 in *Creazione di nuove metriche* derivate.

   Se desiderate che tutti gli utenti del profilo utilizzino la metrica modificata, dovete pubblicarla nel profilo di lavoro utilizzando Gestione profili.

Per ulteriori informazioni, consulta la documentazione:

[Sintassi per le espressioni metriche](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

[Creazione e modifica di metriche derivate](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/profile-mgr/c-drvd-mtrcs.html)
