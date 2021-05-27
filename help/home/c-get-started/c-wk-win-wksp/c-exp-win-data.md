---
description: È possibile esportare i dati in alcune finestre in un file Excel (.xls o .xlsx) o in un file di valori separati da tabulazioni (.tsv).
title: Esportare i dati della finestra
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
exl-id: ab931453-d366-4d3a-990e-7a368328da2d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# Esportare i dati della finestra{#export-window-data}

È possibile esportare i dati in alcune finestre in un file Excel (.xls o .xlsx) o in un file di valori separati da tabulazioni (.tsv).

I dati non vengono esportati da grafici, browser dei percorsi, mappe dei processi, grafici a dispersione e globi.

## Esportare i dati della finestra in Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

Per esportare dati di singole finestre in Microsoft Excel, è necessario soddisfare i seguenti requisiti:

* Microsoft Excel deve essere installato sullo stesso computer di Data Workbench.
* L&#39;account utente in cui è in esecuzione il processo di Data Workbench deve disporre dell&#39;autorizzazione per accedere a Microsoft Excel.
* Quando si esportano dati come file Excel, si apre una nuova istanza di Excel.
* Sebbene Data Workbench supporti più di 256 colonne e 65.536 righe di dati, le versioni di Microsoft Excel precedenti alla versione 8.0 non lo supportano.

Se questi requisiti sono soddisfatti, Data Workbench avvia automaticamente Microsoft Excel ed esporta i dati in una nuova cartella di lavoro Excel quando si seleziona l&#39;opzione di menu **[!UICONTROL Export To Excel]**.

**Per esportare i dati della finestra in un file .xls o .xlsx**

Fai clic con il pulsante destro del mouse sul bordo superiore della finestra e fai clic su **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Viene aperta una nuova cartella di lavoro contenente i dati esportati. A meno che non sia stato fornito un titolo personalizzato (come descritto nella sezione seguente), la cartella di lavoro viene denominata utilizzando il nome [!DNL Export title] (Tabella del giorno nell’esempio precedente).

## Applica titoli personalizzati {#section-2a6559df812a470685e43923b7b9024e}

Se si fornisce un titolo personalizzato per una finestra (utilizzando il campo [!DNL Custom title] nel menu [!DNL Export] ), il foglio di lavoro a cui la Data Workbench esporta i dati viene denominato utilizzando questo titolo personalizzato invece del titolo nel campo [!DNL Export title] (Tabella del giorno nell&#39;esempio precedente).

**Applicazione di un titolo personalizzato a una visualizzazione**

1. Fai clic con il pulsante destro del mouse sul bordo superiore della finestra e fai clic sul campo **[!UICONTROL Custom title]** .
1. voi

![](assets/mnu_window_TitleBar_Export.png)

Quando si esporta la visualizzazione in Excel, il foglio di lavoro contenente i dati di questa finestra viene denominato utilizzando il titolo specificato al posto del titolo nel campo [!DNL Export title].

## Esportare i dati della finestra in un file TSV {#section-93c6b24f7338430aaf5a63b99b9489e8}

**Per esportare una finestra in un file .tsv**

Fai clic con il pulsante destro del mouse sul bordo superiore della finestra e fai clic su **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. Viene visualizzata la finestra di dialogo [!DNL Save Window].
1. Passa alla directory in cui desideri salvare il file. Se necessario, modifica il nome del file e fai clic su **[!UICONTROL Save]**.
