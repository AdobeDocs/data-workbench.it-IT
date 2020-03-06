---
description: Prima di poter generare rapporti e avvisi, è necessario configurare il server di report per specificare l'indirizzo del server di Insight e identificare i profili con cui si desidera eseguire il rapporto.
solution: Analytics
title: Configurazione della connessione al server di Insight
topic: Data workbench
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurazione della connessione al server di Insight{#configuring-the-connection-to-the-insight-server}

Prima di poter generare rapporti e avvisi, è necessario configurare il server di report per specificare l&#39;indirizzo del server di Insight e identificare i profili con cui si desidera eseguire il rapporto.

>[!NOTE]
>
>Fino a quando non configurate il server di report come descritto di seguito, non potete eseguire correttamente il server di report. Se si tenta di eseguire Report Server con il file non configurato installato con il programma, Report Server genera un flusso di errori.

**Per configurare il server di report**

1. Con Esplora risorse, andate alla directory in cui avete installato Report Server.
1. Aprite il [!DNL ReportServer.cfg] file in Blocco note e modificate il file come desiderate.

   L&#39;esempio seguente [!DNL Report Server.cfg] contiene solo i parametri inclusi nel [!DNL Report Server.cfg] file per impostazione predefinita (evidenziando le impostazioni dei parametri richieste). Se contattate Adobe License Server tramite un server proxy, dovete aggiungere il vettore Licensing e i relativi parametri. Per una descrizione dettagliata, consulta Parametri [di](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) Report Server.cfg.

   ```
   Fonts = vector: 0 items
   Gamma = float: 1.6
   Network Location = string: NetworkLocationName
   Servers = vector: 1 items
     0 = serverInfo:
       Address = string: ServerIPAddress
       Name = string: 
       Port = int: 443
       Proxy Address = string:
       Proxy Password = string:
       Proxy Port = int: 8080
       Proxy User Name = string:
       SSL Client Certificate = string: ReportCertFileName.pem
       SSL Server Common Name = string: ServerCommonName
       Use SSL = bool: true
   Result Memory Limit (KB) = double: 100000
   Maximum Slice Size = int: 30
   Use OpenGL Hardware Rendering = bool: true
   Reporting = :
     Profiles = vector: 1 items
       0 = ReportProfile:
         Server = string: ServerCommonName
         Profile = string: ProfileName
     Update Interval (minutes) = int: 10
     Completion Message Interval (seconds) = int: 600
     Status interval (seconds) = int: 600
     SMTP Server for Errors = string: SMTPServerHostName
     SMTP Server for Errors Username = string: SMTPServerUsername
     SMTP Server for Errors Password = string: SMTPServerPassword
     SMTP Server for Errors Send From = string: SenderAddress
     SMTP Server for Errors Send To = string: RecipientAddresses
   ```

1. Salvate e chiudete il file.
