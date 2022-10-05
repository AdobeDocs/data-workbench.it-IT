---
description: Passaggi per mappare il Report Portal (Portale dei rapporti) in una directory virtuale (IIS 6.0).
title: Mappatura del Report Portal (Portale dei rapporti) su una directory virtuale (IIS 6.0)
uuid: e09d23d7-09de-4180-8260-60527f47aa98
exl-id: 39335705-7391-49af-a63d-c0fe4ca3f8f0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 3%

---

# Mappatura del Report Portal (Portale dei rapporti) su una directory virtuale (IIS 6.0){#mapping-report-portal-to-a-virtual-directory-iis}

{{eol}}

Passaggi per mappare il Report Portal (Portale dei rapporti) in una directory virtuale (IIS 6.0).

Mappatura della [!DNL Report Portal] in una directory virtuale in IIS 6.0 sono previste tre attività separate:

1. [Modificare il file di configurazione](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [Importare il file di configurazione in IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [Abilitare le pagine ASP (Active Server Pages) in IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

Devi completare tutte e tre le attività.

## Per modificare il file di configurazione {#section-eaf1c58935074cfa840dac33e1286520}

1. Sulla macchina dove [!DNL Report Portal] è installato, aprire \*PortalName*\ReportPortalSetup.xml in un editor di testo come Blocco note.

1. Utilizza la funzione trova e sostituisci dell’editor per sostituire globalmente (Sostituisci tutto) la stringa &quot;VSVirtualPortalName&quot; con il nome del portale. Ad esempio, se desideri utilizzare &quot;VisualReportPortal&quot; come nome del tuo [!DNL Report Portal], cerca &quot;VSVirtualPortalName&quot; e lo sostituisci con &quot;VisualReportPortal&quot;.
1. Individua il seguente elemento in questo file:

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. Imposta l’elemento [!DNL Path] alla posizione fisica della directory in cui [!DNL Report Server] salva l&#39;output per i set di rapporti.

   La cartella di output può trovarsi ovunque, può essere denominata qualsiasi cosa e contiene una sottocartella per ogni set di rapporti.

   >[!NOTE]
   >
   >Deve essere la stessa directory specificata nel parametro Output Root nel [!DNL Report.cfg] file per un set di rapporti. Per ulteriori informazioni, consulta [Configurazione dei file Report.cfg](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d).

   L&#39;esempio di codice seguente mostra come impostare il [!DNL Path] se i rapporti sono stati salvati in [!DNL E:\VSReport\ReportOutput]:

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >È fondamentale che il [!DNL Path] attributo impostato correttamente.

1. Se hai modificato il valore predefinito [!DNL Path] del [!DNL Output] elemento, sposta [!DNL profiles.xml] dal *\PortalName*\PortalFiles\Output nella directory di output specificata al passaggio 4. Nell’esempio precedente, ti muovi [!DNL profiles.xml] a [!DNL E:\VSReport\ReportOutput].

1. Verifica che [!DNL Path] attributi per tutti gli altri [!DNL IIsWebVirtualDir] gli elementi vengono mappati nella posizione corretta ricercando tutte le istanze di [!DNL C:\Inetpub\wwwroot] e sostituirli con il percorso corretto.

1. Salvate il file. Se si desidera conservare il file originale, è possibile salvare il file di configurazione utilizzando un nuovo nome.

## Importazione del file di configurazione in IIS {#section-9d61f6bfa93846dcb96973fec5573b19}

1. Sulla macchina dove [!DNL Report Portal] è installato, avviare IIS Manager utilizzando **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Systems (IIS) Manager]**.

1. Seleziona **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Fai clic con il pulsante destro del mouse **[!UICONTROL Default Web Site]** e seleziona **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]** (dal file).

1. Seleziona la **[!UICONTROL ReportPortalSetup.xml]** e fai clic su **[!UICONTROL Read File]**.

1. Verifica che siano elencate sei directory virtuali per [!DNL Report Portal] come illustrato nell’esempio seguente.

   ![](assets/rptPort_dia_VirDirs.png)

   Se non vengono visualizzate sei directory virtuali o se viene visualizzato un messaggio di errore, fare clic su **[!UICONTROL Cancel]** ed esamina il file di configurazione per verificare la presenza di errori.

1. Selezionare la prima directory virtuale nell&#39;elenco (quella padre delle altre cinque directory) e fare clic su **[!UICONTROL OK]**. IIS importa le mappature e aggiunge le directory virtuali al sito Web predefinito.

   Assicurati che la struttura di directory risultante abbia una cartella principale (con lo stesso nome del portale) e cinque sottodirectory come mostrato nell’esempio seguente.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Fare clic su ciascuna directory virtuale per assicurarsi che IIS sia in grado di individuare la directory fisica che rappresenta. Se IIS visualizza un errore, fare clic con il pulsante destro del mouse sul nome della directory virtuale e verificare che il [!DNL Local Path] il campo punta alla directory fisica corretta.

## Per abilitare le pagine ASP (Active Server Pages) in IIS {#section-a7725ec2afc64ffc854c5bd8c5c31802}

Per utilizzare [!DNL Report Portal], gli ASP devono essere abilitati in IIS. (Per impostazione predefinita, gli ASP sono disabilitati quando è installato IIS 6.0.) Per verificare che gli ASP siano abilitati in IIS, attenersi alla procedura descritta di seguito.

1. Nella finestra Gestione IIS, selezionare **[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]**.
1. Verifica che [!DNL Active Server Pages] l&#39;estensione è impostata su [!DNL Allowed].

   ![](assets/report_aspenable.png)

1. Se lo stato è proibito, selezionare **[!UICONTROL Active Server Pages]** e fai clic su **[!UICONTROL Allow]**.
1. Chiudere IIS Manager.
