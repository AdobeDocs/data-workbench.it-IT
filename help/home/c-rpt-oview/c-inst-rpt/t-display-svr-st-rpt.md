---
description: L’interfaccia di Stato dettagliata di Data Workbench è utile per la risoluzione dei problemi relativi a errori o altri problemi con i computer Data Workbench Server e Report Server che sono client di Data Workbench Server.
title: Visualizzazione dello stato del server di rapporto
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# Visualizzazione dello stato del server di rapporto{#displaying-report-server-status}

L’interfaccia di Stato dettagliata di Data Workbench è utile per la risoluzione dei problemi relativi a errori o altri problemi con i computer Data Workbench Server e Report Server che sono client di Data Workbench Server.

Per visualizzare lo stato del rapporto nell’interfaccia [!DNL Master Server Detailed Status], è necessario aggiungere un server di stato del rapporto al vettore [!DNL Servers] nel file [!DNL Communications.cfg] del server di Data Workbench. La procedura seguente descrive come aggiungere il server di stato del report al file [!DNL Communications.cfg] :

Per ulteriori informazioni sulle interfacce [!DNL Detailed Status], vedere il capitolo relativo alle interfacce amministrative della *Guida utente Data Workbench*.

**Per aggiungere una[!DNL Report Status Server]**

1. Passare alla cartella Componenti nella directory in cui è stato installato il server di Data Workbench (InsightServer64.exe).

   Esempio: [!DNL C:\Adobe\Server\Components]
1. Apri [!DNL Communications.cfg] in un editor di testo come Blocco note.
1. Individua il vettore [!DNL Servers] e aggiungi il server di stato del report a questo vettore come evidenziato nel seguente frammento di file.

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

1. Aggiorna il conteggio degli elementi per il vettore [!DNL Servers] (ovvero, incrementa il valore degli elementi di uno) come evidenziato nel frammento di file nel passaggio precedente.
1. Salvate il file.
