---
description: Informazioni sui codici e i formati del fuso orario.
solution: Analytics
title: Codici Fuso Orario
topic: Data workbench
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Codici Fuso Orario{#time-zone-codes}

Informazioni sui codici e i formati del fuso orario.

La maggior parte dei parametri basati sul tempo nel server workbench dati sono specificati nel seguente formato:

* Mese GG , AAAA HH :MM :SS TZone
* Esempio: 13 agosto 2013 22:30:00 EST

I fusi orari sono espressi in un formato del fuso orario indipendente dal sistema (ora universale coordinata) nel seguente formato:

* UTC +hhmm moduli

Il segno (+) può essere un segno più (+) o meno (-), e hhmm è l&#39;offset dall&#39;UTC in ore e minuti. Le combinazioni di variabili facoltative specificano un insieme di regole per implementare l&#39;ora legale o un criterio simile per lo spostamento dell&#39;orologio.

Se si specificano le specifiche, un file delimitato da tabulazioni denominato [!DNL dstrules.dst] deve essere presente all&#39;interno della directory Dataset\TimeZone del [!DNL Base] profilo (per i file di configurazione non associati a un set di dati specifico) o del profilo del dataset (per i file di configurazione specifici per i dataset). Il file specifica un set di regole indipendente dal fuso orario per l&#39;ora legale. Potete avere diversi insiemi di regole per anni diversi. Il [!DNL DST.dst] file fornito da Adobe nel [!DNL Base] profilo specifica le regole standard statunitensi stabilite dal Energy Policy Act del 2005 (in vigore dal 2007) e dalle regole statunitensi per gli anni precedenti.

Di seguito sono elencate le voci relative al fuso orario di esempio:

* Ora legale USA: Fuso orario = stringa: UTC -0500 DST
* Ora UTC senza offset e nessuna dilatazione (corrispondente a GMT): Fuso orario = stringa: UTC -0000

Quando si utilizza questo formato, il fuso orario del sistema del server workbench dati, del workbench dati e dei computer report non deve corrispondere al fuso orario specificato. Inoltre, tutti i profili dataset attivi su un computer server workbench dati non devono avere la stessa impostazione di fuso orario.

La tabella seguente contiene l&#39;elenco di codici che è possibile utilizzare per specificare i fusi orari nei parametri basati su tempo.

## Tabella codici zona temporale {#section-b4f965b872c543e2ac52a3c94410d076}

Se si sta implementando l&#39;ora legale o un criterio simile per lo spostamento dell&#39;orologio, è necessario salvare il [!DNL .dst] file contenente le regole appropriate nella directory del nome del profilo [!DNL \Dataset\Timezone] nel computer del server workbench dati.

| Codice | Fuso orario | Offset da GMT |
|---|---|---|
| gmt | Greenwich Mean | 0 |
| est | Standard orientale | 5 |
| edt | Luce diurna orientale | 5 |
| cst | Standard centrale | 6 |
| cdt | Luce diurna centrale | 6 |
| mst | Mountain Standard | 7 |
| mdt | Luce diurna montagna | 7 |
| pst | Standard Pacifico | 8 |
| pdt | Luce diurna Pacifico | 8 |

