---
description: Se si utilizzano le trasformazioni Categorize o FlatFileLookup, la tabella di ricerca viene caricata in memoria e compilata da un file semplice la cui posizione viene specificata al momento della definizione della trasformazione.
solution: Analytics
title: Compilazione della tabella di ricerca
topic: Data workbench
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Compilazione della tabella di ricerca{#populating-the-lookup-table}

Se si utilizzano le trasformazioni Categorize o FlatFileLookup, la tabella di ricerca viene caricata in memoria e compilata da un file semplice la cui posizione viene specificata al momento della definizione della trasformazione.

Il file semplice specificato deve soddisfare i seguenti requisiti:

* Ogni riga del file deve rappresentare una riga nella tabella di ricerca.
* Le colonne nel file devono essere separate da un delimitatore ASCII. È possibile utilizzare qualsiasi carattere che non sia un carattere di fine riga e che non venga visualizzato in alcun punto all&#39;interno dei dati dell&#39;evento stesso. Quando definite la trasformazione, specificate il carattere utilizzato per delimitare le colonne nel file semplice.

Se si utilizza una [!DNL ODBCLookup] trasformazione, la tabella di ricerca viene caricata in memoria e compilata da una tabella o una vista in un [!DNL ODBC] database specificato dall&#39;utente. Quando si definisce la trasformazione, è inoltre necessario specificare l&#39;origine dati, il nome utente e la password che il server workbench dati deve utilizzare per stabilire una connessione al database.

>[!NOTE]
>
>Le tabelle di ricerca vengono caricate quando il server workbench dati inizia inizialmente a creare il dataset. Una volta stabiliti, i file di ricerca non devono essere modificati. Se si modifica il file o la [!DNL ODBC] tabella flat utilizzato per la fase di trasformazione, è necessario trasformare nuovamente l&#39;intero set di dati. Se si modifica un file semplice utilizzato durante la fase di elaborazione del registro, i nuovi dati di ricerca vengono applicati a tutti i nuovi record che entrano nel set di dati, ma le modifiche non vengono applicate retroattivamente.

