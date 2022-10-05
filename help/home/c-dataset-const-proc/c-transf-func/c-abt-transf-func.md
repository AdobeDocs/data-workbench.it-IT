---
description: La funzionalità di trasformazione (trasformazione) viene eseguita su un computer server di Data Workbench per abilitare l’esportazione dei dati di origine del registro per l’utilizzo da parte di altre applicazioni.
title: Informazioni sulla funzionalità di trasformazione
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
exl-id: db5d6329-407d-43f3-92fc-1b40f7289916
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---

# Informazioni sulla funzionalità di trasformazione{#about-transformation-functionality}

{{eol}}

La funzionalità di trasformazione (trasformazione) viene eseguita su un computer server di Data Workbench per abilitare l’esportazione dei dati di origine del registro per l’utilizzo da parte di altre applicazioni.

[!DNL Transform] può leggere [!DNL .vsl] file, file di registro, file XML e dati ODBC ed esporta i dati come [!DNL .vsl] file, file di testo o file di testo delimitati che possono essere utilizzati dalle routine di caricamento del DataWarehouse, dalle agenzie di controllo o da altre destinazioni. L’estrazione e la trasformazione dei dati possono essere eseguite in modo continuo o su altra base pianificata.

>[!NOTE]
>
>In genere, [!DNL Transform] è configurato su una FSU del server di Data Workbench. Tuttavia, l’implementazione potrebbe richiedere la configurazione su una DPU del server di Data Workbench. Per ulteriori informazioni, contatta l’Adobe .

È possibile visualizzare le informazioni sull&#39;utilizzo della memoria per [!DNL Transform] nell’interfaccia di stato dettagliato . Per ulteriori informazioni, vedere il capitolo relativo alle interfacce amministrative *Guida utente di Data Workbench*.

La funzione di esportazione del segmento fornisce un altro modo per esportare i dati da un’applicazione di Adobe. [!DNL Transform] consente di esportare dati non elaborati in un target esterno, ma la funzione di esportazione del segmento consente di inviare dati elaborati dal set di dati e richiede che i dati esportati siano definiti come una dimensione nel set di dati. Per ulteriori informazioni sull’esportazione dei segmenti, consulta la sezione *Guida utente di Data Workbench*.
