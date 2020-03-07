---
description: Passaggi per mappare il portale dei report su una directory virtuale (IIS 6.0).
solution: Analytics
title: Mappatura del portale di report su una directory virtuale (IIS 6.0)
topic: Data workbench
uuid: e09d23d7-09de-4180-8260-60527f47aa98
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mappatura del portale di report su una directory virtuale (IIS 6.0){#mapping-report-portal-to-a-virtual-directory-iis}

Passaggi per mappare il portale dei report su una directory virtuale (IIS 6.0).

Il mapping [!DNL Report Portal] a una directory virtuale in IIS 6.0 comporta tre attività separate:

1. [Modificare il file di configurazione](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [Importare il file di configurazione in IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [Abilitare ASP (Active Server Pages) in IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

È necessario completare tutte e tre le attività.

## To Edit the Configuration File {#section-eaf1c58935074cfa840dac33e1286520}

1. Nel computer in cui [!DNL Report Portal] è installato, aprite \*PortalName*\ReportPortalSetup.xml in un editor di testo come Blocco note.

1. Utilizzate la funzione di ricerca e sostituzione dell’editor per sostituire globalmente (Replace All) la stringa &quot;VSVirtualPortalName&quot; con il nome del portale. Ad esempio, se desiderate utilizzare &quot;VisualReportPortal&quot; come nome del vostro [!DNL Report Portal], cercate &quot;VSVirtualPortalName&quot; e sostituitelo con &quot;VisualReportPortal&quot;.
1. Individuate il seguente elemento in questo file:

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. Impostate l&#39;attributo di questo elemento [!DNL Path] sulla posizione fisica della directory in cui [!DNL Report Server] salva l&#39;output per i set di report.

   La cartella di output può trovarsi ovunque, può avere un nome qualsiasi e contiene una sottocartella per ciascun set di rapporti.

   >[!NOTE]
   >
   >Deve essere la stessa directory specificata nel parametro Radice di output del [!DNL Report.cfg] file per un set di report. Per ulteriori informazioni, consulta [Configurazione dei file](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d)Report.cfg.

   L’esempio di codice seguente mostra come impostare l’ [!DNL Path] attributo se i rapporti sono stati salvati in [!DNL E:\VSReport\ReportOutput]:

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >È fondamentale che l&#39; [!DNL Path] attributo sia impostato correttamente.

1. Se avete modificato il valore predefinito [!DNL Path] dell&#39; [!DNL Output] elemento, spostate il [!DNL profiles.xml] file da *\PortalName*\PortalFiles\Output folder to the output directory that you specified in Step 4. Nell&#39;esempio precedente, passereste [!DNL profiles.xml] a [!DNL E:\VSReport\ReportOutput].

1. Verificate che gli [!DNL Path] attributi di tutti gli altri [!DNL IIsWebVirtualDir] elementi siano mappati sulla posizione corretta cercando tutte le istanze di [!DNL C:\Inetpub\wwwroot] e sostituendo ciascuna con il percorso corretto.

1. Salvate il file. Se desiderate conservare il file originale, potete salvare il file di configurazione con un nuovo nome.

## Importazione del file di configurazione in IIS {#section-9d61f6bfa93846dcb96973fec5573b19}

1. Nel computer in cui [!DNL Report Portal] è installato, avviate Gestione IIS utilizzando **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Systems (IIS) Manager]**.

1. Seleziona **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Fare clic con il pulsante destro del mouse **[!UICONTROL Default Web Site]** e selezionare **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]** (da file).

1. Selezionate il **[!UICONTROL ReportPortalSetup.xml]** file e fate clic su **[!UICONTROL Read File]**.

1. Verificate che siano elencate sei directory virtuali [!DNL Report Portal] come illustrato nell&#39;esempio seguente.

   ![](assets/rptPort_dia_VirDirs.png)

   Se non vengono visualizzate sei directory virtuali o se viene visualizzato un messaggio di errore, fare clic su **[!UICONTROL Cancel]** e verificare la presenza di errori nel file di configurazione.

1. Selezionate la prima directory virtuale nell’elenco (quella che è l’elemento padre degli altri cinque) e fate clic **[!UICONTROL OK]**. IIS importa i mapping e aggiunge le directory virtuali al sito Web predefinito.

   Verificate che la struttura di directory risultante contenga una cartella principale (con lo stesso nome del portale) e cinque sottodirectory come illustrato nell&#39;esempio seguente.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Fare clic su ciascuna directory virtuale per verificare che IIS sia in grado di individuare la directory fisica che rappresenta. Se IIS visualizza un errore, fare clic con il pulsante destro del mouse sul nome della directory virtuale e verificare che il [!DNL Local Path] campo punti alla directory fisica corretta.

## Abilitazione delle pagine ASP (Active Server Pages) in IIS {#section-a7725ec2afc64ffc854c5bd8c5c31802}

Per utilizzare [!DNL Report Portal], gli ASP devono essere abilitati in IIS. Per impostazione predefinita, gli ASP sono disabilitati quando è installato IIS 6.0. Utilizzare la procedura seguente per verificare che gli ASP siano abilitati in IIS.

1. Nella finestra Gestione IIS, selezionare **[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]**.
1. Verificate che l&#39; [!DNL Active Server Pages] estensione sia impostata su [!DNL Allowed].

   ![](assets/report_aspenable.png)

1. Se il relativo Stato è proibito, selezionatelo **[!UICONTROL Active Server Pages]** e fate clic su **[!UICONTROL Allow]**.
1. Chiudere Gestione IIS.

