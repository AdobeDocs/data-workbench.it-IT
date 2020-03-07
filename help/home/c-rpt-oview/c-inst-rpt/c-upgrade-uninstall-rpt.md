---
description: Informazioni sull'aggiornamento e la disinstallazione del software del server di report.
solution: Analytics
title: Aggiornamento e disinstallazione del server di report
topic: Data workbench
uuid: 42f0d190-1a88-424d-be4b-90338144d287
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aggiornamento e disinstallazione del server di report{#upgrading-and-uninstalling-report-server}

Informazioni sull&#39;aggiornamento e la disinstallazione del software del server di report.

* [Aggiornamento del rapporto](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Disinstallazione del rapporto](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Aggiornamento del server di report {#section-95fea4bddad74616a8aea450dcdb2282}

Se si sta effettuando l&#39;aggiornamento alla versione [!DNL Report Server] 5.4, è possibile utilizzare le istruzioni per aggiornare il [!DNL Report Server] software. Se utilizzi la versione [!DNL Report Server] 3.6 o precedente, contatta Adobe per assistenza sull’aggiornamento.

Per aggiornare [!DNL Report Server] 5.4, utilizzare workbench dati per copiare un file di aggiornamento nel server workbench dati a cui [!DNL Report Server] si connette. In questo modo, le istanze [!DNL Report] Server si aggiornano automaticamente quando si connettono a tale server e caricano un profilo.

>[!NOTE]
>
>Prima di eseguire l&#39;aggiornamento [!DNL Report Server], accertarsi di aver aggiornato correttamente il software del server workbench dati e i profili in esecuzione sul server workbench dati. Per ulteriori informazioni, contattate i servizi di consulenza Adobe.

Per eseguire la procedura seguente, è innanzitutto necessario ottenere il file di aggiornamento per [!DNL Report Server].

**Per effettuare l&#39;aggiornamento alla versione[!DNL Report Server]5.4 e versioni successive**

1. Eseguire un backup di tutti i file in [!DNL E:\Portal] e rimuovere tutti i file e le cartelle in questa directory.
1. Copiate i contenuti della nuova build in [!DNL E:\Portal].
1. Modificate [!DNL global.asa], [!DNL email.asp]e [!DNL TopNavigation.xml] in base alle istruzioni della sezione precedente.

1. Copiare il [!DNL users.mdb] backup.

   >[!NOTE]
   >
   >Se in precedenza non venivano generati rapporti con un output .png, era necessario entrare nelle singole cartelle dei rapporti e modificarli [!DNL reports.xml] per includere un formato di rapporto di png. In caso contrario, potrebbe verificarsi un errore 500. L’originale [!DNL reports.xml] avrà un aspetto simile al seguente:

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

   Dovrebbe essere modificato come segue:

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

1. In [!DNL report.cfg], includete un formato di output di png e salvate. In futuro, dovrebbe generare report in formato png.

**Per effettuare l&#39;aggiornamento alla versione[!DNL Report Server]4.0**

1. Nel computer del workbench dati, copiare il file di aggiornamento del server di report nella [!DNL Temp\Software] cartella nella directory in cui è installato il workbench dati.
1. Avviare il workbench dati e caricare il [!DNL Configuration] profilo.
1. Fate clic sulla **[!UICONTROL Configure Connection to Servers]** miniatura.
1. Fare clic con il pulsante destro del [!DNL Servers Manager]mouse sull&#39;icona del server workbench dati e fare clic su **[!UICONTROL Server Files]**.

1. Nella cartella Software, aprire la [!DNL Report Server] cartella.
1. Fare clic con il pulsante destro del mouse sul **[!UICONTROL Temp]** segno di spunta [!DNL ReportServer.exe] e selezionare **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Disinstallazione del server di report {#section-96eb3281c45a45c0a7065deaa6845c25}

**Per disinstallare[!DNL Report Server]**

1. Annullate la registrazione del [!DNL Report Windows] servizio.

   1. Aprire un prompt dei comandi e passare alla sottodirectory bin nella cartella in cui è installato il server workbench dati (InsightServer64.exe). Esempio: [!DNL D:\Adobe\Report\bin]
   1. Al prompt dei comandi, eseguite il comando seguente per arrestarlo e annullarne la registrazione come servizio in Microsoft Windows: [!DNL visualreport /unregserver]

1. Eliminate la directory di installazione del server di report.

