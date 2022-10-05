---
description: Questa sezione è una guida rapida che offre i passaggi minimi necessari per impostare e pianificare gli script per la rielaborazione settimanale dei file di registro. Può essere utilizzato come guida di riferimento per impostare o modificare i profili.
title: Script per la rielaborazione settimanale
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
exl-id: f1b6f12e-629e-47c7-aa15-41f76d1c3192
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 2%

---

# Script per la rielaborazione settimanale{#scripting-to-weekly-reprocess}

{{eol}}

Questa sezione è una guida rapida che offre i passaggi minimi necessari per impostare e pianificare gli script per la rielaborazione settimanale dei file di registro. Può essere utilizzato come guida di riferimento per impostare o modificare i profili.

## Che cosa è la rielaborazione {#section-7e335aacc199488592e78a835e2649fe}

Caricamento dei dati in DWB in base alle modifiche nelle origini dati, nelle origini dati offline o nel periodo di tempo. Lo script rielabora il parametro della data di inizio in *Log Processing.cfg* file.

## Prerequisiti {#section-804acce5df4942469c9313535627038a}

ID suite di rapporti. I dati del numero di mesi devono essere disponibili in DWB. La cartella Perl64 dovrebbe essere disponibile nella C:\ drive.

## Registri di rielaborazione {#section-565d3e1f0df14127a97d9beecd14f02f}

Fornire i dettagli di cui sopra (prerequisiti) nello script di comando di windows *Reprocess.bat* disponibile nella cartella *\scripts\Elaborazione registro* sul server FSU principale.

Questo script chiamerà internamente due script specifici del client: Una per rielaborare i dati e l’altra per l’avviso e-mail. Questi due script sono disponibili anche nel *\scripts\Elaborazione registro* cartella.

Lo script modificherà i parametri di rielaborazione nel *Log Processing.cfg* file.

## Finestra di rotazione per i registri {#section-ed5f44d890b34523ab33da7aa0ae3990}

Fornire i dettagli (prerequisiti) nello script di comando di Windows *logprocessingdate.bat* disponibile nella cartella *\scripts\Scripting* sul server FSU principale. Questo script chiamerà internamente due script specifici del client: Una per impostare la data di inizio dei registri e un&#39;altra per gli avvisi e-mail. Questi due script sono disponibili anche in* \scripts\Scripository*

Immetti l’ID suite di rapporti e il numero di mesi nel file* logprocessing.bat*.

Lo script modificherà il parametro della data di inizio in *Log Processing.cfg*.

>[!NOTE]
>
>Se la *Archivio* la cartella non è disponibile, segui il processo seguente per copiare il *Archivio* e apporta modifiche ai file di cui sopra utilizzando i dettagli specifici per il cliente. E fornisci il tuo indirizzo e-mail per ricevere un avviso in caso di errore.

## Pianificazione degli script {#section-063cf0c755dc47d28d60947d8d43d0e9}

Seguire questi passaggi per pianificare gli script nell&#39;Utilità di pianificazione di Windows.

1. Pianificare lo script nell&#39;utilità di pianificazione delle attività di Windows.

   * Apri Utilità di pianificazione: Fai clic con il pulsante destro del mouse sul pulsante **Libreria di pianificazione attività** e fai clic su **Crea attività**.

   * In **Generale** specificare un nome per l&#39;attività e selezionare **Opzioni**.

   * Sotto la **Triggers** scheda , fai clic su **Nuovo** e si aprirà una nuova finestra.

   * Sotto la **Azioni** scheda , fai clic su **Nuovo** e si aprirà una nuova finestra. Quindi fornisci i dettagli dello script e altre opzioni. (Inizia in avrà un percorso in cui è posizionato lo script).

1. Convalida: Fai clic con il pulsante destro del mouse ed esegui il processo e verifica le modifiche nella *Log processing.cfg* file. Verrà inviata un’e-mail all’ID e-mail fornito nello script.
