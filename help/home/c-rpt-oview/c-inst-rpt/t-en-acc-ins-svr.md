---
description: Per connettersi a un server workbench dati, il server di report deve disporre dell'autorizzazione per accedere a tale server.
solution: Analytics
title: Abilitazione dell'accesso al server Workbench dati
topic: Data workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Abilitazione dell&#39;accesso al server Workbench dati{#enabling-access-to-the-data-workbench-server}

Per connettersi a un server workbench dati, il server di report deve disporre dell&#39;autorizzazione per accedere a tale server.

È possibile concedere l&#39;accesso a un server workbench dati aggiungendo al file di controllo dell&#39;accesso del server il nome comune del server di report (assegnato nel certificato digitale del server di report).

>[!NOTE]
>
>Quando lavori in un ambiente cluster, Report Server deve essere configurato per accedere al server Workbench dati master per evitare problemi di sincronizzazione. Nel workbench dati è possibile visualizzare informazioni sui server di elaborazione nel cluster utilizzando la voce di [!DNL Related Servers] menu presente nel [!DNL Servers Manager]. Per ulteriori informazioni sull&#39; [!DNL Servers Manager]argomento, vedere il capitolo Interfaccia amministrativa della Guida *utente di Workbench* dati.

La procedura seguente descrive come aggiungere manualmente Report Server al file di controllo dell&#39;accesso in un server Workbench dati. Per aggiornare il file di controllo di accesso in questo modo, è necessario avere accesso al file system nel computer in cui è installato il server workbench dati.

È inoltre possibile aggiornare il file di controllo dell&#39;accesso del server utilizzando il workbench dati [!DNL Server Files Manager] in. A tal fine, il client workbench dati deve disporre di privilegi amministrativi sul server.

Per ulteriori informazioni sull&#39; [!DNL Server Files Manager]argomento, vedere il capitolo Interfaccia amministrativa della Guida *utente di Workbench* dati.

**Per configurare l&#39;accesso a un server workbench dati**

1. Passare alla cartella Controllo accesso nella directory in cui è stato installato il server Workbench dati (InsightServer64.exe).

   Esempio: [!DNL C:\Adobe\Server\Access Control]

1. Aprite [!DNL Access Control.cfg] in un editor di testo come Blocco note.
1. Individuare [!DNL Report Server AccessGroup] e aggiungere un nome [!DNL Report Server’s] comune a questo gruppo come evidenziato nel seguente frammento di file. (Digitate il nome comune esattamente come appare sul certificato [!DNL Report Server’s] digitale.)

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
