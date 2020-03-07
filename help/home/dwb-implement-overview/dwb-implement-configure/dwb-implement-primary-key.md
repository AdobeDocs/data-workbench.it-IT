---
description: In questa sezione viene illustrato come creare chiavi primarie (ID tracciamento) per i set di dati Workbench dati per la progettazione e l'implementazione dello schema.
title: Elaborazione dei dati - Creazione della chiave primaria
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Elaborazione dei dati - Creazione della chiave primaria{#data-processing-building-primary-key}

In questa sezione viene illustrato come creare chiavi primarie (ID tracciamento) per i set di dati Workbench dati per la progettazione e l&#39;implementazione dello schema.

## Informazioni sull’ID di tracciamento {#section-24683031044a4af49988655ccb9a45fd}

Dopo aver letto e decodificato i dati in DWB (utilizzando i decodificatori), il primo passo è definire l&#39;ID tracciamento e la marca temporale. L&#39;ID tracciamento è un identificatore che identifica in modo univoco un record cliente. Può trattarsi di qualsiasi campo del feed, ad esempio ID e-mail, Numero previdenza sociale, ID cookie e così via. Il campo da utilizzare come ID tracciamento viene deciso dal client durante la sessione di individuazione. ID tracciamento e marca temporale sono campi obbligatori e devono essere definiti per ciascun record.

Solitamente, per i dati online, il Cookie ID (combinazione di *x-visid_high* e* x-visid_low*) viene utilizzato come meccanismo predefinito per l&#39;identificazione cliente univoca, tuttavia, questo può essere modificato in base ai requisiti del Client. La data e l&#39;ora in cui si verifica la richiesta (o l&#39;evento) è la marca *x-timestamp*. Tutti i record in DWB sono raggruppati per *tracciamento* e ordinati per marca temporale. Il file Campo richiesto è un file DataSet di elaborazione log che definisce i campi richiesti: [!DNL Definitions.cfg] *x-trackingid* e *x-timestamp*.

Nota: *x-trackingid *in DWB è un campo incorporato e questo nome non deve essere utilizzato per nessun altro campo.

**Esempio 1**: Creazione di *x-trackingid* con l&#39;ID del cookie (quando vengono utilizzati solo dati online)

Per creare la *x-trackingid *in DWB utilizzando l&#39;ID del cookie, utilizzate la funzione Hash per creare la *x-trackingid* nel [!DNL foundation.cfg] file (è consigliabile definire l&#39;ID di tracciamento in [!DNL foundation.cfg] ma può essere definita in qualsiasi altro file di configurazione nella [!DNL Dataset > log processing] cartella) come illustrato:

![](assets/dwb_impl_primary_key1.png)

**Esempio 2**: Creazione di dati *x-trackingid* con ID e-mail (quando sono disponibili sia dati online che offline)

Presupponendo che siano disponibili dati offline e online (per questo esempio), e l&#39;ID e-mail sia disponibile in entrambe le origini dati. Poiché l&#39;ID e-mail identifica in modo univoco un cliente, verrà utilizzato per creare la *x-trackingid*.

Utilizzate la funzione Hash per creare *trackingId* come mostrato:

![](assets/dwb_impl_primary_key2.png)

