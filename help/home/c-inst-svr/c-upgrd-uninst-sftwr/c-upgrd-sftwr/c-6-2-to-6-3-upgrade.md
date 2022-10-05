---
description: Aggiornamento dei componenti server per Data Workbench 6.3.
title: Aggiornamento del server DWB da 6.2 a 6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
exl-id: 5106d9a3-179a-49f1-915a-c03b36ed5257
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Aggiornamento del server DWB: da 6.2 a 6.3{#dwb-server-upgrade-to}

{{eol}}

Aggiornamento dei componenti server per Data Workbench 6.3.

**Server di aggiornamento**

Se hai profili personalizzati che hanno la precedenza sui file predefiniti forniti nella [!DNL Base] pacchetto, allora sarà necessario aggiornare questi file personalizzati:

* **Aggiornare il file Meta.cfg** ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]impostare la crittografia password aggiornata per il server FSU (File System Unit) e aggiungere voci per le trasformazioni Name Value Pair per sfruttare [Raggruppamenti di stringhe di query](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0).

   1. Apri [!DNL meta.cfg] file sulla FSU.
   1. Modificare il tipo di dati per **[!UICONTROL Proxy Password]** da &quot; [!DNL string"] a &quot; [!DNL EncryptedString]&quot; nel *Configurazione della workstation* sezione .

      ```
        Proxy User Name = string:
        Proxy Password = EncryptedString:   (
        from Proxy Password = String)
        Use Address File = bool: true
      ```

   1. Aggiungi nuove voci per abilitare le nuove trasformazioni Coppia di valori dei nomi: *BuildNameValuePair* e *ExtractNameValuePair*.

      Apri un’area di lavoro e fai clic con il pulsante destro del mouse **Amministratore** > **Profile Manager**.

      Sotto **Contesto**, fai clic su **meta.cfg** nel **Base** quindi fai clic su **Rendi locale**. Dalla colonna della tabella Utente, fai clic con il pulsante destro del mouse e seleziona **Apri** > **in Workstation**.

      ![](assets/meta_cfg.png)

      * Nella nuova finestra, fai clic su **metadati** e aggiungere modelli figlio accettabili.

         ![](assets/meta_cfg_child.png)

      * Apri **trasformazione** e aggiungi nuovi modelli.

         ![](assets/meta_cfg_template.png)

* **Aggiornamento per miglioramenti della funzione di unione rapida**. Aggiungi parametri o modifica valori ai seguenti file di configurazione per sfruttare i miglioramenti di velocità nella Data Workbench durante una trasformazione.

   * **Communications.cfg** ( [!DNL E:\Server\Components\Communications.cfg])

      ```
      18 = SourceListServer:
          URI = string: /SourceListServer/
          Listing Interval = int: 10 (
      <new>)
      ```

   * **Disk Files.cfg** (a) [!DNL E:\Server\Components] e [!DNL E:\Server\Components for Processing Servers])

      ```
      Disk Cache Size (MB) = double: 1024
      <(from double: 256)>
      Disk Cache Read Limit (MB) = double: 768
      <(new)>
      ```

   * **Elaborazione registro Mode.cfg** ( [!DNL E:\Server\Profiles\<your profile>\Dataset\Log Processing Mode.cfg])

      ```
      <(changed)
      Batch Bytes = int: 268435456
      Cloud Bytes = int: 268435456
      Real Time FIFO Bytes = int: 268435456
      ```

      ```
      (
      <new>)
      Cache Bytes = int: 32000000
      Fast Input Decision Ratio = double: 200
      Fast Input FIFO Bytes = int: 268435456
      FIFO Hash Mask = int: 16383
      Fast Merge Buffer Bytes = int: 536870912
      Slow Merge Buffer Bytes = int: 268435456
      Fast Merge Fan In = int: 64
      Key Cache Size Logarithm = int: 21
      Max Seeks = int: 512
      Output Old Buffer Bytes = int: 536870912
      Overflow FIFO Bytes = int: 67108864
      Paused = bool: false
      ```
   >[!NOTE]
   >
   >Per usufruire dei miglioramenti apportati alla funzione Fast Merge, assicurati di disporre di almeno 8 GB di RAM per DPU.

* **Aggiornamento dell’integrazione Adobe Target con DWB**. Un nuovo file di esportazione, [!DNL ExportIntegration.exe], sostituisce l&#39;esistente [!DNL TnTSend.exe] file su Insight Server (`E:\Server\Scripts\TnTSend.exe`). Questo nuovo file di esportazione supporta entrambi [Adobe Target](https://www.adobe.com/marketing/target.html) integrazione e coordinamento con il nuovo profilo marketing principale (MMP) e [Adobe Audience Manager](https://www.adobe.com/analytics/audience-manager.html).

   Sarà necessario aggiornare i seguenti comandi per le esportazioni Adobe Target.

   `Command = string: TnTSend.exe`

   in

   ```
   <filepath>
   Command = string: ExportIntegration.exe
   </filepath>
   ```

   >[!NOTE]
   >
   >Questo interesserà solo le esportazioni create prima della versione 6.3.

   Puoi anche provare quanto segue per utilizzare il vecchio processo di esportazione:

   * Crea una nuova esportazione Test e Target nella workstation.
   * Modifica la vecchia esportazione Test e Target trovata in [!DNL Server/Profiles/`<your profile>`/Export.]

* **Aggiorna il profilo Adobe SC.** Modifiche al [!DNL Exclude Hit.cfg] i file richiedono la dichiarazione di un campo nel [!DNL Decoding Instructions.cfg] file.

   >[!NOTE]
   >
   >Se il tuo profilo SC Adobe include un [!DNL Decoding Instructions.cfg] file , sarà necessario includere un [!DNL DelimitedDecoder] al file personalizzato.

   ```
   0 = DelimitedDecoder:
      Delimiter = string: \t
      Fields = vector: x items
      …
         5 = string:
   Changed to:
   
   5 = string: x-hit_source
   ```

   Aggiunta di [!DNL DelimitedDecoder] Il campo ti consente di sfruttare gli aggiornamenti delle funzioni e di evitare possibili problemi di Log Processing derivanti da questi aggiornamenti.
