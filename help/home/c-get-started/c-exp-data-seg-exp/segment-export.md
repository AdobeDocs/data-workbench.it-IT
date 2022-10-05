---
description: Esportare segmenti utilizzando la procedura guidata di esportazione dei segmenti
title: Procedura guidata di esportazione del segmento
uuid: 705bdf00-54e5-4992-8978-91afda8c7543
exl-id: 6f42c5c6-a158-4ddd-8949-4ef55a44ed1c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 6%

---

# Procedura guidata di esportazione del segmento{#segment-export-wizard}

{{eol}}

Esportare segmenti utilizzando la procedura guidata di esportazione dei segmenti

La procedura guidata di esportazione dei segmenti fornisce una procedura dettagliata per configurare ed esportare i segmenti anziché [esportazione di segmenti da una tabella di dettaglio](https://experienceleague.adobe.com/docs/data-workbench/using/client/export-data/c-sgmt-expt.html).

## Esportare segmenti utilizzando la procedura guidata {#section-b30f2699dbc7490bad18512b91cb0cb3}

Per aprire la procedura guidata, fare clic con il pulsante destro del mouse in un’area di lavoro e selezionare **Amministratore** > **Procedure guidate** > **Procedura guidata di esportazione del segmento**.

>[!NOTE]
>
>Verranno acquisiti solo i segmenti applicati prima dell’apertura della procedura guidata. Inoltre, le esportazioni dei segmenti create dalla procedura guidata non possono generare comandi esterni.

1. Seleziona i vari livelli padre delle dimensioni e delle metriche da aggiungere all’esportazione.

   I livelli visualizzati dipendono dal profilo selezionato. Puoi selezionare più livelli di dimensione in base al profilo.

   ![](assets/seg_wizard_1.png)

1. Fai clic su **Avanti**.
1. Seleziona il Dimension e le metriche per i livelli selezionati.

   Ad esempio, dopo aver selezionato Visualizzazione pagina come livello padre, puoi selezionare le dimensioni e le metriche secondarie disponibili per l’esportazione.

1. Fai clic su **Avanti**.

   ![](assets/seg_wizard_2.png)

   ![](assets/seg_wizard_2_1.png)

1. Selezionare il formato di esportazione e immettere un nome per il file di esportazione.

   ![](assets/seg_wizard_3.png)

   I tipi CSV, TSV, Segment Export e Segment Export With Header non necessitano di configurazioni aggiuntive. Tuttavia, i profili e l’esportazione del pubblico, il servizio di record personalizzato e l’esportazione di Adobe Target devono essere configurati nel passaggio 3. Ad esempio, consulta i campi di configurazione per l’esportazione di profili e pubblico . Configura questi tipi di esportazione e fai clic su **Successivo**.

   ![](assets/seg_wizard_3_1.png)

   ![](assets/seg_wizard_3_2.png)

   ![](assets/seg_wizard_3_3.png)

1. Configura il tipo di esportazione selezionato.

   Intestazione: se Intestazione è True, denominare **File di output** campo .

   Campo di escape: impostato come **True** o **False**.

   Ordine dei campi - Consente di selezionare un campo e di spostarsi verso l&#39;alto o verso il basso per impostare l&#39;ordine nel file di esportazione.

   ![](assets/seg_wizard_4.png)

   Fai clic su **Avanti**.

1. Visualizza il Livello e i filtri applicati in questa finestra di dialogo. Fai clic su **Avanti**. ![](assets/seg_wizard_5.png)

1. Se **CSV**, **TSV**, **Esportazione segmento** o **Esportazione segmento con intestazione** è selezionato quindi sono disponibili tre opzioni:

   Esportazione generica: il file di output verrà generato dal server nella cartella Server/Export.

   ![](assets/seg_wizard_6.png)

   Esportazione FTP: il file di output verrà trasferito al server selezionato. (L&#39;elenco del server verrà preso dal file FTPServerInfo.cfg.)

   ![](assets/seg_wizard_6_1.png)

   Esportazione SFTP: il file di output verrà trasferito in modo sicuro al server selezionato.

1. Fai clic su **Avanti**

   **Nota:** Se il tipo di esportazione selezionato è **Esportazione di profili e pubblico**, **Servizio di record personalizzati** e **Esportazione Adobe Target**, il testo sarà statico in base all’esportazione selezionata.

1. Configura i parametri di pianificazione.

   **Una foto** può essere impostato su True o False.

   **Pianificazione avanzata** può essere attivato o disattivato facendo clic sul pulsante Advanced Scheduling Configuration (Configurazione programmazione avanzata).

   ![](assets/seg_wizard_7.png)

   Come per l&#39;esportazione dalla tabella dei dettagli, una ripresa sparirà se l&#39;impostazione avanzata è attivata. Fai clic su **Avanti**.

1. Visualizza l’anteprima del file di esportazione e fai clic su **Esegui esportazione**.

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
