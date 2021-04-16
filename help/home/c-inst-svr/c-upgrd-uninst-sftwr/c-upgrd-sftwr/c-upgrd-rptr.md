---
description: Istruzioni per aggiornare Repeater utilizzando Insight o per eseguire l’aggiornamento copiando i file.
title: Aggiornamento di Repeater
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Aggiornamento di Repeater{#upgrading-repeater}

Istruzioni per aggiornare Repeater utilizzando Insight o per eseguire l’aggiornamento copiando i file.

Puoi utilizzare uno dei seguenti metodi per aggiornare [!DNL Repeater] da Platform 4.x o versione successiva:

* Se hai creato una connessione tra [!DNL Insight] e [!DNL Repeater] come descritto in [Creazione di una connessione tra Insight e il Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), puoi utilizzare [!DNL Insight] per aggiornare [!DNL Repeater]. Consultare [Aggiornamento del Repeater Using Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -oppure-

* Se non è stato possibile o non è stato possibile creare una connessione tra [!DNL Insight] e [!DNL Repeater], è necessario copiare i file di aggiornamento direttamente nel computer [!DNL Repeater]. Consultare [Aggiornamento del Repeater (Ripetitore) tramite Copia dei file](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Aggiornamento del Repeater tramite Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. Sul computer [!DNL Insight], copia la cartella [!DNL bin] dal pacchetto di aggiornamento [!DNL Insight Server] nella cartella [!DNL Temp] nella directory in cui è installato [!DNL Insight].
1. Inizio [!DNL Insight].
1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.
1. Fai clic con il pulsante destro del mouse sull&#39;icona del [!DNL Repeater] da aggiornare e fai clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], procedi come segue per caricare i file di aggiornamento sul server:

   1. Individua la cartella [!DNL bin] .
   1. Fare clic con il pulsante destro del mouse sul segno di spunta della cartella [!DNL bin] nella directory Temp e selezionare **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Verrà visualizzato un messaggio che indica che questo passaggio sovrascrive i file con lo stesso nome presenti sul server. Fai clic su **[!UICONTROL Yes]** per continuare.

>[!NOTE]
>
>Se hai bisogno di caricare altri file per completare l&#39;aggiornamento [!DNL Repeater], Adobe ti fornirà le istruzioni necessarie.

Dopo aver caricato i file di aggiornamento sul computer [!DNL Repeater], [!DNL Repeater] si riavvia automaticamente e carica la nuova versione.

## Aggiornamento del Repeater tramite copia dei file {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Apri il file di aggiornamento fornito da Adobe. Molto probabilmente, questo file è un file [!DNL .zip] per l&#39;aggiornamento [!DNL Insight Server].
1. Vai alla directory in cui hai installato [!DNL Repeater] (ad esempio, [!DNL D:\Adobe\Repeater]).
1. Copia la cartella [!DNL bin] all&#39;interno del file [!DNL .zip] e incollala nella directory di installazione [!DNL Repeater] per sovrascrivere la cartella [!DNL bin] esistente.

>[!NOTE]
>
>Se hai bisogno di caricare altri file per completare l&#39;aggiornamento [!DNL Insight Server], Adobe ti fornirà le istruzioni necessarie.

Dopo aver copiato i file di aggiornamento nel computer [!DNL Repeater], [!DNL Repeater] si riavvia automaticamente e carica la nuova versione.
