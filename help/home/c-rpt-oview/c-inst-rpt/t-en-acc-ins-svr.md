---
description: Per connettersi a un server di Data Workbench, il server di rapporto deve disporre delle autorizzazioni necessarie per accedere a tale server.
title: Abilitazione dell’accesso al server di Data Workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
exl-id: bf409413-470e-4e05-9bd2-b5b511bbe4a5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%

---

# Abilitazione dell’accesso al server di Data Workbench{#enabling-access-to-the-data-workbench-server}

Per connettersi a un server di Data Workbench, il server di rapporto deve disporre delle autorizzazioni necessarie per accedere a tale server.

Per concedere l’accesso a un server di Data Workbench, aggiungi al file di controllo accessi del server il nome comune del server di rapporto (assegnato sul certificato digitale del server di rapporto).

>[!NOTE]
>
>Quando si lavora in un ambiente cluster, Report Server deve essere configurato per accedere al server di Data Workbench principale per evitare problemi di sincronizzazione. All’interno di Data Workbench è possibile visualizzare informazioni sui server di elaborazione nel cluster utilizzando la voce di menu [!DNL Related Servers] in [!DNL Servers Manager]. Per ulteriori informazioni su [!DNL Servers Manager], vedere il capitolo relativo alle interfacce amministrative della *Guida utente alla Data Workbench*.

La procedura seguente descrive come aggiungere manualmente Report Server al file di controllo accessi su un server di Data Workbench. Per aggiornare il file di controllo di accesso in questo modo, è necessario disporre dell’accesso al file system nel computer in cui è installato il server di Data Workbench.

Puoi anche aggiornare il file di controllo degli accessi del server utilizzando [!DNL Server Files Manager] in Data Workbench. A questo scopo, il client di Data Workbench deve disporre di privilegi amministrativi sul server.

Per ulteriori informazioni su [!DNL Server Files Manager], vedere il capitolo relativo alle interfacce amministrative della *Guida utente alla Data Workbench*.

**Per configurare l’accesso a un server di Data Workbench**

1. Passare alla cartella Controllo accesso nella directory in cui è stato installato il server di Data Workbench (InsightServer64.exe).

   Esempio: [!DNL C:\Adobe\Server\Access Control]

1. Apri [!DNL Access Control.cfg] in un editor di testo come Blocco note.
1. Individua il [!DNL Report Server AccessGroup] e aggiungi [!DNL Report Server’s] nome comune a questo gruppo, come evidenziato nel seguente frammento di file. (Digita il nome comune esattamente come appare nel certificato digitale [!DNL Report Server’s].)

   ```
   . . .
     5 = AccessGroup: 
       Members = vector: 1 items
         0 = string: CN: ReportCommonName
       Name = string: Report Server
       Read-Only Access = vector: 5 items
         0 = string: /Profiles/$
         1 = string: /Status/
         3 = string: /Software/
         4 = string: /Addresses/
         5 = string: /Users/$
       Read-Write Access = vector: 3 items
         0 = string: /Profiles/
         1 = string: /Users/%CN%/
         2 = string: /ReportStatus.vsp
      . . .
   ```

1. Salvate il file.
