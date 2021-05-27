---
description: Imposta il file insight.zbin per impostare la lingua dell'applicazione client.
title: Impostazione delle lingue localizzate
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Impostazione delle lingue localizzate{#setting-up-localized-languages}

Imposta il file insight.zbin per impostare la lingua dell&#39;applicazione client.

## Aggiornare i componenti del server di Data Workbench {#section-5d07a081befc4eaa8fdf7fea904e0d48}

L’amministratore deve prima completare queste attività per aggiornare questi componenti server:

1. **Aggiornamento al server di Data Workbench 6.x.** È necessario aggiornare il server di Data Workbench per la localizzazione aggiornando il  [!DNL base\localization\*.zbin] file . Questo file [!DNL insight.zbin] verrà quindi copiato nel client.

   Un file [!DNL insight.zbin] è incluso nella cartella di installazione accanto al file [!DNL insight.exe]. Se ti connetti a un server che non ti fornisce file [!DNL .zbin] specifici per la lingua, Data Workbench procederà all’utilizzo di questo file.

   Il file di backup [!DNL insight.zbin] può essere fornito in qualsiasi lingua. Di conseguenza, se utilizzi Data Workbench in cinese e ti connetti a un server che non supporta questa lingua, il client di Data Workbench sarà ancora in cinese, anche se il server modifica il tuo profilo di base e rimuove i file [!DNL .zbin] dalla cartella [!DNL Base/Localization].

1. **Aggiorna il server di rapporto di Data Workbench.** Per impostazione predefinita, la cartella principale  [!DNL insight.zbin] del server di report di Data Workbench è in inglese. In qualità di amministratore, ti verrà richiesto di selezionare e copiare il file [!DNL .zbin] dal pacchetto del server di rapporto aggiornato e inserirlo nella directory principale del server di rapporto di Data Workbench. Come il client, anche il server di report richiede gli argomenti appropriati per la lingua selezionata, ad esempio [!DNL Insight.exe -zh-cn]

   1. Arresta i servizi del server di rapporto.
   1. Copia la cartella [!DNL Localization] dal nuovo pacchetto del server di report.
   1. Dalla cartella [!DNL Localization], copia il file [!DNL Insight.zbin] e inseriscilo nella directory principale del server di report in cui si trova il percorso [!DNL Insight.exe].

   1. Aggiungi eventuali argomenti richiesti, ad esempio [!DNL insight.exe -zh-cn]
   1. Riavvia il server di rapporto.

## Aggiornare il client di Data Workbench {#section-9653d3fcaf2a4337a97b685857e7aeac}

Dopo aver aggiornato il server, segui questi passaggi per aggiornare ogni client.

1. Per assicurarti che il client non venga aggiornato dal server durante questo aggiornamento, imposta l&#39;argomento [!DNL Insight.cfg] su False.

   ```
   Update Software = bool: false
   ```

1. Riavvia il client.
1. Passa al profilo Software e Documenti (profilo SoftDocs) e scarica il file **[!UICONTROL insight.zbin]** richiesto dal pacchetto client: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Sposta il file [!DNL insight.zbin] nella cartella in cui si trova [!DNL insight.exe].

1. Per assicurarti che i file client ora vengano aggiornati dal server, modifica l&#39;argomento del file [!DNL Insight.cfg] in True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Il client si sincronizzerà con il server e verrà visualizzato un messaggio che indica che si sta aggiornando. Al termine del download, verrà visualizzato un messaggio in cui si chiede se si desidera riavviare il client.

1. Fare clic su **OK** per riavviare il client.

Se ricevi il seguente messaggio, significa che il file [!DNL zbin] non è stato inserito nella stessa posizione del file [!DNL Insight.exe].

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**Schermate introduttive localizzate**

Data Workbench cerca i seguenti file della schermata iniziale:

* Inglese (predefinito): [!DNL Base/Images/<version_product> Splash.png]
* Cinese (quando iniziato con -zh-cn): [!DNL Base/Images/<version_product> Splash zh-cn.png].

Se è richiesta una schermata iniziale ma è mancante, per impostazione predefinita Data Workbench accederà alla schermata iniziale inglese.

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->
