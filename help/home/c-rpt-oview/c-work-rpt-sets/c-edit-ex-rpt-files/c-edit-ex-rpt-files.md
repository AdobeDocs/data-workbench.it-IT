---
description: Passaggi per modificare i file Report.cfg esistenti utilizzando Worktop o un editor di testo.
solution: Analytics
title: Modifica dei file Report.cfg esistenti
topic: Data workbench
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modifica dei file Report.cfg esistenti{#editing-existing-report-cfg-files}

Passaggi per modificare i file Report.cfg esistenti utilizzando Worktop o un editor di testo.

>[!NOTE]
>
>* Per modificare [!DNL Report.cfg] i file dovete lavorare online. Per lavorare online, fate clic con il pulsante destro del mouse sulla barra del titolo [!DNL Worktop]e fate clic su **[!UICONTROL Work Online]**.
   >
   >
* Se il **[!UICONTROL Allow Report Regeneration]** parametro nel [!DNL Report.cfg] file è impostato su [!DNL True], quando apportate modifiche a tale file e lo salvate nuovamente nel server, [!DNL Report] vengono automaticamente rigenerati i rapporti in quel set. Anche se rigenera i rapporti, non invia nuovamente i rapporti via e-mail. Per i passaggi necessari, consulta [Invio di report per e-mail](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607).
>



È possibile modificare un elemento esistente [!DNL Report.cfg] dall&#39;editor di testo [!DNL Worktop] o utilizzando un editor di testo.

La modifica di un [!DNL Report.cfg] file mediante la [!DNL Reports] scheda del file [!DNL Worktop] consente di modificare solo i parametri, i vettori e gli elementi vettoriali già presenti nel file. Per aggiungere al file un parametro o un vettore, è necessario modificarlo utilizzando un editor di testo, come Blocco note.

* [Per modificare un report.cfg esistente utilizzando il worktop](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [Per modificare un report.cfg esistente utilizzando un editor di testo](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## Per modificare un report.cfg esistente utilizzando il worktop {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>È necessario lavorare online per modificare il [!DNL Report.cfg] da [!DNL Worktop].

1. Nel workbench dati, nella [!DNL Reports] scheda, selezionare la sottocartella (scheda o sottodirectory a discesa) per il set di report che si desidera configurare.
1. Fai clic su **[!UICONTROL Report.cfg]** (Fine). Vengono visualizzati i parametri del set di report [!DNL Report.cfg] per il set.

1. Modificate i parametri di configurazione come desiderate. Per informazioni su questi parametri, consultate Parametri [](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.
1. Salvate il file facendo clic con il pulsante destro del mouse **[!UICONTROL Report.cfg (modified)]** nella parte superiore dei parametri e facendo clic su **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.

## Per modificare un report.cfg esistente utilizzando un editor di testo {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. Per aprire l’area di lavoro, fate [!DNL Reports Manager] clic con il pulsante destro del mouse e fate clic su **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**.

1. Fate clic sulla cartella del set di rapporti.
1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al [!DNL Report.cfg] set di rapporti e quindi scegliere **[!UICONTROL Make Local]**.

1. Nella [!DNL User] colonna, fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Report.cfg] per il set di rapporti e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Si apre il [!DNL Report.cfg] file.

   L’esempio [!DNL Report.cfg] mostrato in [Configura set](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) di report contiene solo i parametri inclusi nel [!DNL Report.cfg] file per impostazione predefinita. L&#39;esempio seguente include tutti i parametri disponibili per il [!DNL Report.cfg] file che potete utilizzare come modelli per le voci dei parametri:

   ```
   Attachments = vector: 1 items
     0 = Attachment:
       FileName = string: c:\\myimage.jpg
       Content Type = string: image/jpeg
   Alert Threshold = int: 0
   Allow Report Regeneration = bool: true
   Color Set = int: 1
   Command To Execute = string: 
   Default Excel Template = string: 
   Dimension Name = string: 
   Email Only If Perfect = bool: false
   End Date = string: 
   Every = string: month
   Excel Watchdog Timeout (seconds) = double: 300.0
   Filter Formula = string: 
   Gamma Correction = double: 1
   Hide Logos = bool: false
   Lookup File = string: 
   Mail Report = MailReport: 
     Body XSL Template = string: 
     Recipients = vector: 0 items
     SMTP Server = SmtpServerInfo: 
       Address = string: 
       Password = string: 
       User = string: 
     Sender Address = string: 
     Sender Name = string: 
     Subject = string: 
   Notification Only = bool: false
   Output Root = string: 
   Report Types = vector: 3 items
     0 = string: thumbnail
     1 = string: png
     2 = string: excel
   Start Date = string: 7/1/06 19:16 EDT
   Thumbnail X = int: 240
   Thumbnail Y = int: 180
   Top N Metric = string: 
   Top N Value = int: 0
   Use Local Sample Only = bool: false
   Workspace Path = string: 
   ```

1. Modificate i parametri di configurazione come desiderate. Per informazioni su questi parametri, consultate Parametri [](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.
1. Salvate e chiudete il file.
1. Fare clic con il pulsante destro del [!DNL Reports Manager]mouse sul segno di spunta nella [!DNL User] colonna del [!DNL Report.cfg] file e selezionare **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.

