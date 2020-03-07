---
description: È possibile utilizzare il parametro Nascosto o Mostra per nascondere le dimensioni estese in modo che non vengano visualizzate nel menu delle dimensioni nel workbench dati.
solution: Analytics
title: Nascondere le dimensioni estese
topic: Data workbench
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Nascondere le dimensioni estese{#hiding-extended-dimensions}

È possibile utilizzare il parametro Nascosto o Mostra per nascondere le dimensioni estese in modo che non vengano visualizzate nel menu delle dimensioni nel workbench dati.

Quando si immette l&#39;impostazione appropriata per uno dei due parametri, il nome della dimensione non viene elencato nel menu nel workbench dati, ma è ancora nel profilo e può essere utilizzato. Qualsiasi utente del workbench dati può scoprire temporaneamente le dimensioni nascoste impostando il parametro Unhide All nel [!DNL Insight.cfg] file su true.

Per ulteriori informazioni sul parametro Scopri tutto, vedere l&#39;appendice sui parametri di configurazione del workbench dati nella Guida *utente di Workbench* dati.

Nelle sezioni seguenti viene descritto come utilizzare i parametri Nascosto e Mostra per nascondere le dimensioni estese.

* [Nascondere le dimensioni estese utilizzando il parametro nascosto](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Nascondere le dimensioni estese utilizzando il parametro Show](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Nascondere le dimensioni estese utilizzando il parametro nascosto {#section-7167a6f6241a4bc78f2f322e048d65cf}

Il parametro Hidden (Nascosto) è un parametro facoltativo che potete utilizzare per definire le dimensioni estese nei [!DNL Transformation Dataset Configuration] file.

1. Aprire [!DNL Transformation Dataset Configuration] i file in cui è definita la dimensione estesa che si desidera nascondere. Consulta [Modifica dei set di dati esistenti Includi file](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Individuate il parametro Nascosto per la dimensione desiderata nella finestra di configurazione e digitate *true*.
1. Salvate il file localmente, quindi salvatelo nel profilo appropriato sul server. Consulta [Modifica dei set di dati esistenti Includi file](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

Il set di dati si ritrasforma, dopo di che la dimensione estesa non viene visualizzata nel menu della dimensione nel workbench dati. Per ulteriori informazioni sul parametro Hidden, consultate Dimensioni [](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)estese.

Se modificate l&#39;impostazione del parametro Nascosto, dovete trasformare nuovamente il dataset affinché la modifica abbia effetto.

## Nascondere le dimensioni estese utilizzando il parametro Show {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

Il parametro Show non è uno dei parametri disponibili per la definizione delle dimensioni estese nei [!DNL Transformation Dataset Configuration] file. Il parametro viene invece definito nei [!DNL .dim] file per tutte le dimensioni derivate create dall’utente. Pertanto, per utilizzare il parametro Show per nascondere una dimensione estesa, è innanzitutto necessario creare una dimensione derivata basata sulla dimensione estesa come descritto nella procedura seguente:

1. Utilizzate un editor di testo come Blocco note per creare un file vuoto denominato &lt;nome ** dimensione>.dim Il nome file deve corrispondere al nome della dimensione che desiderate nascondere. Ad esempio, per nascondere la dimensione Pagina successiva, è necessario creare un [!DNL Next Page.dim] file.

1. Aggiungete il testo seguente al file:

   * entity = ref: wdata/model/dim/Parent/+name
   * show = bool: false

1. Salvate il file nella directory Dimensions (Dimensioni) del profilo. Se lo desiderate, potete salvare il file in una sottodirectory.

Quando si utilizza il parametro Mostra per nascondere una dimensione estesa, non è necessario trasformare nuovamente il dataset per rendere effettiva la modifica. Potete scegliere di nascondere o mostrare la dimensione nella versione locale del profilo (vale a dire, è possibile salvare il [!DNL .dim] file nella cartella Utente), oppure salvare il [!DNL .dim] file sul server per l&#39;utilizzo da parte di altri utenti del profilo.

Potete inoltre utilizzare il parametro Show per nascondere metriche e filtri. Per ulteriori informazioni, vedere il capitolo Configurazione delle funzioni di interfaccia e analisi nella Guida *utente di Workbench* dati.
