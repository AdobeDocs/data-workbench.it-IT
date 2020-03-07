---
description: Per tutte le lingue, Report Server 6.0 e versioni successive richiede il file "insight.zbin" copiato nella cartella principale del server di report.
solution: Analytics
title: Aggiorna server di report con un file della lingua (file .zbin)
topic: Data workbench
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aggiorna server di report con un file della lingua (file .zbin){#update-report-server-with-a-language-file-zbin-file}

Per tutte le lingue, Report Server 6.0 e versioni successive richiede il file &quot;insight.zbin&quot; copiato nella cartella principale del server di report.

Aggiornare i file della lingua del server di report:

1. Aggiungete il file &quot;insight.zbin&quot; rinominato nella directory principale di ReportServer.
1. Il file di configurazione del server di report (reportserver.cfg) richiede impostazioni di font per le lingue a doppio byte. Ad esempio, il cinese richiede l&#39;aggiunta di font utilizzando SimSun:

   ```
   <b>Report Server.cfg - Add Fonts</b> 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. È necessario passare un parametro per Report Server 6.0 nella riga di comando per la localizzazione, ad esempio:

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Se non viene specificata alcuna lingua, il server di report predefinito è Inglese.

   Seguite i passaggi per avviare ReportServer come servizio con i parametri delle impostazioni internazionali:

   1. Avviate un prompt dei comandi come amministratore.
   1. Andate alla cartella di installazione di ReportServer.
   1. Digitate il comando seguente per avviare il servizio:

      * Per inglese: [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * Per cinese: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. Per verificare se ReportServer è in esecuzione con i parametri corretti:

   1. Aprire Windows Service Manager.
   1. Right-click [!DNL Adobe Insight Report Server - Properties].
   Il percorso dell&#39;eseguibile conterrà i parametri:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

