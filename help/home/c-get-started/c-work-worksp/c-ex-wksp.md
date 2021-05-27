---
description: È possibile esportare un'area di lavoro come file di immagine .png o esportare i dati da determinate finestre in un file Excel (.xls o .xlsx).
title: Esportare un’area di lavoro
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
exl-id: 87416ddf-2ac0-4f95-ae8e-71051061c757
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# Esportare un’area di lavoro{#export-a-workspace}

È possibile esportare un&#39;area di lavoro come file di immagine .png o esportare i dati da determinate finestre in un file Excel (.xls o .xlsx).

## Esporta le aree di lavoro come file PNG {#section-f9fbe0f0a1c341e2b063cce106cac35e}

È possibile salvare un&#39;istantanea di un&#39;area di lavoro in formato grafico a rete portatile (`.png` file). Quando si salvano le aree di lavoro come file `.png` sono disponibili le seguenti opzioni di colore:

* **Lo** sfondo nero copia l’area di lavoro come visualizzata.
* **Lo** sfondo bianco copia gli elementi dell’area di lavoro a colori e li visualizza su uno sfondo bianco.
* **Lo sfondo bianco (bianco e nero)** copia gli elementi dell’area di lavoro in scala di grigi e li visualizza su uno sfondo bianco.

**Per esportare un’area di lavoro come file .png**

Nel menu della barra del titolo di un’area di lavoro, fai clic su **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]***.

Viene visualizzata la finestra di dialogo [!UICONTROL Save Image As].

Passa alla directory in cui desideri salvare il file, modifica il nome del file se necessario e fai clic su **[!UICONTROL Save]**.

## Esportare i dati dell&#39;area di lavoro in Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

Durante l’esportazione di un’area di lavoro in Excel, Data Workbench esporta dati da determinate visualizzazioni, legende di dimensioni e valori e annotazioni di testo in una nuova cartella di lavoro Excel con una visualizzazione per foglio di lavoro.

Per esportare le aree di lavoro e le singole finestre in Microsoft Excel, è necessario soddisfare i seguenti requisiti:

* Microsoft Excel deve essere installato sullo stesso computer di Data Workbench.
* L&#39;account utente in cui è in esecuzione il processo di Data Workbench deve disporre dell&#39;autorizzazione per accedere a Microsoft Excel.

>[!NOTE]
>
>* Quando si esportano dati come file Excel, si apre una nuova istanza di Excel. Per ulteriori informazioni su questo processo, consulta [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
>* Sebbene Data Workbench supporti più di 256 colonne e 65.536 righe di dati, le versioni di Microsoft Excel precedenti alla versione 8.0 non lo supportano.
>



Se questi requisiti sono soddisfatti, Data Workbench avvia automaticamente Microsoft Excel ed esporta i dati in una nuova cartella di lavoro Excel. I dati non vengono esportati dalle seguenti visualizzazioni: grafici, browser dei percorsi, mappe dei processi, grafici a dispersione e globi.

## Applica titoli personalizzati {#section-a332e157554546cb8e88922a8d7a4fa2}

A meno che non sia stato specificato un titolo personalizzato per la finestra nel menu [!UICONTROL Export], il nome del foglio di lavoro viene utilizzato come [!UICONTROL Export title] elencato (ad esempio, Tabella città).

1. Fai clic con il pulsante destro del mouse sul bordo superiore della finestra e fai clic sul campo **[!UICONTROL Custom title]** .
1. Digitare il titolo da applicare alla finestra.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>Se immetti un trattino (-) nel campo [!UICONTROL Custom title] , questa visualizzazione non viene esportata con l’area di lavoro.

Quando si esporta l&#39;area di lavoro in Excel, il foglio di lavoro contenente i dati per questa finestra viene denominato utilizzando il titolo specificato al posto del titolo nel campo [!UICONTROL Export title].

## Esportare un&#39;area di lavoro o una barra laterale in Excel {#section-360438b66d5f4734826ab463b4a01a75}

**Per esportare i dati dell’area di lavoro in un nuovo  [!DNL .xls] file o in un nuovo  [!DNL .xlsx] file**

1. Nella barra del titolo dell’area di lavoro, fai clic su **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. Specifica se esportare l’area di lavoro, la barra laterale o entrambi.

## Esporta in un file Excel modello {#section-814772929ca64cf6b92b89d3fdd02302}

Puoi esportare i dati nell&#39;area di lavoro in un file Excel modello (`.xls` o `.xlsx`). L&#39;utilizzo di un file modello può ridurre la quantità di tempo impiegato per la formattazione dei dati ogni volta che l&#39;area di lavoro viene esportata.

>[!NOTE]
>
>Questo file modello deve essere un file `.xls` o `.xlsx`, non un file `.xlt`.

Quando i dati vengono esportati, i fogli a schede esistenti nel modello (ciascuno dei quali rappresenta una visualizzazione) vengono ricompilati con i dati più recenti dell’area di lavoro, mentre le nuove finestre che non sono presenti nel modello come schede vengono ignorate. Tutti gli altri fogli a schede nel file modello rimangono invariati.

Inoltre, se nel file Excel del modello è definita una macro che si desidera eseguire automaticamente quando il report viene generato, denominare la macro &quot;VSExport&quot;.

Supponiamo che desideri utilizzare i dati della campagna esportati da una visualizzazione di tabella in un grafico a torta su un altro foglio a schede in un file Excel e desideri aggiornare tali informazioni ogni settimana. È possibile utilizzare un modello in modo da non dover ricreare i riferimenti dal foglio a schede della tabella al foglio a schede del grafico a torta ogni volta che si desidera aggiornare i dati. I dati della tabella vengono aggiornati al momento dell’esportazione, aggiornando automaticamente il grafico a torta.

**Per esportare i dati dell’area di lavoro in un modello  [!DNL .xls] o in un  [!DNL .xlsx] file**

1. Fai clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e fai clic su **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. Specifica se esportare un’area di lavoro, una barra laterale o entrambi.

   Viene visualizzata la finestra di dialogo [!UICONTROL Select a template worksheet].

1. Completa uno dei seguenti passaggi, a seconda dei casi:

   * Se utilizzi un file modello `.xls`:

      1. Individua e seleziona il file modello `.xls` .
      1. Fai clic su **[!UICONTROL Open]**.
   * Se utilizzi un file modello `.xlsx`:

      1. Individua il percorso del file modello. Il nome del file `.xlsx` non viene visualizzato.
      1. Nel campo [!UICONTROL File name], digita `.xlsx` e fai clic su **[!UICONTROL Open]**. Tutti i nomi dei file `.xlsx` vengono visualizzati nell’elenco dei file.

      1. Selezionare il file modello `.xlsx`.
      1. Fai clic su **[!UICONTROL Open]**.
