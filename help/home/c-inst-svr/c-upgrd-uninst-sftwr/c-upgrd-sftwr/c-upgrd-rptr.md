---
description: Istruzioni per l'aggiornamento Ripetitore con Insight o per l'aggiornamento copiando i file.
solution: Analytics
title: Aggiornamento di Repeater
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---


# Aggiornamento di Repeater{#upgrading-repeater}

Istruzioni per l&#39;aggiornamento Ripetitore con Insight o per l&#39;aggiornamento copiando i file.

Per effettuare l’aggiornamento dalla piattaforma 4.x o [!DNL Repeater] versioni successive, potete utilizzare uno dei seguenti metodi:

* Se avete creato una connessione tra [!DNL Insight] e [!DNL Repeater] come descritto in [Creazione di una connessione tra Insight e Ripetitore](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), potete utilizzare [!DNL Insight] per effettuare l&#39;aggiornamento [!DNL Repeater]. Consultate [Aggiornamento Ripetitore Con Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -oppure-

* Se non è stato possibile creare o meno una connessione tra [!DNL Insight] e [!DNL Repeater], è necessario copiare i file di aggiornamento direttamente nel [!DNL Repeater] computer. Consultate [Aggiornamento del ripetitore mediante la copia dei file](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Aggiornamento Ripetitore Con Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. Sul [!DNL Insight] computer, copiate la [!DNL bin] cartella dal pacchetto di [!DNL Insight Server] aggiornamento alla [!DNL Temp] cartella nella directory in cui [!DNL Insight] è installato.
1. Inizio [!DNL Insight].
1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.
1. Fare clic con il pulsante destro del mouse sull&#39;icona dell&#39; [!DNL Repeater] aggiornamento e scegliere **[!UICONTROL Server Files]**.
1. Per [!DNL Server Files Manager]caricare i file di aggiornamento sul server, effettuate le seguenti operazioni:

   1. Individuate la [!DNL bin] cartella.
   1. Fare clic con il pulsante destro del mouse sul segno di spunta della [!DNL bin] cartella nella directory Temp e selezionare **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Viene visualizzato un messaggio che indica che questo passaggio sovrascrive i file con lo stesso nome presenti sul server. Fare clic **[!UICONTROL Yes]** per continuare.

>[!NOTE]
>
>Se dovete caricare altri file per completare l&#39; [!DNL Repeater] aggiornamento,  Adobe fornirà le istruzioni necessarie.

Dopo aver caricato i file di aggiornamento nel [!DNL Repeater] computer, [!DNL Repeater] si riavvia automaticamente e carica la nuova versione.

## Aggiornamento del ripetitore tramite copia dei file {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Aprite il file di aggiornamento fornito da  Adobe. Probabilmente, questo file è un [!DNL .zip] file da aggiornare [!DNL Insight Server].
1. Andate alla directory in cui avete installato [!DNL Repeater] (ad esempio, [!DNL D:\Adobe\Repeater]).
1. Copiate la [!DNL bin] cartella all’interno del [!DNL .zip] file e incollatela nella directory di [!DNL Repeater] installazione per sovrascrivere la [!DNL bin] cartella esistente.

>[!NOTE]
>
>Se dovete caricare altri file per completare l&#39; [!DNL Insight Server] aggiornamento,  Adobe fornirà le istruzioni necessarie.

Dopo aver copiato i file di aggiornamento nel [!DNL Repeater] computer, [!DNL Repeater] si riavvia automaticamente e carica la nuova versione.
