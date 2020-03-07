---
description: È possibile esportare i dati in determinate finestre in un file Excel (.xls o .xlsx) o in un file di valori separati da tabulazioni (.tsv).
solution: Analytics
title: Esporta dati finestra
topic: Data workbench
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Esporta dati finestra{#export-window-data}

È possibile esportare i dati in determinate finestre in un file Excel (.xls o .xlsx) o in un file di valori separati da tabulazioni (.tsv).

I dati non vengono esportati da grafici, browser di percorsi, mappe di processo, grafici a dispersione e globi.

## Esportare i dati della finestra in Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

Per esportare dati di singole finestre in Microsoft Excel, è necessario soddisfare i seguenti requisiti:

* Microsoft Excel deve essere installato sullo stesso computer di Workbench dati.
* L&#39;account utente in cui è in esecuzione il processo Workbench dati deve disporre dell&#39;autorizzazione per accedere a Microsoft Excel.
* Quando si esportano i dati come file Excel, si apre una nuova istanza di Excel.
* Sebbene Workbench dati supporti più di 256 colonne e 65.536 righe di dati, le versioni di Microsoft Excel precedenti alla 8.0 non sono supportate.

Se questi requisiti sono soddisfatti, Workbench dati avvia automaticamente Microsoft Excel ed esporta i dati in una nuova cartella di lavoro Excel quando si seleziona l&#39;opzione di **[!UICONTROL Export To Excel]** menu.

**Per esportare i dati della finestra in un file .xls o .xlsx**

Fare clic con il pulsante destro del mouse sul bordo superiore della finestra e scegliere **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Viene aperta una nuova cartella di lavoro contenente i dati esportati. A meno che non sia stato fornito un titolo personalizzato (come descritto nella sezione seguente), la cartella di lavoro viene denominata utilizzando la tabella del giorno [!DNL Export title] (Tabella del giorno nell&#39;esempio precedente).

## Applicare titoli personalizzati {#section-2a6559df812a470685e43923b7b9024e}

Se si fornisce un titolo personalizzato per una finestra (utilizzando il [!DNL Custom title] campo del [!DNL Export] menu), il foglio di lavoro al quale i dati vengono esportati da Workbench dati viene denominato utilizzando questo titolo personalizzato invece del titolo nel [!DNL Export title] campo (Tabella giorno nell&#39;esempio precedente).

**Applicazione di un titolo personalizzato a una visualizzazione**

1. Fare clic con il pulsante destro del mouse sul bordo superiore della finestra, quindi fare clic nel **[!UICONTROL Custom title]** campo.
1. you

![](assets/mnu_window_TitleBar_Export.png)

Quando si esporta la visualizzazione in Excel, il foglio di lavoro contenente i dati per questa finestra viene denominato utilizzando il titolo specificato al posto del titolo nel [!DNL Export title] campo.

## Esportare i dati della finestra in un file TSV {#section-93c6b24f7338430aaf5a63b99b9489e8}

**Per esportare una finestra in un file .tsv**

Fare clic con il pulsante destro del mouse sul bordo superiore della finestra e scegliere **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. Viene visualizzata la [!DNL Save Window] finestra di dialogo.
1. Passate alla directory in cui desiderate salvare il file. Se necessario, modificate il nome del file e fate clic su **[!UICONTROL Save]**.

