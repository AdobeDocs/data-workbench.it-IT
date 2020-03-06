---
description: Configurate il file insight.zbin per impostare la lingua dell'applicazione client.
title: Impostazione delle lingue localizzate
uuid: 97baf281-32fd-4df0-81a6-c2c7126b053c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Impostazione delle lingue localizzate{#setting-up-localized-languages}

Configurate il file insight.zbin per impostare la lingua dell&#39;applicazione client.

## Aggiornamento dei componenti del server workbench dati {#section-5d07a081befc4eaa8fdf7fea904e0d48}

Per aggiornare questi componenti server, l’amministratore deve prima completare le seguenti attività:

1. **Aggiornamento al server workbench dati 6.x.** È necessario aggiornare il server workbench dati per la localizzazione aggiornando il [!DNL base\localization\*.zbin] file. Questo [!DNL insight.zbin] file verrà quindi copiato nel client.

   Un [!DNL insight.zbin] file è incluso nella cartella di installazione accanto al [!DNL insight.exe] file. Se ci si connette a un server che non fornisce [!DNL .zbin] file specifici per la lingua, il workbench dati procederà a utilizzare questo file.

   Il [!DNL insight.zbin] file di backup può essere fornito in qualsiasi lingua. Di conseguenza, se si utilizza il workbench dati in cinese e ci si collega a un server che non supporta questa lingua, il client workbench dati sarà comunque in cinese, anche se il server modifica il profilo di base e rimuove [!DNL .zbin] i file dalla [!DNL Base/Localization] cartella.

1. **Aggiornare il server di report workbench dati.** Per impostazione predefinita, [!DNL insight.zbin] nella cartella principale del server di report workbench dati viene utilizzato l&#39;inglese. L&#39;amministratore dovrà selezionare e copiare il [!DNL .zbin] file dal pacchetto del server di report aggiornato e inserirlo nella directory principale del server di report workbench dati. Come il client, anche il server di report richiede gli argomenti appropriati per la lingua selezionata, ad esempio [!DNL Insight.exe -zh-cn]

   1. Arrestate i servizi del server di report.
   1. Copiate la [!DNL Localization] cartella dal nuovo pacchetto del server di report.
   1. Dalla [!DNL Localization] cartella, copiate il [!DNL Insight.zbin] file e inseritelo nella directory principale del server di report in cui si [!DNL Insight.exe] trova.

   1. Aggiungete eventuali argomenti richiesti, ad esempio [!DNL insight.exe -zh-cn]
   1. Riavviate il server di report.

## Aggiornamento del client workbench dati {#section-9653d3fcaf2a4337a97b685857e7aeac}

Dopo aver aggiornato il server, eseguite i seguenti passaggi per aggiornare ogni client.

1. Per essere certi che il client non venga aggiornato dal server durante questo aggiornamento, impostate l&#39; [!DNL Insight.cfg] argomento su False.

   ```
   Update Software = bool: false
   ```

1. Riavviate il client.
1. Andate al profilo Software e Docs (profilo SoftDocs) e scaricate il **[!UICONTROL insight.zbin]** file richiesto dal pacchetto client: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Spostate il [!DNL insight.zbin] file nella cartella in cui [!DNL insight.exe] si trova.

1. Per essere certi che i file client ora vengano aggiornati dal server, modificate l&#39;argomento [!DNL Insight.cfg] file in True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Il client si sincronizzerà con il server e verrà visualizzato un messaggio in cui si informa che si sta aggiornando. Al termine del download, riceverete un messaggio in cui vi viene chiesto se desiderate riavviare il client.

1. Fate clic su **OK** per riavviare il client.

Se ricevi il messaggio seguente, significa che il [!DNL zbin] file non è stato inserito nella stessa posizione del [!DNL Insight.exe].

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**Schermate iniziali localizzate**

Il workbench dati cerca i seguenti file della schermata iniziale:

* Inglese (predefinito): [!DNL Base/Images/<version_product> Splash.png]
* Cinese (quando iniziato con -zh-cn): [!DNL Base/Images/<version_product> Splash zh-cn.png].

Se una schermata iniziale è richiesta ma mancante, per impostazione predefinita il workbench dati accederà alla schermata iniziale inglese.

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->

