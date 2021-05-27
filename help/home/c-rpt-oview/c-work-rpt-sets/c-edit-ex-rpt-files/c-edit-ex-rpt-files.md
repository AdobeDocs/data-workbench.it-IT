---
description: Passaggi per modificare i file Report.cfg esistenti utilizzando Worktop o un editor di testo.
title: Modifica dei file Report.cfg esistenti
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
exl-id: 69038c0c-bb01-4e61-aad6-1be0bdec8a6d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 2%

---

# Modifica dei file Report.cfg esistenti{#editing-existing-report-cfg-files}

Passaggi per modificare i file Report.cfg esistenti utilizzando Worktop o un editor di testo.

>[!NOTE]
>
>* Devi lavorare online per modificare i file [!DNL Report.cfg]. Per lavorare in linea, fai clic con il pulsante destro del mouse sulla barra del titolo e fai clic su **[!UICONTROL Work Online]**.[!DNL Worktop]
   >
   >
* Se il parametro **[!UICONTROL Allow Report Regeneration]** nel file [!DNL Report.cfg] è impostato su [!DNL True], quando apporti modifiche a tale file e lo salvi nuovamente sul server, [!DNL Report] rigenera automaticamente i rapporti in quel set. Anche se rigenera i rapporti, non li invia nuovamente via e-mail. Per i passaggi necessari, consulta [Invio di rapporti per e-mail](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607).

>



Puoi modificare un elemento [!DNL Report.cfg] esistente dal [!DNL Worktop] o utilizzando un editor di testo.

La modifica di un file [!DNL Report.cfg] utilizzando la scheda [!DNL Reports] di [!DNL Worktop] consente di modificare solo i parametri, i vettori e gli elementi vettoriali già presenti nel file. Se devi aggiungere un parametro o un vettore al file, devi modificarlo utilizzando un editor di testo, ad esempio Blocco note.

* [Per modificare un rapporto.cfg esistente utilizzando il Worktop](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [Per modificare un Report.cfg esistente utilizzando un editor di testo](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## Per modificare un rapporto.cfg esistente utilizzando Worktop {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>Devi lavorare online per modificare il [!DNL Report.cfg] da [!DNL Worktop].

1. All’interno di Data Workbench, nella scheda [!DNL Reports] , seleziona la sottocartella (scheda o sottodirectory a discesa) per il set di rapporti che desideri configurare.
1. Fai clic su **[!UICONTROL Report.cfg]**. Vengono visualizzati i parametri del [!DNL Report.cfg] per questo set di rapporti.

1. Modifica i parametri di configurazione come desiderato. Per informazioni su questi parametri, consulta [Parametri Report.cfg](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Salva il file facendo clic con il pulsante destro del mouse su **[!UICONTROL Report.cfg (modified)]** nella parte superiore dei parametri e facendo clic su **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.

## Per modificare un Report.cfg esistente utilizzando un editor di testo {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. Apri il [!DNL Reports Manager] facendo clic con il pulsante destro del mouse all&#39;interno di un&#39;area di lavoro e facendo clic su **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**.

1. Fai clic sulla cartella del set di rapporti.
1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Report.cfg] per il set di rapporti e fai clic su **[!UICONTROL Make Local]**.

1. Nella colonna [!DNL User], fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Report.cfg] per il set di rapporti e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Viene aperto il file [!DNL Report.cfg] .

   L&#39;esempio [!DNL Report.cfg] mostrato in [Configura il set di rapporti](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) contiene per impostazione predefinita solo i parametri inclusi nel file [!DNL Report.cfg]. L&#39;esempio seguente include tutti i parametri disponibili per il file [!DNL Report.cfg] che puoi utilizzare come modelli per le voci dei parametri:

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

1. Modifica i parametri di configurazione come desiderato. Per informazioni su questi parametri, consulta [Parametri Report.cfg](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Salva e chiudi il file.
1. In [!DNL Reports Manager], fai clic con il pulsante destro del mouse sul segno di spunta nella colonna [!DNL User] del file [!DNL Report.cfg] e seleziona **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]***.
