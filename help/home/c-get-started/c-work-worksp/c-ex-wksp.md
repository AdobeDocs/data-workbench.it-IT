---
description: Potete esportare un’area di lavoro come file immagine .png o esportare i dati da determinate finestre in un file Excel (.xls o .xlsx).
solution: Analytics
title: Esportare un’area di lavoro
topic: Data workbench
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Esportare un’area di lavoro{#export-a-workspace}

Potete esportare un’area di lavoro come file immagine .png o esportare i dati da determinate finestre in un file Excel (.xls o .xlsx).

## Esportare un’area di lavoro come file PNG {#section-f9fbe0f0a1c341e2b063cce106cac35e}

Potete salvare un’istantanea di un’area di lavoro in formato grafico di rete portatile (`.png` file). Quando salvate le aree di lavoro come `.png` file, sono disponibili le seguenti opzioni di colore:

* **Lo sfondo** nero copia l’area di lavoro come visualizzata.
* **Lo sfondo** bianco copia a colori gli elementi dell’area di lavoro e li visualizza su uno sfondo bianco.
* **Lo sfondo bianco (bianco e nero)** copia gli elementi dell’area di lavoro in scala di grigio e li visualizza su uno sfondo bianco.

**Per esportare un’area di lavoro come file .png**

Nel menu della barra del titolo di un’area di lavoro, fate clic su **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>*.

Viene visualizzata la [!UICONTROL Save Image As] finestra di dialogo.

Passare alla directory in cui si desidera salvare il file, modificare il nome del file, se necessario, e fare clic **[!UICONTROL Save]**.

## Esportare i dati dell&#39;area di lavoro in Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

Quando si esporta un&#39;area di lavoro in Excel, Workbench dati esporta dati da determinate visualizzazioni, legende di dimensioni e valori e annotazioni di testo in una nuova cartella di lavoro Excel con una visualizzazione per foglio di lavoro.

Per esportare aree di lavoro e singole finestre in Microsoft Excel, è necessario soddisfare i seguenti requisiti:

* Microsoft Excel deve essere installato sullo stesso computer di Workbench dati.
* L&#39;account utente in cui è in esecuzione il processo Workbench dati deve disporre dell&#39;autorizzazione per accedere a Microsoft Excel.

>[!NOTE]
>
>* Quando si esportano i dati come file Excel, si apre una nuova istanza di Excel. Per ulteriori informazioni su questo processo, vedere [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
>* Sebbene Workbench dati supporti più di 256 colonne e 65.536 righe di dati, le versioni di Microsoft Excel precedenti alla 8.0 non sono supportate.
>



Se questi requisiti sono soddisfatti, Workbench dati avvia automaticamente Microsoft Excel ed esporta i dati in una nuova cartella di lavoro Excel. I dati non vengono esportati dalle seguenti visualizzazioni: grafici, browser di percorsi, mappe di processo, grafici a dispersione e globi.

## Applicare titoli personalizzati {#section-a332e157554546cb8e88922a8d7a4fa2}

A meno che non sia stato specificato un titolo personalizzato per la finestra del [!UICONTROL Export] menu, come nome del foglio di lavoro viene utilizzato l&#39; [!UICONTROL Export title] elenco (ad esempio, Tabella città).

1. Fare clic con il pulsante destro del mouse sul bordo superiore della finestra, quindi fare clic nel **[!UICONTROL Custom title]** campo.
1. Digitare il titolo che si desidera applicare alla finestra.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>Se immetti un trattino (-) nel [!UICONTROL Custom title] campo, la visualizzazione non viene esportata con l’area di lavoro.

Quando si esporta l&#39;area di lavoro in Excel, il foglio di lavoro contenente i dati per questa finestra viene denominato utilizzando il titolo specificato al posto del titolo nel [!UICONTROL Export title] campo.

## Esportare un’area di lavoro o una barra laterale in Excel {#section-360438b66d5f4734826ab463b4a01a75}

**Per esportare i dati dell’area di lavoro in un nuovo[!DNL .xls][!DNL .xlsx]file o in un nuovo file**

1. Nella barra del titolo dell’area di lavoro, fate clic su **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. Specificate se esportare l’area di lavoro, la barra laterale o entrambi.

## Esportazione in un file Excel modello {#section-814772929ca64cf6b92b89d3fdd02302}

Potete esportare i dati nell’area di lavoro in un file Excel modello (`.xls` o `.xlsx`). L’utilizzo di un file modello può ridurre il tempo impiegato per formattare i dati ogni volta che l’area di lavoro viene esportata.

>[!NOTE]
>
>Questo file modello deve essere un `.xls` file o `.xlsx` non un `.xlt` file.

Quando i dati vengono esportati, i fogli a schede esistenti nel modello (ciascuno dei quali rappresenta una visualizzazione) vengono ricompilati con i dati più recenti dall’area di lavoro, mentre le nuove finestre che non sono presenti nel modello come schede vengono ignorate. Tutti gli altri schede del file modello rimangono invariati.

Inoltre, se nel file Excel modello è definita una macro che si desidera eseguire automaticamente al momento della generazione del rapporto, assegnare alla macro il nome &quot;VSExport&quot;.

Supponiamo che desideriate utilizzare i dati della campagna esportati da una visualizzazione di tabella in un grafico a torta su un altro foglio a schede in un file Excel e che desiderate aggiornare queste informazioni ogni settimana. È possibile utilizzare un modello in modo da non dover ricreare i riferimenti dal foglio a schede della tabella al foglio a schede del grafico a torta ogni volta che si desidera aggiornare i dati. I dati della tabella vengono aggiornati al momento dell&#39;esportazione, il che aggiorna automaticamente il grafico a torta.

**Per esportare i dati dell’area di lavoro in un modello[!DNL .xls]o[!DNL .xlsx]file**

1. Fate clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e scegliete **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. Specificate se esportare un’area di lavoro, una barra laterale o entrambi.

   Viene visualizzata [!UICONTROL Select a template worksheet] la finestra di dialogo.

1. Completate uno dei seguenti passaggi, a seconda delle necessità:

   * Se utilizzate un file `.xls` modello:

      1. Individuate e selezionate il `.xls` file modello.
      1. Fai clic su **[!UICONTROL Open]** (Fine).
   * Se utilizzate un file `.xlsx` modello:

      1. Individuate il percorso del file modello. Il nome del `.xlsx` file non viene visualizzato.
      1. Nel [!UICONTROL File name] campo digitare `.xlsx` e fare clic su **[!UICONTROL Open]**. Tutti i nomi `.xlsx` di file vengono visualizzati nell&#39;elenco dei file.

      1. Selezionate il `.xlsx` file modello.
      1. Fai clic su **[!UICONTROL Open]** (Fine).


