---
description: Formattare le istruzioni sui parametri basati su tempo in Insight Server.
title: Codici del fuso orario
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 4%

---

# Codici del fuso orario{#time-zone-codes}

Formattare le istruzioni sui parametri basati su tempo in Insight Server.

La maggior parte dei parametri basati sul tempo in [!DNL Insight Server] sono specificati nel seguente formato:

*Mese GG, AAAA HH:MM:SS Time Zone*

Esempio: 13 agosto 2013 22:30:00 EST

I fusi orari sono espressi in un formato del fuso orario indipendente dal sistema (ora universale coordinata) del seguente formato:

UTC +hhmm *ostruzioni*

Il segno (+) può essere un segno più (+) o meno (-) e *hhmm* è l&#39;offset dall&#39;UTC in ore e minuti. La variabile opzionale *dstrules* specifica un set di regole per implementare l&#39;ora legale o un criterio di spostamento dell&#39;orologio simile.

Se si specifica *dstrules*, un file delimitato da tabulazioni denominato *&lt; [!DNL dstrules]* [!DNL .dst] deve essere presente nella directory Dataset\TimeZone del profilo Base (per i file di configurazione non associati a un particolare set di dati) o del profilo del set di dati (per i file di configurazione specifici per un set di dati). Il file specifica un set di regole indipendente dal fuso orario per l’ora legale. Puoi avere diversi set di regole per diversi anni. Il file [!DNL DST.dst] fornito dall&#39;Adobe nel profilo Base specifica le regole standard statunitensi stabilite dal Energy Policy Act del 2005 (in vigore a partire dal 2007) e le regole statunitensi per gli anni precedenti.

Di seguito sono elencate le voci relative al fuso orario di esempio:

* Ora legale USA: Fuso orario = stringa: UTC -0500 DST
* Ora UTC senza offset e nessuna *dilatazione* (corrispondente a GMT): Fuso orario = stringa: UTC -0000

Quando si utilizza questo formato, il fuso orario del sistema delle macchine [!DNL Insight Server], [!DNL Insight] e [!DNL Report] non deve corrispondere al fuso orario specificato. Inoltre, tutti i profili di set di dati attivi su un computer [!DNL Insight Server] non devono avere la stessa impostazione di fuso orario.

La tabella seguente contiene l’elenco di codici che è possibile utilizzare per specificare i fusi orari nei parametri basati su tempo.

## Tabella del codice del fuso orario {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Se si implementa l&#39;ora legale o un criterio simile per lo spostamento dell&#39;orologio, è necessario salvare il file [!DNL .dst] contenente le regole appropriate nel computer *nome profilo*\Dataset\Timezone directory on the [!DNL Insight Server].

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
