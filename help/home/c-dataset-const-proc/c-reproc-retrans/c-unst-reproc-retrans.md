---
description: Durante la rielaborazione, il server di Data Workbench ricostruisce il set di dati come specificato nei file Elaborazione registro e Configurazione set di dati di trasformazione.
title: Informazioni sulla rielaborazione e la ritrasformazione
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# Informazioni sulla rielaborazione e la ritrasformazione{#understanding-reprocessing-and-retransformation}

Durante la rielaborazione, il server di Data Workbench ricostruisce il set di dati come specificato nei file Elaborazione registro e Configurazione set di dati di trasformazione.

A tal fine, il server di Data Workbench (InsightServer64.exe) deve completare sia la fase di elaborazione del registro che la fase di trasformazione della costruzione del set di dati. Al termine dell’elaborazione del registro, la trasformazione viene attivata automaticamente, ma può anche verificarsi indipendentemente dall’elaborazione del registro.

Durante la fase di elaborazione del registro, gli utenti di Data Workbench non hanno accesso ai dati nel set di dati. Durante la fase di trasformazione, gli utenti di Data Workbench hanno accesso ai dati aggiornati, ma i dati vengono campionati invece che completati. L’analisi dei dati può continuare durante la trasformazione, ma le query verranno completate solo con la stessa rapidità con cui si verifica la trasformazione.

## Rielaborazione {#section-92f1e46bf1534b3dba39e9493190b8ab}

Ogni volta che si completa una delle seguenti attività, l&#39;elaborazione del registro e quindi la trasformazione, si verifica automaticamente per ricostruire il set di dati come specificato nei file di configurazione del set di dati:

* Aggiungi una nuova origine dati.
* Aggiungi un nuovo server di Data Workbench al cluster nel file [!DNL Profile.cfg] .
* Modifica il file [!DNL Cluster.cfg].
* Modifica il file [!DNL Log Processing.cfg] o un file [!DNL Log Processing Dataset Include], incluso ma non limitato a quanto segue:

   * Aggiungi un nuovo parametro
   * Modificare una trasformazione
   * Modificare i parametri Ora di inizio o Ora di fine

* Aggiorna il file [!DNL Insight Server.exe].

È inoltre possibile avviare la rielaborazione in qualsiasi momento immettendo qualsiasi carattere o combinazione di caratteri nel parametro Reprocess del file [!DNL Log Processing.cfg] e salvando il file.

>[!NOTE]
>
>Per eseguire la rielaborazione, il parametro Pause nel file [!DNL Log Processing Mode.cfg] deve essere impostato su false. Il valore predefinito di questo parametro è false, pertanto la modifica del parametro potrebbe non essere necessaria. Per ulteriori informazioni su [!DNL Log Processing Mode.cfg], consulta [File di configurazione aggiuntivi](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## Ritrasformazione {#section-02446744549940ada8eba0573ec5575f}

Ogni volta che si modificano informazioni nel file [!DNL Transformation.cfg] o in un file [!DNL Transformation Dataset Include], ad esempio se si modifica una trasformazione o si definisce una nuova dimensione, la trasformazione viene eseguita automaticamente.

Ogni volta che si modificano i file di ricerca a cui si fa riferimento nel file [!DNL Transformation.cfg] o in un file [!DNL Transformation Dataset Include] (inclusi i file di ricerca per le trasformazioni [!DNL Categorize], [!DNL FlatFileLookup] e [!DNL ODBCLookup]), è necessario avviare la trasformazione immettendo qualsiasi carattere o combinazione di caratteri nel parametro Reprocess del file [!DNL Transformation.cfg] e salvando il file.
