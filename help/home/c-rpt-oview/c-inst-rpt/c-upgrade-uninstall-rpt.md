---
description: Informazioni sull'aggiornamento e la disinstallazione del software del server di rapporto.
title: Aggiornamento e disinstallazione del server di rapporto
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 2%

---

# Aggiornamento e disinstallazione del server di rapporto{#upgrading-and-uninstalling-report-server}

{{eol}}

Informazioni sull&#39;aggiornamento e la disinstallazione del software del server di rapporto.

* [Aggiornamento del rapporto](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Disinstallazione del rapporto](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Aggiornamento del server di rapporto {#section-95fea4bddad74616a8aea450dcdb2282}

Se esegui l’aggiornamento a [!DNL Report Server] 5.4, puoi utilizzare le istruzioni per aggiornare il tuo [!DNL Report Server] software. Se utilizzi [!DNL Report Server] 3.6 o versioni precedenti, contatta l&#39;Adobe per assistenza sull&#39;aggiornamento.

Per aggiornare [!DNL Report Server] 5.4, utilizza Data Workbench per copiare un file di aggiornamento nel server di Data Workbench a cui [!DNL Report Server] si connette. In seguito, [!DNL Report] Le istanze del server si aggiornano automaticamente quando si connettono a tale server e caricano un profilo.

>[!NOTE]
>
>Prima dell&#39;aggiornamento [!DNL Report Server], assicurati di aver aggiornato correttamente il software del server di Data Workbench e i profili in esecuzione sul server di Data Workbench. Per ulteriori informazioni, contattare Adobe Consulting Services.

Per eseguire la procedura seguente, è innanzitutto necessario ottenere il file di aggiornamento per [!DNL Report Server].

**Per effettuare l’aggiornamento a [!DNL Report Server] 5.4 e versioni successive**

1. Esegui un backup di tutti i file in [!DNL E:\Portal] e rimuovere tutti i file e le cartelle presenti in questa directory.
1. Copia il contenuto della nuova build in [!DNL E:\Portal].
1. Modifica [!DNL global.asa], [!DNL email.asp]e [!DNL TopNavigation.xml] come indicato nelle istruzioni della sezione precedente.

1. Copia il [!DNL users.mdb] dal backup.

   >[!NOTE]
   >
   >Se in precedenza non hai generato rapporti con un output .png, devi accedere alle singole cartelle di report e modificare il [!DNL reports.xml] per includere un formato di report di png. In caso contrario, potresti ricevere un errore 500. Il tuo originale [!DNL reports.xml] avrà un aspetto simile al seguente:

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

**Per effettuare l’aggiornamento a [!DNL Report Server] 4,0**

1. Nel computer di Data Workbench, copia il file di aggiornamento del server di rapporto in [!DNL Temp\Software] nella directory in cui è installato Data Workbench.
1. Avvia Data Workbench e carica il [!DNL Configuration] profilo.
1. Fai clic sul pulsante **[!UICONTROL Configure Connection to Servers]** miniatura.
1. In [!DNL Servers Manager], fai clic con il pulsante destro del mouse sull’icona del server di Data Workbench e fai clic su **[!UICONTROL Server Files]**.

1. Nella cartella Software, apri la [!DNL Report Server] cartella.
1. Fai clic con il pulsante destro del mouse sul pulsante **[!UICONTROL Temp]** segno di spunta [!DNL ReportServer.exe] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Disinstallazione del server di rapporto {#section-96eb3281c45a45c0a7065deaa6845c25}

**Per disinstallare[!DNL Report Server]**

1. Annulla la registrazione [!DNL Report Windows] servizio.

   1. Aprire un prompt dei comandi e passare alla sottodirectory bin nella cartella in cui è stato installato il server di Data Workbench (InsightServer64.exe.) Esempio: [!DNL D:\Adobe\Report\bin]
   1. Al prompt dei comandi, esegui il seguente comando per arrestarlo e annullarne la registrazione come servizio in Microsoft Windows: [!DNL visualreport /unregserver]

1. Elimina la directory di installazione del server di rapporto.
