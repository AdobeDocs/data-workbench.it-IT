---
description: Prima di poter generare rapporti e avvisi, è necessario configurare Report Server per specificare l’indirizzo di Insight Server e identificare i profili sui quali si desidera creare rapporti.
title: Configurazione della connessione a Insight Server
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
exl-id: a398a665-fe09-448a-977c-b0f9de4add09
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---

# Configurazione della connessione a Insight Server{#configuring-the-connection-to-the-insight-server}

Prima di poter generare rapporti e avvisi, è necessario configurare Report Server per specificare l’indirizzo di Insight Server e identificare i profili sui quali si desidera creare rapporti.

>[!NOTE]
>
>Finché non si configura il server di rapporto come descritto di seguito, non è possibile eseguire correttamente il server di rapporto. Se si tenta di eseguire Report Server con il file non configurato installato con il programma, Report Server genera un flusso di errori.

**Per configurare il server di rapporto**

1. Con Esplora risorse, passare alla directory in cui è stato installato Report Server.
1. Apri il file [!DNL ReportServer.cfg] in Blocco note e modifica il file come desiderato.

   L&#39;esempio seguente [!DNL Report Server.cfg] contiene solo i parametri inclusi nel file [!DNL Report Server.cfg] per impostazione predefinita (ed evidenzia le impostazioni dei parametri richieste). Se si contatta il server licenze Adobe tramite un server proxy, è necessario aggiungere il vettore Licensing e i relativi parametri. Per una descrizione dettagliata, consulta [Parametri server.cfg del rapporto](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) .

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

1. Salva e chiudi il file.
