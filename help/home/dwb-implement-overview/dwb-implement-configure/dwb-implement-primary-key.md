---
description: Questa sezione spiega come creare chiavi primarie (ID di tracciamento) per Data Workbench di set di dati per la progettazione e l’implementazione dello schema.
title: Elaborazione dei dati - Creazione della chiave principale
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
exl-id: 9937038f-d011-4946-8a5b-cc724b611ae5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# Elaborazione dei dati - Creazione della chiave principale{#data-processing-building-primary-key}

{{eol}}

Questa sezione spiega come creare chiavi primarie (ID di tracciamento) per Data Workbench di set di dati per la progettazione e l’implementazione dello schema.

## Informazioni sul tracking ID {#section-24683031044a4af49988655ccb9a45fd}

Dopo aver letto e decodificato i dati in DWB (utilizzando i decoder), il primo passo è quello di definire l’ID di tracciamento e il timestamp. L&#39;ID di tracciamento è un identificatore che identifica in modo univoco un record Cliente. Può essere qualsiasi campo nel feed come ID e-mail, numero di previdenza sociale, ID cookie, ecc. Il campo da utilizzare come ID di tracciamento viene deciso dal client durante la sessione di individuazione. ID tracciamento e timestamp sono campi obbligatori e devono essere definiti per ciascun record.

Di solito, per i dati online, ID cookie (combinazione di *x-visid_high* e* x-visid_low*) viene utilizzato come meccanismo predefinito per l&#39;identificazione univoca del cliente, tuttavia può essere modificato in base alle esigenze del cliente. La data e l’ora in cui si verifica la richiesta (o l’evento) è la *x-timestamp*. Tutti i record in DWB sono raggruppati per *trackingid* e ordinati in base al timestamp. Campo richiesto [!DNL Definitions.cfg] file è un file di inclusione del set di dati di elaborazione del registro che definisce i campi richiesti : *x-trackingid* e *x-timestamp*.

Nota: *x-trackingid *in DWB è un campo incorporato e questo nome non deve essere utilizzato per nessun altro campo.

**Esempio 1**: Creazione *x-trackingid* utilizzo dell’ID cookie (quando vengono utilizzati solo dati online)

Per creare *x-trackingid *in DWB utilizzando l&#39;ID cookie, utilizza la funzione Hash per creare il *x-trackingid* in [!DNL foundation.cfg] file (è consigliabile definire l’ID di tracciamento in [!DNL foundation.cfg] ma può essere definito in qualsiasi altro file di configurazione in [!DNL Dataset > log processing] come mostrato:

![](assets/dwb_impl_primary_key1.png)

**Esempio 2**: Creazione *x-trackingid* utilizzo dell’ID e-mail (quando sono disponibili sia dati online che offline)

Presupponendo che siano disponibili sia dati offline che online (per questo esempio) e che l’ID e-mail sia disponibile in entrambe le origini dati. Poiché l’ID e-mail identifica in modo univoco un cliente, verrà utilizzato per creare il *x-trackingid*.

Utilizza la funzione Hash per creare il *trackingId* come mostrato:

![](assets/dwb_impl_primary_key2.png)
