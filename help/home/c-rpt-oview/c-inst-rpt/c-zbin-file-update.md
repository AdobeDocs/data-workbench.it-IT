---
description: Per tutte le lingue, Report Server 6.0 e versioni successive richiede il file "insight.zbin" copiato nella cartella principale del server di rapporto.
title: Aggiorna il server di rapporto con un file della lingua (file .zbin)
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
exl-id: a76b7c01-83f0-4cf2-97a9-07d51cc75b3c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 9%

---

# Aggiorna il server di rapporto con un file della lingua (file .zbin){#update-report-server-with-a-language-file-zbin-file}

{{eol}}

Per tutte le lingue, Report Server 6.0 e versioni successive richiede il file &quot;insight.zbin&quot; copiato nella cartella principale del server di rapporto.

Aggiornare i file della lingua del server di rapporto:

1. Aggiungi il file &quot;insight.zbin&quot; rinominato alla directory principale ReportServer.
1. Il file di configurazione del server di rapporto (reportserver.cfg) richiede le impostazioni dei font per le lingue a doppio byte. Ad esempio, il cinese richiede l’aggiunta di font utilizzando SimSun:

   ```
   <b>Report Server.cfg - Add Fonts</b> 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. Un parametro per Report Server 6.0 deve essere trasmesso nella riga di comando per la localizzazione, ad esempio:

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Se non viene specificata alcuna impostazione internazionale, il valore predefinito del server di rapporto è Inglese.

   Segui i passaggi per avviare ReportServer come servizio con i parametri internazionali:

   1. Avviare un prompt dei comandi come amministratore.
   1. Passare alla cartella di installazione di ReportServer.
   1. Digita il seguente comando per avviare il servizio:

      * Per inglese: [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * Per cinese: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. Per verificare se ReportServer è in esecuzione con i parametri corretti:

   1. Apri Gestione servizi Windows.
   1. Fai clic con il pulsante destro del mouse [!DNL Adobe Insight Report Server - Properties].

   Il percorso dell&#39;eseguibile conterrà i parametri seguenti:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```
