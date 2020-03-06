---
description: La funzionalità di trasformazione (Transform) viene eseguita su un computer server workbench dati per consentire l'esportazione dei dati di origine del registro da utilizzare da altre applicazioni.
solution: Analytics
title: Informazioni sulle funzionalità di trasformazione
topic: Data workbench
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informazioni sulle funzionalità di trasformazione{#about-transformation-functionality}

La funzionalità di trasformazione (Transform) viene eseguita su un computer server workbench dati per consentire l&#39;esportazione dei dati di origine del registro da utilizzare da altre applicazioni.

[!DNL Transform] può leggere [!DNL .vsl] file, file di registro, file XML e dati ODBC ed esportare i dati come [!DNL .vsl] file, file di testo o file di testo delimitati che possono essere utilizzati da routine di caricamento DataWarehouse, agenzie di controllo o altri target. L&#39;estrazione e la trasformazione dei dati possono essere eseguite in modo continuo o su altra base programmata.

>[!NOTE]
>
>In genere [!DNL Transform] è configurato su un FSU di un server workbench dati. Tuttavia, l&#39;implementazione potrebbe richiedere la configurazione su un DPU server workbench dati. Per ulteriori informazioni, contattate Adobe.

È possibile visualizzare le informazioni sull&#39;utilizzo della memoria [!DNL Transform] nell&#39;interfaccia Stato dettagliato. Per ulteriori informazioni, vedere il capitolo relativo alle interfacce amministrative della Guida *utente di Workbench* dati.

La funzione di esportazione del segmento fornisce un altro metodo per esportare i dati da un’applicazione Adobe. [!DNL Transform] consente di esportare dati non elaborati in una destinazione esterna, ma la funzione di esportazione del segmento consente di inviare i dati elaborati dal dataset e richiede che i dati esportati siano definiti come una dimensione nel dataset. Per ulteriori informazioni sull&#39;esportazione dei segmenti, vedere la Guida *utente di Workbench* dati.
