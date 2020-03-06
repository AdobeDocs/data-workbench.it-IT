---
description: Durante la rielaborazione, il server workbench dati ricostruisce il dataset come specificato nei file di configurazione del set di dati Elaborazione log e Trasformazione.
solution: Analytics
title: Informazioni sulla rielaborazione e la ritrasformazione
topic: Data workbench
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Informazioni sulla rielaborazione e la ritrasformazione{#understanding-reprocessing-and-retransformation}

Durante la rielaborazione, il server workbench dati ricostruisce il dataset come specificato nei file di configurazione del set di dati Elaborazione log e Trasformazione.

A tal fine, il server workbench dati (InsightServer64.exe) deve completare sia la fase di elaborazione del log che la fase di trasformazione della costruzione del dataset. Al termine dell&#39;elaborazione del registro, la trasformazione viene attivata automaticamente, ma anche indipendentemente dall&#39;elaborazione del registro.

Durante la fase di elaborazione del registro, gli utenti del workbench dati non hanno accesso ai dati nel dataset. Durante la fase di trasformazione, gli utenti del workbench dati hanno accesso ai dati aggiornati, ma i dati vengono campionati invece di essere completati. L&#39;analisi dei dati può continuare durante la trasformazione, ma le query verranno completate solo con la stessa rapidità con cui si verifica la trasformazione.

## Rielaborazione {#section-92f1e46bf1534b3dba39e9493190b8ab}

Ogni volta che si completa una delle seguenti attività, l&#39;elaborazione del registro e quindi la trasformazione, si verifica automaticamente per ricostruire il dataset come specificato nei file di configurazione del dataset:

* Aggiungi una nuova origine dati.
* Aggiungere un nuovo server workbench dati al cluster nel [!DNL Profile.cfg] file.
* Modificate il [!DNL Cluster.cfg] file.
* Modificate il [!DNL Log Processing.cfg] file o un [!DNL Log Processing Dataset Include] file, includendo, tra l’altro, quanto segue:

   * Aggiungere un nuovo parametro
   * Modificare una trasformazione
   * Modificare i parametri Ora di inizio o Ora di fine

* Aggiornate il [!DNL Insight Server.exe] file.

È inoltre possibile avviare la rielaborazione in qualsiasi momento immettendo qualsiasi carattere o combinazione di caratteri nel parametro Rielabora del [!DNL Log Processing.cfg] file e salvando il file.

>[!NOTE]
>
>Per eseguire nuovamente l&#39;elaborazione, il parametro Pausa nel [!DNL Log Processing Mode.cfg] file deve essere impostato su false. Il valore predefinito di questo parametro è false, pertanto la modifica del parametro potrebbe non essere necessaria. Per ulteriori informazioni su [!DNL Log Processing Mode.cfg], consultate [File](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md)di configurazione aggiuntivi.

## Retransformazioni {#section-02446744549940ada8eba0573ec5575f}

Ogni volta che modificate le informazioni nel [!DNL Transformation.cfg] file o in un [!DNL Transformation Dataset Include] file, ad esempio modificate una trasformazione o definite una nuova dimensione, la trasformazione viene eseguita automaticamente.

Ogni volta che modificate i file di ricerca a cui viene fatto riferimento nel [!DNL Transformation.cfg] file o in un [!DNL Transformation Dataset Include] file (inclusi i file di ricerca per [!DNL Categorize], [!DNL FlatFileLookup]e [!DNL ODBCLookup] le trasformazioni), dovete avviare la trasformazione immettendo qualsiasi carattere o combinazione di caratteri nel parametro Rielabora del [!DNL Transformation.cfg] file e salvando il file.
