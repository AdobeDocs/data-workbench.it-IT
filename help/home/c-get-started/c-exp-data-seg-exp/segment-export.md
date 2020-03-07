---
description: Esportare segmenti utilizzando la procedura guidata di esportazione dei segmenti
title: Esportazione guidata segmenti
uuid: 705bdf00-54e5-4992-8978-91afda8c7543
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Segment export wizard{#segment-export-wizard}

Esportare segmenti utilizzando la procedura guidata di esportazione dei segmenti

La procedura guidata di esportazione dei segmenti consente di configurare ed esportare i segmenti anziché di [esportarli da una tabella](https://docs.adobe.com/content/help/en/data-workbench/using/client/export-data/c-sgmt-expt.html)di dettaglio.

## Esportare segmenti utilizzando la procedura guidata {#section-b30f2699dbc7490bad18512b91cb0cb3}

Per aprire la procedura guidata, fai clic con il pulsante destro del mouse in un’area di lavoro e seleziona **Amministratore** > **Procedure guidate** > Esportazione guidata **** segmenti.

>[!NOTE]
>
>Vengono acquisiti solo i segmenti applicati prima dell’apertura della procedura guidata. Inoltre, le esportazioni di segmenti create dalla procedura guidata non possono generare comandi esterni.

1. Seleziona i vari livelli padre delle dimensioni e delle metriche da aggiungere all&#39;esportazione.

   I livelli visualizzati dipendono dal profilo selezionato. Potete selezionare più livelli di dimensione in base al profilo.

   ![](assets/seg_wizard_1.png)

1. Fai clic su **Successivo**.
1. Selezionare la dimensione e le metriche per i livelli selezionati.

   Ad esempio, dopo aver selezionato Visualizzazione pagina come livello padre, potete selezionare le dimensioni e le metriche figlie disponibili per l’esportazione.

1. Fai clic su **Successivo**.

   ![](assets/seg_wizard_2.png)

   ![](assets/seg_wizard_2_1.png)

1. Selezionate il formato di esportazione e immettete un nome per il file di esportazione.

   ![](assets/seg_wizard_3.png)

   Per i tipi CSV, TSV, Esportazione segmenti ed Esportazione segmenti con intestazione non è necessaria alcuna configurazione aggiuntiva. Tuttavia, i profili e l&#39;esportazione dell&#39;audience, il servizio record personalizzato e l&#39;esportazione Adobe Target devono essere configurati nel passaggio 3. Ad esempio, vedete i campi di configurazione per Profili e Audience Export. Configurate questi tipi di esportazione e fate clic su **Avanti**.

   ![](assets/seg_wizard_3_1.png)

   ![](assets/seg_wizard_3_2.png)

   ![](assets/seg_wizard_3_3.png)

1. Configura il tipo di esportazione selezionato.

   Intestazione: se Intestazione è True, assegnare un nome al campo File **di** output.

   Campo di escape (Escape Field) - Impostato come **True** o **False**.

   Ordine dei campi (Order of Fields) - Selezionate un campo e spostatevi in alto o in basso per impostare l&#39;ordine nel file di esportazione.

   ![](assets/seg_wizard_4.png)

   Fai clic su **Successivo**.

1. Visualizza il livello e i filtri applicati in questa finestra di dialogo. Fai clic su **Successivo**. ![](assets/seg_wizard_5.png)

1. Se **CSV**, **TSV**, Esportazione **** segmento o Esportazione **segmento con intestazione** è selezionato, sono disponibili tre opzioni:

   Esportazione generica - Il file di output verrà generato dal server nella cartella Server/Export.

   ![](assets/seg_wizard_6.png)

   Esportazione FTP - Il file di output verrà trasferito al server selezionato. (L&#39;elenco del server verrà selezionato dal file FTPServerInfo.cfg.)

   ![](assets/seg_wizard_6_1.png)

   Esportazione SFTP - Il file di output verrà trasferito in modo sicuro al server selezionato.

1. Fai clic su **Avanti**. 

   **Nota:** Se il tipo di esportazione selezionato è **Profili ed esportazione** pubblico, **Custom Record Service** e **Adobe Target Export**, il testo sarà statico in base all&#39;esportazione selezionata.

1. Configurare i parametri di pianificazione.

   **Una ripresa** può essere impostata su True o False.

   **È possibile attivare o disattivare la programmazione** avanzata facendo clic sul pulsante Advanced Scheduling Configuration (Configurazione programmazione avanzata).

   ![](assets/seg_wizard_7.png)

   Come per l’esportazione dalla tabella dei dettagli, se l’opzione Impostazioni avanzate è attivata, One Shot viene disattivato. Fai clic su **Successivo**.

1. Visualizzate l’anteprima del file di esportazione e fate clic su **Esegui esportazione**.

   ![](assets/seg_wizard_8.png)

   ![](assets/seg_wizard_8_1.png)

I seguenti tipi di esportazioni sono disponibili tramite la procedura guidata:

**Tipi di esportazione dei segmenti**

* Generico
* FTP
* SFTP

**Esportazione segmento con intestazione**

* Generico
* FTP
* SFTP

**Esportazione CSV**

* Generico
* FTP
* SFTP

**Esportazione TSV**

* Generico
* FTP
* SFTP

