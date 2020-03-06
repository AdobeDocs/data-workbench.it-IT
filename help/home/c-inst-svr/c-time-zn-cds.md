---
description: Formattare le istruzioni sui parametri basati su tempo in Insight Server.
solution: Insight
title: Codici Fuso Orario
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Codici Fuso Orario{#time-zone-codes}

Formattare le istruzioni sui parametri basati su tempo in Insight Server.

La maggior parte dei parametri basati sul tempo in [!DNL Insight Server] sono specificati nel seguente formato:

*Mese GG, AAAA HH:MM:SS Fuso orario*

Esempio: 13 agosto 2013 22:30:00 EST

I fusi orari sono espressi in un formato del fuso orario indipendente dal sistema (ora universale coordinata) nel seguente formato:

UTC + *dstrules*

Il segno (+) può essere un segno più (+) o meno (-) e *hhmm* è l&#39;offset dall&#39;UTC in ore e minuti. Le *combinazioni* di variabili facoltative specificano un insieme di regole per implementare l&#39;ora legale o un criterio simile per lo spostamento dell&#39;orologio.

Se si specificano *le specifiche*, un file delimitato da tabulazioni denominato *&lt;[!DNL dstrules]>* [!DNL .dst] deve essere presente nella directory Dataset\TimeZone del profilo Base (per i file di configurazione non associati a un particolare dataset) o del profilo dataset (per i file di configurazione specifici per i dataset). Il file specifica un set di regole indipendente dal fuso orario per l&#39;ora legale. Potete avere diversi insiemi di regole per anni diversi. Il [!DNL DST.dst] file fornito da Adobe nel profilo Base specifica le regole standard statunitensi stabilite dal Energy Policy Act del 2005 (in vigore dal 2007) e dalle regole statunitensi per gli anni precedenti.

Di seguito sono elencate le voci relative al fuso orario di esempio:

* Ora legale USA: Fuso orario = stringa: UTC -0500 DST
* Ora UTC senza offset e nessuna *dilatazione* (corrispondente a GMT): Fuso orario = stringa: UTC -0000

Quando si utilizza questo formato, il fuso orario del sistema di [!DNL Insight Server], [!DNL Insight]e [!DNL Report] i computer non devono corrispondere al fuso orario specificato. Inoltre, tutti i profili di dataset attivi su un [!DNL Insight Server] computer non devono avere la stessa impostazione di fuso orario.

La tabella seguente contiene l&#39;elenco di codici che è possibile utilizzare per specificare i fusi orari nei parametri basati su tempo.

## Tabella codici zona temporale {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Se state implementando l&#39;ora legale o un criterio simile per lo spostamento dell&#39;orologio, dovete salvare il [!DNL .dst] file contenente le regole appropriate nel nome *\Dataset\Timezone directory on the* del [!DNL Insight Server] profilo.

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

