---
description: Informazioni sull'aggiornamento e la disinstallazione del software del server di rapporto.
title: Aggiornamento e disinstallazione del server di rapporto
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 2%

---

# Aggiornamento e disinstallazione del server di rapporto{#upgrading-and-uninstalling-report-server}

Informazioni sull&#39;aggiornamento e la disinstallazione del software del server di rapporto.

* [Aggiornamento del rapporto](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Disinstallazione del rapporto](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Aggiornamento del server di rapporto {#section-95fea4bddad74616a8aea450dcdb2282}

Se stai eseguendo l&#39;aggiornamento a [!DNL Report Server] 5.4, puoi utilizzare le istruzioni per aggiornare il software [!DNL Report Server]. Se utilizzi [!DNL Report Server] 3.6 o versioni precedenti, contatta Adobe per assistenza sull&#39;aggiornamento.

Per aggiornare [!DNL Report Server] 5.4, utilizza Data Workbench per copiare un file di aggiornamento nel server di Data Workbench a cui [!DNL Report Server] si connette. In seguito, le istanze [!DNL Report] Server si aggiornano automaticamente quando si connettono a tale server e caricano un profilo.

>[!NOTE]
>
>Prima di eseguire l’aggiornamento di [!DNL Report Server], assicurati di aver aggiornato correttamente il software del server di Data Workbench e i profili in esecuzione sul server di Data Workbench. Per ulteriori informazioni, contattare Adobe Consulting Services.

Per eseguire la procedura seguente, è innanzitutto necessario ottenere il file di aggiornamento per [!DNL Report Server].

**Per eseguire l’aggiornamento alla versione  [!DNL Report Server] 5.4 e successive**

1. Esegui un backup di tutti i file sotto [!DNL E:\Portal] e rimuovi tutti i file e le cartelle all&#39;interno di questa directory.
1. Copia il contenuto della nuova build in [!DNL E:\Portal].
1. Modifica [!DNL global.asa], [!DNL email.asp] e [!DNL TopNavigation.xml] come indicato nelle istruzioni della sezione precedente.

1. Copia il [!DNL users.mdb] dal backup.

   >[!NOTE]
   >
   >Se in precedenza non hai generato report con output .png, devi accedere alle singole cartelle di report e modificare il [!DNL reports.xml] per includere un formato di report di png. In caso contrario, potresti ricevere un errore 500. Il tuo originale [!DNL reports.xml] avrà un aspetto simile al seguente:

   ```
      <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

   È necessario modificarlo nel modo seguente:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
    <REPORT format="png">
    <NAME>Dashboard</NAME>
     <PATH>Dashboard.png</PATH>
     <WEB_PATH>Dashboard.png</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

1. In [!DNL report.cfg], includi un formato di output di png e salva. In futuro, dovrebbe generare report in formato png.

**Per effettuare l’aggiornamento alla versione  [!DNL Report Server] 4.0**

1. Nel computer di Data Workbench, copia il file di aggiornamento del server di rapporto nella cartella [!DNL Temp\Software] nella directory in cui è installato Data Workbench.
1. Avvia Data Workbench e carica il profilo [!DNL Configuration] .
1. Fai clic sulla miniatura **[!UICONTROL Configure Connection to Servers]**.
1. In [!DNL Servers Manager], fai clic con il pulsante destro del mouse sull’icona del server di Data Workbench e fai clic su **[!UICONTROL Server Files]**.

1. Nella cartella Software, apri la cartella [!DNL Report Server] .
1. Fai clic con il pulsante destro del mouse sul segno di spunta **[!UICONTROL Temp]** per [!DNL ReportServer.exe] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Disinstallazione del server di rapporto {#section-96eb3281c45a45c0a7065deaa6845c25}

**Per disinstallare[!DNL Report Server]**

1. Annulla la registrazione del servizio [!DNL Report Windows].

   1. Aprire un prompt dei comandi e passare alla sottodirectory bin nella cartella in cui è stato installato il server di Data Workbench (InsightServer64.exe.) Esempio: [!DNL D:\Adobe\Report\bin]
   1. Al prompt dei comandi, eseguire il comando seguente per arrestarlo e annullarne la registrazione come servizio in Microsoft Windows: [!DNL visualreport /unregserver]

1. Elimina la directory di installazione del server di rapporto.
