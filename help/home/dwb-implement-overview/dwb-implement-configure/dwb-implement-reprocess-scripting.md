---
description: Questa sezione è una guida rapida che illustra i passaggi minimi necessari per impostare e pianificare gli script per la rielaborazione settimanale dei file di registro. Può essere utilizzato come guida di riferimento per impostare o modificare i profili.
title: Script per la rielaborazione settimanale
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Script per la rielaborazione settimanale{#scripting-to-weekly-reprocess}

Questa sezione è una guida rapida che illustra i passaggi minimi necessari per impostare e pianificare gli script per la rielaborazione settimanale dei file di registro. Può essere utilizzato come guida di riferimento per impostare o modificare i profili.

## Che cos&#39;è la rielaborazione {#section-7e335aacc199488592e78a835e2649fe}

Caricamento dei dati a DWB in base alle modifiche apportate alle origini dati, alle origini dati offline o al periodo di tempo. Lo script rielabora il parametro della data di inizio nel file *Log Processing.cfg* .

## Prerequisiti {#section-804acce5df4942469c9313535627038a}

ID suite di rapporti, numero di dati del mese da rendere disponibili in DWB. La cartella Perl64 dovrebbe essere disponibile nella cartella C:\ drive.

## Rielabora registri {#section-565d3e1f0df14127a97d9beecd14f02f}

Fornire i dettagli di cui sopra (prerequisiti) nello script di comando di Windows *Reprocess.bat* disponibile nella cartella *\scripts\Log Processing* al server FSU principale.

Questo script richiamerà internamente due script specifici del client: Uno per rielaborare i dati e l’altro per l’avviso e-mail. Questi due script sono disponibili anche nella cartella *\scripts\Log Processing* .

Lo script modificherà i parametri di rielaborazione nel file *Log Processing.cfg* .

## Finestra di scorrimento per i registri {#section-ed5f44d890b34523ab33da7aa0ae3990}

Fornire i dettagli (prerequisiti) nel comando di Windows script *logprocessingdate.bat* disponibile nella cartella *\scripts\Scripository* sul server FSU principale. Questo script richiamerà internamente due script specifici del client: Una per impostare la data di inizio dei registri e un&#39;altra per gli avvisi e-mail. Questi due script sono disponibili anche in* \scripts\Scripository*

Specifica l&#39;ID della suite di rapporti e il numero di mesi nel file* logprocessing.bat*.

Lo script modificherà il parametro della data di inizio in *Log Processing.cfg*.

>[!NOTE]
>
>Se la cartella *Scripting* non è disponibile, seguite la procedura riportata di seguito per copiare la cartella *Scripting* e apportare modifiche ai file precedenti utilizzando i dettagli specifici per il cliente. Inoltre, fornisci il tuo indirizzo e-mail per ricevere un avviso in caso di errore.

## Pianificazione di script {#section-063cf0c755dc47d28d60947d8d43d0e9}

Per pianificare gli script nell&#39;Utilità di pianificazione di Windows, procedere come segue.

1. Pianificare lo script nell&#39;Utilità di pianificazione di Windows.

   * Apri Utilità di pianificazione: Fare clic con il pulsante destro del mouse sulla Libreria **Utilità di pianificazione e scegliere** Crea attività ****.

   * Nella scheda **Generale** , specificare un nome per l&#39;attività e selezionare **Opzioni**.

   * Nella scheda **Triggers** , fare clic su **Nuovo** per aprire una nuova finestra.

   * Nella scheda **Azioni** , fare clic su **Nuovo** per aprire una nuova finestra. Fornire quindi i dettagli dello script e altre opzioni. (Inizia in avrà un percorso in cui è posizionato lo script).

1. Convalida: Fare clic con il pulsante destro del mouse ed eseguire il processo e verificare le modifiche nel file *Log processing.cfg* . Viene inviata un&#39;e-mail all&#39;ID e-mail fornito nello script.

