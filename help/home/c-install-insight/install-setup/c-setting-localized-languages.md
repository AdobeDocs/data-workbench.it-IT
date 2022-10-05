---
description: Imposta il file insight.zbin per impostare la lingua dell'applicazione client.
title: Impostazione delle lingue localizzate insight.zbin
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 1%

---

# Impostazione delle lingue localizzate{#setting-up-localized-languages}

{{eol}}

Imposta il file insight.zbin per impostare la lingua dell&#39;applicazione client.

## Aggiornamento dei componenti del server di Data Workbench {#section-5d07a081befc4eaa8fdf7fea904e0d48}

L’amministratore deve prima completare queste attività per aggiornare questi componenti server:

1. **Aggiornamento al server di Data Workbench 6.x.** È necessario aggiornare il server di Data Workbench per la localizzazione aggiornando il [!DNL base\localization\*.zbin] file. Questo [!DNL insight.zbin] il file verrà quindi copiato nel client.

   Un [!DNL insight.zbin] è incluso nella cartella di installazione accanto al [!DNL insight.exe] file. Se ci si connette a un server che non fornisce informazioni specifiche per la lingua [!DNL .zbin] file, quindi Data Workbench procederà all’utilizzo di questo file.

   Backup [!DNL insight.zbin] file può essere fornito in qualsiasi lingua. Di conseguenza, se utilizzi Data Workbench in cinese e ti connetti a un server che non supporta questa lingua, il client di Data Workbench sarà ancora in cinese, anche se il server modifica il tuo profilo di base e rimuove il tuo [!DNL .zbin] file dal [!DNL Base/Localization] cartella.

1. **Aggiorna il server di rapporto di Data Workbench.** La [!DNL insight.zbin] per impostazione predefinita, nella cartella principale del server di rapporti di Data Workbench è disponibile l’inglese. In qualità di amministratore, dovrai selezionare e copiare il [!DNL .zbin] dal pacchetto del server di rapporto aggiornato e inseriscilo nella directory principale del server di rapporto di Data Workbench. Come il client, anche il server di report richiede gli argomenti appropriati per la lingua selezionata, ad esempio [!DNL Insight.exe -zh-cn]

   1. Arresta i servizi del server di rapporto.
   1. Copia il [!DNL Localization] dal nuovo pacchetto del server di report.
   1. Da [!DNL Localization] cartella, copia [!DNL Insight.zbin] e posizionarlo nella directory principale del server di report dove [!DNL Insight.exe] si trova.

   1. Aggiungi eventuali argomenti richiesti, ad esempio [!DNL insight.exe -zh-cn]
   1. Riavvia il server di rapporto.

## Aggiornare il client di Data Workbench {#section-9653d3fcaf2a4337a97b685857e7aeac}

Dopo aver aggiornato il server, segui questi passaggi per aggiornare ogni client.

1. Per assicurarti che il client non venga aggiornato dal server durante questo aggiornamento, imposta la [!DNL Insight.cfg] argomento su False.

   ```
   Update Software = bool: false
   ```

1. Riavvia il client.
1. Passa al profilo Software e Documenti (profilo SoftDocs) e scarica il **[!UICONTROL insight.zbin]** file dal pacchetto client: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Sposta la [!DNL insight.zbin] nella cartella in cui [!DNL insight.exe] si trova.

1. Per essere certi che i file client vengano aggiornati dal server, modifica il [!DNL Insight.cfg] argomento file su True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Il client si sincronizzerà con il server e verrà visualizzato un messaggio che indica che si sta aggiornando. Al termine del download, verrà visualizzato un messaggio in cui si chiede se si desidera riavviare il client.

1. Fai clic su **OK** per riavviare il client.

Se ricevi il seguente messaggio, significa che [!DNL zbin] il file non è stato inserito nella stessa posizione del [!DNL Insight.exe].

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
