---
description: In questa sezione viene illustrato come creare marche temporali per un dataset Workbench dati.
title: Impostazione dell'ora evento
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Impostazione dell&#39;ora evento{#setting-up-event-time}

In questa sezione viene illustrato come creare marche temporali per un dataset Workbench dati.

## Informazioni sull’ora dell’evento {#section-e10ef2b5b6244dc5b215836e3c77d663}

Ora evento è la data e l’ora in cui si verifica la richiesta (o l’evento).

In genere, per i dati online, *x_hit_time_gmt* viene utilizzato come campo timestamp. L’ora della chiamata può essere utilizzata come marca temporale per i dati offline (come i dati del call center). Questo campo è obbligatorio e tutte le origini dati devono contenere un campo che può essere utilizzato come timestamp. Queste informazioni devono essere fornite dalla vostra organizzazione.

In DWB, le seguenti variabili predefinite acquisiscono la marca temporale:

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> Data e ora (GMT) in cui la richiesta è stata ricevuta dal server. Il tempo è espresso come numero di 100 nanosecondi dal 1 gennaio 1600. </p> <p>Esempio: 127710989320000000 corrisponde al valore <i>x-timestamp</i> per 11:28:52.0000000 di martedì 13 settembre 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestring</i> </td> 
   <td colname="col2"> <i>x-timestamp</i> nel formato AAAA-MM-GG HH:MM:SS.mmm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> è il tempo epoc che rappresenta il numero di secondi dal 1° gennaio 1970 alle 00:00:01. </td> 
  </tr> 
 </tbody> 
</table>

In base al formato del campo data, viene utilizzata la marca x-timestamp o la stringa x-unixtime o x-timestring. Ad esempio, se i dati in arrivo sono nel formato AAAA-MM-GG, deve essere utilizzata la stringa x-time.

La marca temporale è definita in uno dei formati e DWB genera internamente gli altri due formati. Inoltre, questi sono campi DWB predefiniti e lo stesso nome non deve essere utilizzato per nessun altro campo.

## Fusi orari definiti in DWB {#section-3cdd12254342442b917376661e1d9c9f}

Se il campo data contiene uno dei fusi orari indicati di seguito, DWB considera l’intera riga in quel particolare fuso orario. Ad esempio, un file ha la data definita come 2015-01-01 00:00:00 gmte un altro file ha il valore impostato come 2015-01-01 00:00:00 cst, quindi la data del primo file sarà considerata nel fuso orario GMT, mentre la data del secondo file sarà in CST Fuso orario ST.

| Codice | Fuso orario |
|---|---|
| gmt | Greenwich Mean |
| est | Standard orientale |
| edt | Luce diurna orientale |
| cst | Standard centrale |
| cdt | Luce diurna centrale |
| mst | Mountain Standard |
| mdt | Luce diurna montagna |
| pst | Standard Pacifico |
| pdt | Luce diurna Pacifico |

>[!NOTE]
>
>DWB elabora solo i Fusi orari di cui sopra.

## Impostazione dei fusi orari personalizzati {#section-7c351921f22b439b81c73f40d5b47536}

DWB non elabora l&#39;offset nel Fuso orario. Per considerare l&#39;offset nel fuso orario, i dati devono essere formattati in tale fuso orario offset.

Esempio: per considerare il formato della data nel fuso orario CST, i dati devono essere in formato AAAA-MM-GG HH:MM:SS UTC +/-HHMM dal client.

2015-10-18 05:00:00 UTC -0200

## Come impostare l&#39;ora/la marca temporale dell&#39;evento {#section-81507080f0b44ae6b83d3650ba019812}

In base al formato del campo data, viene utilizzata la variabile *x-timestamp, x-unixtime* o *x-timestring* . Nell&#39;esempio seguente, poiché la *x-hit_time_gmt* viene fornita in formato epoc singolo, viene utilizzato *x-unixtime* .

Nel [!DNL foundation.cfg] file DWB (o in qualsiasi altro file di configurazione all&#39;interno della cartella di elaborazione del registro DataSet), utilizzate la trasformazione Copia per impostare l&#39;ora evento come illustrato:

In base al formato del campo data, viene utilizzata la variabile x-timestamp, x-unixtime o x-timestring. Nell&#39;esempio seguente, poiché x-hit_time_gmt viene fornito in formato unix epoc, viene utilizzato x-unixtime.

In insight foundation.cfg (o qualsiasi altra configurazione nella cartella di elaborazione del registro DataPae), utilizzate la trasformazione Copia per impostare l’ora evento come illustrato di seguito: ![](assets/dwb_impl_timestamp1.png)

Se la data in è in formato AAAA-MM-GG HH:MM:SS.mmm, viene utilizzata la stringa x-timestamp. ![](assets/dwb_impl_timestamp2.png)Esempio: Se il campo data è nel formato diverso da quello definito in DWB, ad esempio AAAA/MM/GG, formattarlo prima in uno dei formati di marca temporale accettati dal DWB e quindi assegnarlo alla variabile corrispondente. Nella schermata seguente, la data viene convertita in formato AAAA-MM-GG e quindi assegnata alla variabile *x-timestring *variable. ![](assets/dwb_impl_timestamp3.png)

