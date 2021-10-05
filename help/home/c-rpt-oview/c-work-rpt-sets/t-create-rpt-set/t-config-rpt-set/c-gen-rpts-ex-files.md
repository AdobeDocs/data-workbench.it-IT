---
description: Informazioni per generare rapporti come file Excel.
title: Generazione di rapporti come file Microsoft Excel
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 4%

---

# Generazione di rapporti come file Microsoft Excel{#generating-reports-as-microsoft-excel-files}

Informazioni per generare rapporti come file Excel.

Devono essere soddisfatti i seguenti requisiti:

* Microsoft Excel deve essere installato sullo stesso computer di [!DNL Report Server].
* L&#39;account utente in cui è in esecuzione il processo [!DNL Report Server] deve disporre dell&#39;autorizzazione per accedere a Microsoft Excel.

   >[!NOTE]
   >
   >
   >
   >
   >    * Quando si generano rapporti come file Excel, si apre una nuova istanza di Excel. Per ulteriori informazioni su questo processo, consulta [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).
   >    * Anche se Data Workbench supporta più di 256 colonne e 65.536 righe di dati, Microsoft Excel non lo supporta.


Se questi requisiti sono soddisfatti, [!DNL Report Server] avvia automaticamente Microsoft Excel e restituisce dati da determinate visualizzazioni, legende di dimensioni e valori e annotazioni di testo a una nuova cartella di lavoro Excel con una visualizzazione per foglio di lavoro.

>[!NOTE]
>
>I dati non vengono esportati da grafici, browser dei percorsi, mappe dei processi, grafici a dispersione e globi.

A meno che non sia stato specificato un valore [!DNL Custom Title] per la visualizzazione, come nome del foglio di lavoro viene utilizzato il tipo di finestra (ad esempio, Tabella filmato).

Per ulteriori informazioni su come specificare [!DNL Custom Titles] per le visualizzazioni, consulta la [Data Workbench guida client](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html?lang=it).

## Utilizzo di un file modello {#section-40ab11916f464b1a88214ab969da6751}

Puoi anche generare un rapporto come file Excel utilizzando un file Excel modello ( [!DNL .xls] o [!DNL .xlsx]). L&#39;utilizzo di un file modello può ridurre la quantità di tempo impiegato per formattare i dati ogni volta che il rapporto viene generato.

Questo file modello deve essere un file [!DNL .xls] o [!DNL .xlsx], non un file [!DNL .xlt].

Puoi scegliere di definire un modello per ogni singolo rapporto, un modello generico per tutti i rapporti o una combinazione di entrambi. Questi due elementi non si escludono a vicenda, pertanto puoi definire un modello generico e quindi definire anche modelli specifici.

Per generare un rapporto utilizzando un modello generico utilizzato per tutti i rapporti, è necessario specificare il nome del file Excel nel parametro Modello Excel predefinito nel [!DNL Report.cfg] per quel file set di rapporti, quindi posizionare il file modello nella stessa cartella del [!DNL Report.cfg] per quel set di rapporti (*directory di installazione di Data Workbench*\*ProfileName*\Reports\*ReportSetName*). Per informazioni su questo parametro, consulta [Parametri Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

Per generare un rapporto utilizzando un modello specifico per un rapporto, è necessario assegnare al file Excel lo stesso nome del file dell’area di lavoro dei rapporti ( [!DNL .vw]), quindi posizionare il file modello nella stessa cartella del file dell’area di lavoro dei rapporti ( [!DNL .vw]).

Quando il rapporto viene generato, i fogli a schede esistenti nel modello (ciascuno dei quali rappresenta una visualizzazione) vengono ricompilati con i dati più recenti del rapporto, mentre le nuove finestre che non sono presenti nel modello come schede vengono ignorate. Tutti gli altri fogli a schede nel file modello rimangono invariati.

Inoltre, se nel file Excel del modello è definita una macro che si desidera eseguire automaticamente quando il report viene generato, denominare la macro &quot;VSExport&quot;.
