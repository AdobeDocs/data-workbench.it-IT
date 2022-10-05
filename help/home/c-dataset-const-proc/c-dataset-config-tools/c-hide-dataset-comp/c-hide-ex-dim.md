---
description: È possibile utilizzare il parametro Nascosto o il parametro Mostra per nascondere le dimensioni estese in modo che non vengano visualizzate nel menu della dimensione in Data Workbench.
title: Nascondere le dimensioni estese
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
exl-id: 5baccf39-6f3b-40a1-b1c0-a8e5d6a61211
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 1%

---

# Nascondere le dimensioni estese{#hiding-extended-dimensions}

{{eol}}

È possibile utilizzare il parametro Nascosto o il parametro Mostra per nascondere le dimensioni estese in modo che non vengano visualizzate nel menu della dimensione in Data Workbench.

Quando immetti l’impostazione appropriata per uno dei due parametri, il nome della dimensione non viene elencato nel menu di Data Workbench, ma è ancora nel profilo e può essere utilizzato. Qualsiasi utente di Data Workbench può visualizzare temporaneamente le dimensioni nascoste impostando il parametro Mostra tutto nel [!DNL Insight.cfg] su true.

Per ulteriori informazioni sul parametro Mostra tutto, vedi l’appendice sui parametri di configurazione di Data Workbench nella sezione *Guida utente di Data Workbench*.

Nelle sezioni seguenti viene descritto come utilizzare i parametri Nascosto e Mostra per nascondere le dimensioni estese.

* [Nascondere Dimension estesi utilizzando il parametro nascosto](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Nascondere Dimension estesi utilizzando il parametro Show](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Nascondere Dimension estesi utilizzando il parametro nascosto {#section-7167a6f6241a4bc78f2f322e048d65cf}

Il parametro Hidden è un parametro facoltativo che può essere utilizzato quando si definiscono le dimensioni estese in [!DNL Transformation Dataset Configuration] file.

1. Apri [!DNL Transformation Dataset Configuration] file in cui è definita la dimensione estesa che si desidera nascondere. Vedi [Modifica di Dataset Include Files (File) esistenti](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Individua il parametro Nascosto per la dimensione desiderata nella finestra di configurazione e digita *true*.
1. Salva il file localmente, quindi salvalo sul profilo appropriato sul server. Vedi [Modifica di Dataset Include Files (File) esistenti](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

Il set di dati si ritrasforma, dopodiché la dimensione estesa non viene visualizzata nel menu delle dimensioni in Data Workbench. Per ulteriori informazioni sul parametro Hidden, consulta [Dimension estesi](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

Se modifichi l’impostazione del parametro Hidden , devi trasformare nuovamente il set di dati per rendere effettiva la modifica.

## Nascondere Dimension estesi utilizzando il parametro Show {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

Il parametro Show non è uno dei parametri disponibili per la definizione delle dimensioni estese in [!DNL Transformation Dataset Configuration] file. Il parametro viene invece definito nella [!DNL .dim] file per eventuali dimensioni derivate create dall&#39;utente. Pertanto, per utilizzare il parametro Show per nascondere una dimensione estesa, è innanzitutto necessario creare una dimensione derivata basata sulla dimensione estesa come descritto nella procedura seguente:

1. Utilizza un editor di testo come Blocco note per creare un file vuoto denominato &lt;*nome dimensione*>.dim Il nome del file deve corrispondere al nome della dimensione che si desidera nascondere. Ad esempio, per nascondere la dimensione Pagina successiva, crea un [!DNL Next Page.dim] file.

1. Aggiungi al file il seguente testo:

   * entity = ref: wdata/model/dim/Parent/+name
   * show = bool: false

1. Salva il file nella directory dei Dimension del profilo. Se lo desideri, puoi salvare il file in una sottodirectory.

Quando utilizzi il parametro Show per nascondere una dimensione estesa, non devi trasformare nuovamente il set di dati per rendere effettiva la modifica. Puoi scegliere di nascondere o mostrare la dimensione nella versione locale del profilo, ovvero puoi salvare il [!DNL .dim] file nella cartella Utente), oppure è possibile salvare [!DNL .dim] al server per essere utilizzato da altri utenti del profilo.

Puoi inoltre utilizzare il parametro Show per nascondere metriche e filtri. Per informazioni, consulta il capitolo Configurazione dell’interfaccia e delle funzioni di analisi in *Guida utente di Data Workbench*.
