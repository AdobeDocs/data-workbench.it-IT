---
description: Passaggi per mappare il portale dei report su una directory virtuale (IIS 5.0).
solution: Analytics
title: Mappatura del portale di report su una directory virtuale (IIS 5.0)
topic: Data workbench
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mappatura del portale di report su una directory virtuale (IIS 5.0){#mapping-report-portal-to-a-virtual-directory-iis}

Passaggi per mappare il portale dei report su una directory virtuale (IIS 5.0).

1. Nel computer in cui [!DNL Report Portal] è installato, avviare Gestione IIS utilizzando **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]** o **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**.

1. Seleziona **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Fare clic con il pulsante destro del mouse **[!UICONTROL Default Web Site]** e selezionare **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Quando [!DNL Virtual Directory Wizard] si apre, fate clic su **[!UICONTROL Next]**.

1. Completare i seguenti passaggi per definire la directory virtuale principale per [!DNL Report Portal]:

   1. Quando viene richiesto un alias, digitare il nome del [!DNL Report Portal], quindi fare clic **[!UICONTROL Next]**. Ad esempio, se desiderate utilizzare &quot;Portal&quot; come nome del vostro [!DNL Report Portal], assegnate l’alias &quot;Portal&quot; alla directory virtuale. Al termine fai clic su **[!UICONTROL Next]** (Continua).

   1. Quando viene richiesto il percorso fisico, individuare e selezionare la *&lt;**[!UICONTROL PortalName]**>* **[!UICONTROL \PortalASP]** directory, quindi fare clic **[!UICONTROL Next]**.

      Esempio: [!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. Quando viene richiesta l&#39;autorizzazione, verificate che le seguenti opzioni siano abilitate:

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. Fai clic su **[!UICONTROL Next]**, quindi su **[!UICONTROL Finish]**. La directory virtuale creata viene visualizzata sotto il sito Web predefinito come illustrato nell&#39;esempio seguente.
   ![](assets/RptPort_scrn_VirDirManual.png)

1. Fare clic con il pulsante destro del mouse sulla directory virtuale appena creata e selezionare **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Utilizzare la [!DNL Virtual Directory] procedura guidata per creare un alias per ciascuna delle seguenti directory fisiche. In questo modo si crea una directory virtuale con il nome appropriato per ciascuna di queste risorse fisiche.

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Crea questo alias. . . </th> 
   <th colname="col2" class="entry"> Per questa risorsa fisica. . . </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Core </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Core </p> <p>Esempio: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CSS </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\CSS </p> <p>Esempio: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\CSS</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> HTC </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\HTC </p> <p>Esempio: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\HTC</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Immagini </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Images </p> <p>Esempio: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uscita </td> 
   <td colname="col2"> <p>Posizione fisica della directory in cui <span class="keyword"> Report Server</span> salva l'output per i set di report. La cartella di output può trovarsi ovunque, può avere un nome qualsiasi e contiene una sottocartella per ciascun set di rapporti. </p> <p>Deve essere la stessa directory specificata nel parametro radice di output del file <span class="filepath"> Report.cfg</span> per un set di report. Per ulteriori informazioni, consulta <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> Configurazione dei file</a>Report.cfg. </p> <p>Il percorso predefinito è \<i>PortalName</i>\PortalFiles\Output. </p> <p>Esempio: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p>Il file <i>PortalName</i>\PortalFiles\Output directory contains the <span class="filepath"> profile.xml</span> , che deve essere spostato nella directory di output specificata per questo alias. </p> <p>È fondamentale che l'attributo <span class="wintitle"> Path</span> sia impostato correttamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Al termine, verificate che IIS visualizzi sei nuove directory virtuali. Accertatevi che la struttura di directory contenga una cartella principale (con lo stesso nome del portale) e cinque sottocartelle, come illustrato di seguito.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Al termine, andate a [Modifica del file](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7) di configurazione della sessione per continuare con il processo di installazione.

