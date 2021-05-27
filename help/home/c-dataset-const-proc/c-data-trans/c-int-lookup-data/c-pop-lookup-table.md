---
description: Se si utilizzano le trasformazioni Categorize o FlatFileLookup, la tabella di ricerca viene caricata in memoria e compilata da un file flat la cui posizione si specifica quando si definisce la trasformazione.
title: Compilazione della tabella di ricerca
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
exl-id: e83d9feb-44fe-4fa1-b559-e1f5606637b5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 2%

---

# Compilazione della tabella di ricerca{#populating-the-lookup-table}

Se si utilizzano le trasformazioni Categorize o FlatFileLookup, la tabella di ricerca viene caricata in memoria e compilata da un file flat la cui posizione si specifica quando si definisce la trasformazione.

Il file flat specificato deve soddisfare i seguenti requisiti:

* Ogni riga del file deve rappresentare una riga nella tabella di ricerca.
* Le colonne del file devono essere separate da un delimitatore ASCII. È possibile utilizzare qualsiasi carattere che non sia un carattere di fine riga e non sia visualizzato in alcun punto all’interno dei dati dell’evento stesso. Quando si definisce la trasformazione, specificare il carattere utilizzato per delimitare le colonne nel file flat.

Se utilizzi una trasformazione [!DNL ODBCLookup], la tabella di ricerca viene caricata in memoria e compilata da una tabella o una visualizzazione in un database [!DNL ODBC] specificato dall&#39;utente. Quando si definisce la trasformazione, è inoltre necessario specificare l’origine dati, il nome utente e la password che il server di Data Workbench deve utilizzare per stabilire una connessione al database.

>[!NOTE]
>
>Le tabelle di ricerca vengono caricate quando il server di Data Workbench inizia inizialmente a costruire il set di dati. Una volta stabiliti, i file di ricerca non devono essere modificati. Se modifichi il file flat o la tabella [!DNL ODBC] utilizzata per la fase di trasformazione, devi trasformare nuovamente l’intero set di dati. Se si modifica un file flat utilizzato durante la fase di elaborazione del registro, i nuovi dati di ricerca vengono applicati a tutti i nuovi record che entrano nel set di dati, ma le modifiche non vengono applicate retroattivamente.
