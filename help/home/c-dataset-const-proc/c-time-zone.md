---
description: Informazioni sui codici e i formati del fuso orario.
title: Codici e formati del fuso orario
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 3%

---

# Codici del fuso orario{#time-zone-codes}

Informazioni sui codici e i formati del fuso orario.

La maggior parte dei parametri basati sul tempo nel server di Data Workbench sono specificati nel seguente formato:

* Mese GG , AAAA HH :MM :SS TZone
* Esempio: 13 agosto 2013 22:30:00 EST

I fusi orari sono espressi in un formato del fuso orario indipendente dal sistema (ora universale coordinata) del seguente formato:

* UTC +hhmm dstrisce

Il segno (+) può essere un segno più (+) o meno (-) e hhmm è l’offset dall’UTC in ore e minuti. Le combinazioni di variabili facoltative specificano un insieme di regole per implementare l&#39;ora legale o un criterio simile per lo spostamento dell&#39;orologio.

Se si specificano le stringhe, viene creato un file con valori delimitati da tabulazioni denominato [!DNL dstrules.dst] deve essere presente nella directory Dataset\TimeZone di [!DNL Base] profilo (per file di configurazione non associati a un particolare set di dati) o profilo di set di dati (per file di configurazione specifici per un set di dati). Il file specifica un set di regole indipendente dal fuso orario per l’ora legale. Puoi avere diversi set di regole per diversi anni. La [!DNL DST.dst] file fornito dall&#39;Adobe nel [!DNL Base] profile specifica le norme standard statunitensi stabilite dal Energy Policy Act del 2005 (in vigore a partire dal 2007) e le norme statunitensi per gli anni precedenti.

Di seguito sono elencate le voci relative al fuso orario di esempio:

* Ora legale USA: Fuso orario = stringa: UTC -0500 DST
* Ora UTC senza offset e nessuna dilatazione (corrispondente a GMT): Fuso orario = stringa: UTC -0000

Quando si utilizza questo formato, il fuso orario del sistema del server di Data Workbench, di Data Workbench e dei computer Report non deve corrispondere al fuso orario specificato. Inoltre, tutti i profili di set di dati attivi su un computer server di Data Workbench non devono avere la stessa impostazione di fuso orario.

La tabella seguente contiene l’elenco di codici che è possibile utilizzare per specificare i fusi orari nei parametri basati su tempo.

## Tabella dei codici del fuso orario {#section-b4f965b872c543e2ac52a3c94410d076}

Se si implementa l&#39;ora legale o un criterio simile per lo spostamento dell&#39;orologio, è necessario salvare il [!DNL .dst] file contenente le regole appropriate nel nome del profilo [!DNL \Dataset\Timezone] nel computer server di Data Workbench.

| Codice | Fuso orario | Offset da GMT |
|---|---|---|
| gmt | Greenwich Mean | 0 |
| test | Standard orientale | 5 |
| edt | Daylight orientale | 5 |
| cst | Standard centrale | 6 |
| cdt | Daylight centrale | 6 |
| mst | Standard di montagna | 7 |
| mdt | Luce diurna sulle montagne | 7 |
| pst | Standard del Pacifico | 8 |
| pdt | Daylight Pacifico | 8 |
