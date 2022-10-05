---
description: Questa sezione spiega come creare marche temporali per un set di dati di Data Workbench.
title: Impostazione dell’ora evento
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
exl-id: 9632e713-5cf9-4acf-aafa-bfdf79a51ad9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 1%

---

# Impostazione dell’ora evento{#setting-up-event-time}

{{eol}}

Questa sezione spiega come creare marche temporali per un set di dati di Data Workbench.

## Informazioni sull’ora evento {#section-e10ef2b5b6244dc5b215836e3c77d663}

L’ora evento è la data e l’ora in cui si verifica la richiesta (o l’evento).

Di solito, per i dati online, *x_hit_time_gmt* viene utilizzato come campo timestamp . L’ora della chiamata può essere utilizzata come marca temporale per i dati offline (ad esempio i dati del call center). Si tratta di un campo obbligatorio che deve contenere un solo campo da utilizzare come timestamp per tutte le origini dati. Queste informazioni devono essere fornite dalla tua organizzazione.

In DWB, le seguenti variabili predefinite acquisiscono il timestamp:

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> Data e ora (GMT) in cui la richiesta è stata ricevuta dal server. Il tempo è espresso come numero di 100 nanosecondi dal 1° gennaio 1600. </p> <p>Esempio: 127710989320000000 sarà il <i>x-timestamp</i> valore per 11:28:52.0000000 martedì 13 settembre 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <i>x-timestamp</i> nel formato AAAA-MM-GG HH:MM:SS.mmm </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> è il tempo dell'epoc che rappresenta il numero di secondi dal 1° gennaio 1970 a 00:00:01 </td> 
  </tr> 
 </tbody> 
</table>

In base al formato del campo data, viene utilizzato il timestamp x o x-unixtime o x-timestring. Ad esempio, se i dati in arrivo sono nel formato AAAA-MM-GG, utilizzare la stringa temporale x.

La marca temporale è definita in uno dei formati e DWB genera internamente gli altri due formati. Inoltre, si tratta di campi DWB predefiniti e lo stesso nome non deve essere utilizzato per altri campi.

## Fusi orari definiti in DWB {#section-3cdd12254342442b917376661e1d9c9f}

Se il campo data contiene uno dei fusi orari indicati di seguito, DWB considera l’intera riga in quel particolare fuso orario. Ad esempio, un file ha la data definita come 2015-01-01 00:00:00 gmte un altro file ha il valore 2015-01-01 00:00:0 cst, quindi la data del primo file verrà considerata nel fuso orario GMT, mentre la data del secondo file sarà nel fuso orario CST.

| Codice | Fuso orario |
|---|---|
| gmt | Greenwich Mean |
| test | Standard orientale |
| edt | Daylight orientale |
| cst | Standard centrale |
| cdt | Daylight centrale |
| mst | Standard di montagna |
| mdt | Luce diurna sulle montagne |
| pst | Standard del Pacifico |
| pdt | Daylight Pacifico |

>[!NOTE]
>
>DWB elabora solo i Fusi orari menzionati in precedenza.

## Impostazione dei fusi orari personalizzati {#section-7c351921f22b439b81c73f40d5b47536}

DWB non elabora l&#39;offset nel fuso orario. Per considerare l&#39;offset nel fuso orario, i dati devono essere formattati in quel fuso orario di offset.

Esempio: per considerare il formato della data nel fuso orario CST, i dati devono essere in AAAA-MM-GG HH:MM:Formato SS UTC +/-HHMM dal client.

2015-10-18 05:00:00 UTC -0200

## Come impostare l’ora/la marca temporale dell’evento {#section-81507080f0b44ae6b83d3650ba019812}

In base al formato del campo data, *x-timestamp, x-unixtime* o *x-timestamp* viene utilizzata la variabile . Nell’esempio seguente, dal *x-hit_time_gmt* viene in formato unix epoc, *x-unixtime* viene utilizzato.

Nel DWB [!DNL foundation.cfg] file (o qualsiasi altro file di configurazione nella cartella di elaborazione del registro di Dataset), utilizzare la trasformazione Copia per impostare l&#39;ora evento come mostrato:

In base al formato del campo data, viene utilizzata la variabile x-timestamp, x-unixtime o x-timestring. Nell’esempio seguente, poiché x-hit_time_gmt viene fornito in formato unix epoc, viene utilizzato x-unixtime.

In insight foundation.cfg (o qualsiasi altra configurazione nella cartella di elaborazione del registro di Datasetà), utilizza la trasformazione Copia per impostare l’ora evento come mostrato di seguito: ![](assets/dwb_impl_timestamp1.png)

Se la data in è AAAA-MM-GG HH:MM:Formato SS.mmm, x-timestamp. ![](assets/dwb_impl_timestamp2.png)Esempio: Se il campo data è nel formato diverso da quello definito in DWB, ad esempio AAAA/MM/GG, formattalo prima in uno dei formati di marca temporale accettati dal DWB e quindi assegnalo alla variabile corrispondente. Nella schermata seguente, la data viene prima convertita in formato AAAA-MM-GG e poi assegnata alla variabile *x-timestring *. ![](assets/dwb_impl_timestamp3.png)
