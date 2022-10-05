---
description: Durante la rielaborazione, il server di Data Workbench ricostruisce il set di dati come specificato nei file Elaborazione registro e Configurazione set di dati di trasformazione.
title: Informazioni sulla rielaborazione e la ritrasformazione
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# Informazioni sulla rielaborazione e la ritrasformazione{#understanding-reprocessing-and-retransformation}

{{eol}}

Durante la rielaborazione, il server di Data Workbench ricostruisce il set di dati come specificato nei file Elaborazione registro e Configurazione set di dati di trasformazione.

A tal fine, il server di Data Workbench (InsightServer64.exe) deve completare sia la fase di elaborazione del registro che la fase di trasformazione della costruzione del set di dati. Al termine dell’elaborazione del registro, la trasformazione viene attivata automaticamente, ma può anche verificarsi indipendentemente dall’elaborazione del registro.

Durante la fase di elaborazione del registro, gli utenti di Data Workbench non hanno accesso ai dati nel set di dati. Durante la fase di trasformazione, gli utenti di Data Workbench hanno accesso ai dati aggiornati, ma i dati vengono campionati invece che completati. L’analisi dei dati può continuare durante la trasformazione, ma le query verranno completate solo con la stessa rapidità con cui si verifica la trasformazione.

## Rielaborazione {#section-92f1e46bf1534b3dba39e9493190b8ab}

Ogni volta che si completa una delle seguenti attività, l&#39;elaborazione del registro e quindi la trasformazione, si verifica automaticamente per ricostruire il set di dati come specificato nei file di configurazione del set di dati:

* Aggiungi una nuova origine dati.
* Aggiungi un nuovo server di Data Workbench al cluster nel [!DNL Profile.cfg] file.
* Modificare la [!DNL Cluster.cfg] file.
* Modificare la [!DNL Log Processing.cfg] file o [!DNL Log Processing Dataset Include] , compresi, tra l’altro, i seguenti elementi:

   * Aggiungi un nuovo parametro
   * Modificare una trasformazione
   * Modificare i parametri Ora di inizio o Ora di fine

* Aggiorna [!DNL Insight Server.exe] file.

È inoltre possibile avviare la rielaborazione in qualsiasi momento immettendo qualsiasi carattere o combinazione di caratteri nel parametro Reprocess del [!DNL Log Processing.cfg] e salvare il file.

>[!NOTE]
>
>Per eseguire la rielaborazione, il parametro Pause nel [!DNL Log Processing Mode.cfg] il file deve essere impostato su false. Il valore predefinito di questo parametro è false, pertanto la modifica del parametro potrebbe non essere necessaria. Per ulteriori informazioni [!DNL Log Processing Mode.cfg], vedi [File di configurazione aggiuntivi](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## Ritrasformazione {#section-02446744549940ada8eba0573ec5575f}

Ogni volta che si modificano le informazioni nel [!DNL Transformation.cfg] o in un [!DNL Transformation Dataset Include] file, ad esempio la modifica di una trasformazione o la definizione di una nuova dimensione, la trasformazione avviene automaticamente.

Ogni volta che si modificano i file di ricerca a cui si fa riferimento nel [!DNL Transformation.cfg] o in un [!DNL Transformation Dataset Include] file (inclusi i file di ricerca per [!DNL Categorize], [!DNL FlatFileLookup]e [!DNL ODBCLookup] trasformazioni), è necessario avviare la trasformazione inserendo qualsiasi carattere o combinazione di caratteri nel parametro Reprocess del [!DNL Transformation.cfg] e salvare il file.
