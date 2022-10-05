---
description: Data Workbench fornisce una procedura guidata di configurazione per installare l’applicazione della workstation (client).
title: Configurazione guidata della workstation
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
exl-id: bfd9f2ad-282a-4be8-9f66-53e045648ef1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 1%

---

# Configurazione guidata della workstation{#workstation-setup-wizard}

{{eol}}

Data Workbench fornisce una procedura guidata di configurazione per installare l’applicazione della workstation (client).

## Installazione della workstation mediante la procedura guidata di installazione {#section-58da9bb6196c46eab3b54146913fdcb8}

Avvia l&#39;eseguibile della procedura guidata di installazione e passa attraverso ogni passaggio per installare il programma client della workstation. Dopo l’installazione della workstation, puoi connetterti a server e profili.

1. Fare doppio clic sull&#39;eseguibile del programma di installazione della workstation.
1. Fai clic su **Sì** per consentire l&#39;installazione del programma su Windows.
1. Seleziona una **Lingua** per la configurazione guidata.

   Verrà aperta la procedura guidata:

   ![](assets/6_4_workstation_wizard.png)

1. Fai clic su **Successivo** sulla **Installazione guidata Data Workbench** finestra di dialogo.

1. Selezionare per installare un **Nuova installazione** o **Aggiornamento o riparazione** un&#39;installazione esistente.

   **Nuova installazione** sovrascrive tutti i file installati in precedenza.

   **Aggiornamento** aggiorna la workstation all’ultima versione o consente di ripristinare un’installazione esistente. Data Workbench confronterà installato **Insight.exe** ed eseguire la procedura guidata di installazione della workstation se è disponibile una versione più recente del client.

1. Selezionare il percorso di installazione:

   **Tipico** viene installato in una cartella e in un percorso predefiniti.

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
      >Un generico ***Insight.cfg*** il file senza i dettagli del server verrà installato inizialmente. Si consiglia di utilizzare la nuova installazione ***Insight.cfg*** e personalizzarlo invece di spostare un file da un&#39;installazione precedente. Poiché il percorso di installazione della workstation è cambiato, l&#39;aggiunta di font, la rimozione di *Cartella utente* e si consiglia di rimuovere il *TraceFileComponent *.

1. (facoltativo) Seleziona **Personalizzato** per scegliere il pacchetto linguistico e il percorso del programma e dei file di dati.
1. Selezionare la posizione per **tasti di scelta rapida nel menu Start**.

   ![](assets/6_4_workstation_wizard_folder.png)

   Fai clic su **Non creare una cartella Menu Start** per non installare un collegamento nel menu Start di Windows.

1. Fai clic su **Avanti.** Verrà visualizzato un riepilogo dei percorsi e delle lingue di percorso dei file selezionati. Fai clic su **Installa.**

1. Individua il **Data Workbench certificato**.

   Se la procedura guidata di installazione non è in grado di trovare il certificato di Data Workbench durante l&#39;installazione, verrà aperta una finestra di dialogo per individuare il percorso del certificato (un **.pem** il file si trova per impostazione predefinita nel client **Certificati** oppure fai clic su **Salta** per trovare il certificato dopo l&#39;installazione.

   Fai clic su **Installa** dopo aver individuato il certificato.

1. Al termine della procedura guidata di installazione e dopo aver Data Workbench l&#39;installazione, fai clic su **Fine** per completare la configurazione.

   >[!NOTE]
   >
   >Percorso di registro predefinito per la procedura guidata di configurazione della workstation in  `C:\Users\<userName>\AppData\Local\Temp`.

   Seleziona la **Applicazione Launch** per aprire workbench dopo l’impostazione.

1. **Configurare le connessioni** a server in **[!DNL Insight.cfg]** file.

   Dopo l&#39;installazione della workstation, si aprirà l&#39;area di lavoro Enhanced Workstation Configuration Experience con ulteriori informazioni su [immissione delle informazioni sulla connessione al server](/help/home/c-get-started/c-insght-config-param.md) in *Insight.cfg* e un’opzione per selezionare un profilo dall’elenco a discesa. È inoltre possibile visualizzare lo stato della connessione ai server.

   ![](assets/6_4_workstation_install_conf_conn.png)

## Cartelle di installazione {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

La struttura delle cartelle Data Workbench dispone di due posizioni di installazione:

* **File di programma** La **Insight.exe** e il supporto dei file client (**Insight.ini**) ora si trova per impostazione predefinita in

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* La **Appdata** cartella.

   **Insight.cfg**, profili, certificati, registri di traccia e file utente ora si trovano per impostazione predefinita in

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   Puoi impostare il percorso per **Appdata** nella cartella `Insight.ini` file:

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## Disinstallazione della workstation {#section-5ce2e233fe4348469ef1b3c451dd5b70}

Data Workbench ora include un eseguibile per disinstallare la workstation (che si trova per impostazione predefinita all&#39;indirizzo **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**).

Avviare e seguire i passaggi per rimuovere i file Data Workbench Workstation dal disco rigido.

>[!NOTE]
>
>Puoi avviare la **unins000.exe** eseguibile dalla cartella, utilizzando **Disinstalla Data Workbench** collegamento dal menu Start o da **[!UICONTROL Control Panel]** > **[!UICONTROL Program and Features]**.
