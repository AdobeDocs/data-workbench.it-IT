---
description: Istruzioni per aggiornare Repeater utilizzando Insight o per eseguire l’aggiornamento copiando i file.
title: Aggiornamento di Repeater
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Aggiornamento di Repeater{#upgrading-repeater}

{{eol}}

Istruzioni per aggiornare Repeater utilizzando Insight o per eseguire l’aggiornamento copiando i file.

Per eseguire l&#39;aggiornamento è possibile utilizzare uno dei metodi seguenti [!DNL Repeater] da Platform 4.x o successivo:

* Se è stata creata una connessione tra [!DNL Insight] e [!DNL Repeater] come descritto in [Creazione di una connessione tra Insight e il Repeater (Ripetitore)](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), puoi utilizzare [!DNL Insight] aggiornamento [!DNL Repeater]. Vedi [Aggiornamento del Repeater con Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -oppure-

* Se non è stato possibile creare o meno una connessione tra [!DNL Insight] e [!DNL Repeater], devi copiare i file di aggiornamento direttamente nel [!DNL Repeater] macchina. Vedi [Aggiornamento del Repeater tramite copia dei file](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Aggiornamento del Repeater con Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. Sulla [!DNL Insight] computer, copia [!DNL bin] dalla cartella [!DNL Insight Server] pacchetto di aggiornamento [!DNL Temp] nella directory in cui [!DNL Insight] è installato.
1. Inizio [!DNL Insight].
1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.
1. Fai clic con il pulsante destro del mouse sull’icona [!DNL Repeater] desideri effettuare l’aggiornamento e fai clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], procedi come segue per caricare i file di aggiornamento sul server:

   1. Individua il [!DNL bin] cartella.
   1. Fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL bin] nella directory Temp e seleziona **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Verrà visualizzato un messaggio che indica che questo passaggio sovrascrive i file con lo stesso nome presenti sul server. Fai clic su **[!UICONTROL Yes]** per continuare.

>[!NOTE]
>
>Se hai bisogno di caricare altri file per completare il tuo [!DNL Repeater] aggiornamento, Adobe fornirà le istruzioni necessarie.

Dopo aver caricato i file di aggiornamento nel [!DNL Repeater] macchina, [!DNL Repeater] si riavvia automaticamente e carica la nuova versione.

## Aggiornamento del Repeater tramite copia dei file {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Apri il file di aggiornamento fornito da Adobe. Molto probabilmente, questo file è un [!DNL .zip] file per l&#39;aggiornamento [!DNL Insight Server].
1. Vai alla directory in cui hai installato [!DNL Repeater] (ad esempio, [!DNL D:\Adobe\Repeater]).
1. Copia il [!DNL bin] nella cartella [!DNL .zip] e incollalo nel [!DNL Repeater] directory di installazione per sovrascrivere l&#39;esistente [!DNL bin] cartella.

>[!NOTE]
>
>Se hai bisogno di caricare altri file per completare il tuo [!DNL Insight Server] aggiornamento, Adobe fornirà le istruzioni necessarie.

Dopo aver copiato i file di aggiornamento nel [!DNL Repeater] macchina, [!DNL Repeater] si riavvia automaticamente e carica la nuova versione.
