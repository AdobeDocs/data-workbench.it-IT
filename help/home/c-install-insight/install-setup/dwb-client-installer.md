---
description: Workbench dati fornisce una procedura guidata per l'installazione dell'applicazione workstation (client).
title: Procedura guidata di impostazione della workstation
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Procedura guidata di impostazione della workstation{#workstation-setup-wizard}

Workbench dati fornisce una procedura guidata per l&#39;installazione dell&#39;applicazione workstation (client).

## Installazione della workstation mediante la procedura guidata di installazione {#section-58da9bb6196c46eab3b54146913fdcb8}

Avviate l&#39;eseguibile della procedura guidata di installazione e seguite ogni passaggio per installare il programma client della workstation. Dopo l&#39;installazione della workstation, è possibile connettersi a server e profili.

1. Fare doppio clic sul programma di installazione della workstation eseguibile.
1. Fare clic su **Sì** per consentire l&#39;installazione del programma in Windows.
1. Selezionare una **lingua** per la procedura guidata di impostazione.

   Viene aperta la procedura guidata:

   ![](assets/6_4_workstation_wizard.png)

1. Fare clic su **Avanti** nella finestra di dialogo **Benvenuti nella procedura guidata** di impostazione Workbench dati.

1. Selezionare per installare una **nuova installazione** o per **aggiornare o ripristinare** un&#39;installazione esistente.

   **La nuova installazione** sovrascrive tutti i file installati in precedenza.

   **L&#39;aggiornamento** consente di aggiornare Workstation alla versione più recente o di ripristinare un&#39;installazione esistente. Workbench dati confronterà i file **Insight.exe** installati ed eseguirà l&#39;Installazione guidata Workstation se è disponibile una versione più recente del client.

1. Selezionate il percorso di installazione:

   **In genere** viene installato in una cartella e in un percorso predefiniti.

   * I file di programma vengono salvati per impostazione predefinita in:

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * I file di dati (profili, certificati, registri di traccia e file utente) vengono salvati per impostazione predefinita in:

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >Inizialmente verrà installato un file ***Insight.cfg*** generico senza i dettagli del server. È consigliabile utilizzare il file ***Insight.cfg*** appena installato e personalizzarlo invece di spostare un file da un&#39;installazione precedente. Poiché il percorso di installazione della workstation è cambiato, si consiglia di aggiungere font, rimuovere la cartella ** utente e rimuovere il *TraceFileComponent *.

1. (facoltativo) Selezionate** Personalizzato** per scegliere il pacchetto lingua e la posizione del programma e dei file di dati.
1. Selezionate la posizione delle **scelte rapide nel menu** Start.

   ![](assets/6_4_workstation_wizard_folder.png)

   Fare clic su **Non creare una cartella** del menu Start per non installare un collegamento nel menu Start di Windows.

1. Fai clic su **Successivo.** Verrà visualizzato un riepilogo dei percorsi e delle lingue di percorso del file selezionati. Fai clic su **Installa.**

1. Individuare il certificato **Workbench** dati.

   Se durante l&#39;installazione non è possibile trovare il certificato di Workbench dati, verrà aperta una finestra di dialogo per individuare il percorso del certificato (un file **.pem** che si trova per impostazione predefinita nella cartella **Certificati** client), oppure fare clic su **Ignora** per trovare il certificato dopo l&#39;installazione.

   Fate clic su **Installa** dopo aver individuato il certificato.

1. Al termine della configurazione guidata e dopo l&#39;installazione di Workbench dati, fare clic su **Fine** per completare la configurazione.

   >[!NOTE]
   >
   >Il percorso di registro predefinito per la procedura guidata di configurazione della workstation è disponibile all&#39;indirizzo **[!DNL C:\Users\`<userName>`\AppData\Local\Temp.]**

   Selezionare la casella di controllo **Avvia applicazione** per aprire il workbench dopo l&#39;impostazione.

1. **Configurare le connessioni** ai server nel **[!DNL Insight.cfg]** file.

   Dopo l&#39;installazione della workstation, l&#39;area di lavoro Enhanced Workstation Configuration Experience si aprirà con informazioni aggiuntive sull&#39; [immissione delle informazioni](/help/home/c-get-started/c-insght-config-param.md) di connessione del server nel file *Insight.cfg* e un&#39;opzione per selezionare un profilo dall&#39;elenco a discesa. È inoltre possibile visualizzare lo stato della connessione sui server.

   ![](assets/6_4_workstation_install_conf_conn.png)

## Cartelle di installazione {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

La struttura delle cartelle di Workbench dati presenta due posizioni di installazione:

* **File** del programma Il file **Insight.exe** e i file client di supporto (**Insight.ini**) ora si trovano per impostazione predefinita in

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* La cartella **Appdata** .

   **Insight.cfg**, profili, certificati, registri di traccia e file utente ora si trovano per impostazione predefinita in

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   Puoi impostare il percorso della cartella **Appdata** nel `Insight.ini` file:

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## Disinstallazione della workstation {#section-5ce2e233fe4348469ef1b3c451dd5b70}

Workbench dati ora include un eseguibile per disinstallare la workstation (che per impostazione predefinita si trova in **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**).

Avviare e seguire i passaggi per rimuovere i file Workbench dati Workstation dal disco rigido.

>[!NOTE]
>
>È possibile avviare il file **unins000.exe** eseguibile dalla cartella, utilizzando la scelta rapida **Disinstalla Workbench** dati dal menu Start o da **[!UICONTROL Control Panel]** > **[!UICONTROL Program and Features]**.
