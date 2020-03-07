---
description: Aggiornamento dei componenti server per Workbench dati 6.3.
title: Aggiornamento del server DWB da 6.2 a 6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Aggiornamento del server DWB: da 6.2 a 6.3{#dwb-server-upgrade-to}

Aggiornamento dei componenti server per Workbench dati 6.3.

**Server di aggiornamento**

Se avete dei profili personalizzati che hanno la precedenza sui file predefiniti forniti nel [!DNL Base] pacchetto, dovrete aggiornare questi file personalizzati:

* **Aggiornare il file** Meta.cfg ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]per impostare la crittografia aggiornata della password per l&#39;unità del file system (server FSU), e aggiungere voci per le trasformazioni Name Value Pair per sfruttare i raggruppamenti [di stringhe di](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0)query.

   1. Aprire il [!DNL meta.cfg] file sull&#39;FSU.
   1. Modificare il tipo di dati per **[!UICONTROL Proxy Password]** da &quot; [!DNL string"] a &quot; [!DNL EncryptedString]&quot; nella sezione Configurazione ** workstation.

      ```
      Proxy User Name = string: 
      Proxy Password = EncryptedString:   ( 
      
<i>da Password proxy = String</i>)Usa file indirizzo = booleano: true&quot;

    1. Aggiungete nuove voci per abilitare le nuove trasformazioni Nome coppia valore: *BuildNameValuePair* e *ExtractNameValuePair*.
    
    Apri un&#39;area di lavoro e fai clic con il pulsante destro del mouse **Admin** > **Profile Manager**.
    
    In **Context**, fare clic sul file **meta.cfg** nella colonna **Base**, quindi fare clic su **Make Local*. Nella colonna della tabella Utente, fare clic con il pulsante destro del mouse e selezionare **Open** > **in Workstation*.
    
    ![](assets/meta_cfg.png)
    
    * Nella nuova finestra, fate clic su **metadata** e aggiungete modelli figlio accettabili.
    
    ![](assets/meta_cfg_child.png)
    
    * Aprire **transformation** e aggiungere nuovi modelli.
    
    ![](assets/meta_cfg_template.png)

* **Aggiornamento per miglioramenti** di unione rapida. Aggiungi parametri o modifica valori ai seguenti file di configurazione per sfruttare i miglioramenti di velocità in Workbench dati durante una trasformazione.

   * **Communications.cfg** ( [!DNL E:\Server\Components\Communications.cfg])

      ```
      18 = SourceListServer:  
          URI = string: /SourceListServer/ 
          Listing Interval = int: 10 ( 
      <new>)
      ```

   * **Disk Files.cfg** (at [!DNL E:\Server\Components] e [!DNL E:\Server\Components for Processing Servers])

      ```
      Disk Cache Size (MB) = double: 1024  
      <(from double: 256)> 
      Disk Cache Read Limit (MB) = double: 768  
      <(new)>
      ```

   * **Modalità di elaborazione log.cfg** ( [!DNL E:\Server\Profiles\<your profile>\Dataset\Log Processing Mode.cfg])

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
   >Per sfruttare i miglioramenti apportati alla funzione Unione veloce, accertatevi di disporre di almeno 8 GB di RAM per unità di elaborazione dati.

* **Adobe Target con aggiornamento** dell&#39;integrazione DWB. Un nuovo file di esportazione [!DNL ExportIntegration.exe]sostituisce il [!DNL TnTSend.exe] file esistente in Insight Server (`E:\Server\Scripts\TnTSend.exe`). Questo nuovo file di esportazione supporta sia l&#39;integrazione [Adobe Target](https://www.adobe.com/marketing/target.html) che il coordinamento con il nuovo profilo marketing principale (MMP) e [Adobe Audience Manager](https://www.adobe.com/analytics/audience-manager.html).

   Dovrete aggiornare i seguenti comandi per le esportazioni di Adobe Target.

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

   Per utilizzare il vecchio processo di esportazione, potete anche provare quanto segue:

   * Crea una nuova esportazione Test e Target nella workstation.
   * Modificate la vecchia esportazione Test e Target trovata in [!DNL Server/Profiles/`<your profile>`/Export.]

* **Aggiorna il profilo Adobe SC.** Le modifiche apportate al [!DNL Exclude Hit.cfg] file richiedono la dichiarazione di un campo nel [!DNL Decoding Instructions.cfg] file associato.

   >[!NOTE]
   >
   >Se il profilo Adobe SC include un [!DNL Decoding Instructions.cfg] file personalizzato, dovrete includere un [!DNL DelimitedDecoder] parametro nel file personalizzato.

   ```
   0 = DelimitedDecoder: 
      Delimiter = string: \t 
      Fields = vector: x items 
      …  
         5 = string: 
   Changed to: 
   
   5 = string: x-hit_source
   ```

   L&#39;aggiunta di questo [!DNL DelimitedDecoder] campo consente di sfruttare gli aggiornamenti delle funzioni e di evitare possibili problemi di elaborazione del registro derivanti da questi aggiornamenti.
