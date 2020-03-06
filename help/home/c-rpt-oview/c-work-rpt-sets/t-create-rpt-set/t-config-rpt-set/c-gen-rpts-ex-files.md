---
description: Informazioni per generare rapporti come file Excel.
solution: Analytics
title: Generazione di rapporti come file Microsoft Excel
topic: Data workbench
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Generazione di rapporti come file Microsoft Excel{#generating-reports-as-microsoft-excel-files}

Informazioni per generare rapporti come file Excel.

Devono essere soddisfatti i seguenti requisiti:

* Microsoft Excel deve essere installato sullo stesso computer [!DNL Report Server].
* L&#39;account utente in cui è in esecuzione il [!DNL Report Server] processo deve disporre dell&#39;autorizzazione per accedere a Microsoft Excel.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Quando generate rapporti come file Excel, state aprendo una nuova istanza di Excel. Per ulteriori informazioni su questo processo, vedere [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
   >    * Sebbene il workbench dati supporti più di 256 colonne e 65.536 righe di dati, non è supportato da Microsoft Excel.


Se questi requisiti sono soddisfatti, [!DNL Report Server] viene avviato automaticamente Microsoft Excel e i dati di output di determinate visualizzazioni, legende di dimensioni e valori e annotazioni di testo in una nuova cartella di lavoro Excel con una visualizzazione per foglio di lavoro.

>[!NOTE]
>
>I dati non vengono esportati da grafici, browser di percorsi, mappe di processo, grafici a dispersione e globi.

A meno che non sia stato specificato un valore [!DNL Custom Title] per la visualizzazione, come nome del foglio di lavoro viene utilizzato il tipo di finestra (ad esempio, Tabella filmato).

Per ulteriori informazioni sulla specifica [!DNL Custom Titles] per le visualizzazioni, consulta la Guida [client](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html)Workbench dati.

## Utilizzo di un file modello {#section-40ab11916f464b1a88214ab969da6751}

Potete inoltre generare un rapporto come file Excel utilizzando un modello di file Excel ( [!DNL .xls] o [!DNL .xlsx]). L&#39;utilizzo di un file modello può ridurre il tempo impiegato per formattare i dati ogni volta che viene generato il rapporto.

Questo file modello deve essere un [!DNL .xls] file o [!DNL .xlsx] non un [!DNL .xlt] file.

Potete scegliere di definire un modello per ogni singolo rapporto, un modello generico per tutti i rapporti o una combinazione di entrambi. Questi due elementi non si escludono a vicenda; potete quindi definire un modello generico e definire anche modelli specifici.

Per generare un rapporto utilizzando un modello generico utilizzato per tutti i rapporti, è necessario specificare il nome del file Excel nel parametro Modello Excel predefinito nel file [!DNL Report.cfg] per tale set di rapporti, quindi posizionare il file modello nella stessa cartella del [!DNL Report.cfg] set di rapporti (directory *di installazione workbench* dati\*ProfileName*\Reports\*ReportSetName*). Per informazioni su questo parametro, consultate Parametri [](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.

Per generare un rapporto utilizzando un modello specifico per un rapporto, è necessario assegnare al file Excel lo stesso nome del file dell&#39;area di lavoro del rapporto ( [!DNL .vw]), quindi inserire il file modello nella stessa cartella del file dell&#39;area di lavoro del rapporto ( [!DNL .vw]).

Quando il rapporto viene generato, i fogli a schede esistenti nel modello (ciascuno dei quali rappresenta una visualizzazione) vengono ricompilati con i dati più recenti del rapporto, mentre le nuove finestre che non sono presenti nel modello come schede vengono ignorate. Tutti gli altri schede del file modello rimangono invariati.

Inoltre, se nel file Excel modello è definita una macro che si desidera eseguire automaticamente al momento della generazione del rapporto, assegnare alla macro il nome &quot;VSExport&quot;.
