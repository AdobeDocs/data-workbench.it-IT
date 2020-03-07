---
description: L'interfaccia Stato dettagliato nel workbench dati è utile per la risoluzione di errori o altri problemi relativi ai computer server Workbench dati e server report che sono client di Workbench dati Server.
solution: Analytics
title: Visualizzazione dello stato del server di report
topic: Data workbench
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualizzazione dello stato del server di report{#displaying-report-server-status}

L&#39;interfaccia Stato dettagliato nel workbench dati è utile per la risoluzione di errori o altri problemi relativi ai computer server Workbench dati e server report che sono client di Workbench dati Server.

Per visualizzare lo stato del report nell&#39; [!DNL Master Server Detailed Status] interfaccia, devi aggiungere un server di stato del report al [!DNL Servers] vettore nel [!DNL Communications.cfg] file del server workbench dati. La procedura seguente descrive come aggiungere il server di stato del report al [!DNL Communications.cfg] file:

Per ulteriori informazioni sulle [!DNL Detailed Status] interfacce, vedere il capitolo relativo alle interfacce amministrative della Guida *utente di Workbench* dati.

**Per aggiungere un[!DNL Report Status Server]**

1. Passare alla cartella Components (Componenti) nella directory in cui è stato installato il server workbench dati (InsightServer64.exe).

   Esempio: [!DNL C:\Adobe\Server\Components]
1. Aprite [!DNL Communications.cfg] in un editor di testo come Blocco note.
1. Individuare il [!DNL Servers] vettore e aggiungere il server di stato del report a questo vettore, come evidenziato nel seguente frammento di file.

   ```
    . . .
   Servers = vector: 17 items
       0 = FileServer: 
         Local Path = string: Audit\\
         URI = string: /Audit
       1 = FileServer: 
         Local Path = string: Bin\\
         URI = string: /Bin
       2 = FileServer: 
         Local Path = string: Components\\
         URI = string: /Components
     . . .
       16 = ReportStatusServer: 
         URI = string: /ReportStatus.vsp
   ```

1. Aggiorna il conteggio degli elementi per il vettore (ovvero, incrementa il valore degli elementi di uno), come evidenziato nel frammento di file nel passaggio precedente. [!DNL Servers]
1. Salvate il file.
