---
description: L’interfaccia di Stato dettagliata di Data Workbench è utile per la risoluzione dei problemi relativi a errori o altri problemi con i computer Data Workbench Server e Report Server che sono client di Data Workbench Server.
title: Visualizzazione dello stato del server di rapporto
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# Visualizzazione dello stato del server di rapporto{#displaying-report-server-status}

{{eol}}

L’interfaccia di Stato dettagliata di Data Workbench è utile per la risoluzione dei problemi relativi a errori o altri problemi con i computer Data Workbench Server e Report Server che sono client di Data Workbench Server.

Per visualizzare lo stato del rapporto nel [!DNL Master Server Detailed Status] , è necessario aggiungere un server di stato del report al [!DNL Servers] vettoriale nel server di Data Workbench [!DNL Communications.cfg] file. La procedura seguente descrive come aggiungere il server di stato del report al [!DNL Communications.cfg] file:

Per ulteriori informazioni [!DNL Detailed Status] interfacce, vedere il capitolo Interfaccia amministrativa *Guida utente di Data Workbench*.

**Per aggiungere una[!DNL Report Status Server]**

1. Passare alla cartella Componenti nella directory in cui è stato installato il server di Data Workbench (InsightServer64.exe).

   Esempio: [!DNL C:\Adobe\Server\Components]
1. Apri [!DNL Communications.cfg] in un editor di testo come Blocco note.
1. Individua il [!DNL Servers] e aggiungi il server di stato del report a questo vettore, come evidenziato nel seguente frammento di file.

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

1. Aggiorna il conteggio degli elementi per il [!DNL Servers] vettore (ovvero, incrementa il valore degli elementi di uno) come evidenziato nel frammento di file nel passaggio precedente.
1. Salvate il file.
