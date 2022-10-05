---
description: Formattare le istruzioni sui parametri basati su tempo in Insight Server.
title: Codici del fuso orario (Insight Server)
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 4%

---

# Codici del fuso orario{#time-zone-codes}

{{eol}}

Formattare le istruzioni sui parametri basati su tempo in Insight Server.

La maggior parte dei parametri basati sul tempo in [!DNL Insight Server] sono specificati nel formato seguente:

*Mese GG, AAAA HH:MM:TimeZone SS*

Esempio: 13 agosto 2013 22:30:00 EST

I fusi orari sono espressi in un formato del fuso orario indipendente dal sistema (ora universale coordinata) del seguente formato:

UTC + h *ostriche*

Il segno (+) può essere un segno più (+) o meno (-) e *eh* è l’offset da UTC in ore e minuti. Variabile opzionale *ostriche* specifica un insieme di regole per implementare l&#39;ora legale o un criterio di spostamento dell&#39;orologio simile.

Se si specifica *ostriche*, un file delimitato da tabulazioni denominato *&lt; [!DNL dstrules]>* [!DNL .dst] deve essere presente nella directory Dataset\TimeZone del profilo Base (per i file di configurazione non associati a un particolare set di dati) o del profilo di set di dati (per i file di configurazione specifici per un set di dati). Il file specifica un set di regole indipendente dal fuso orario per l’ora legale. Puoi avere diversi set di regole per diversi anni. La [!DNL DST.dst] il file fornito dall&#39;Adobe nel profilo Base specifica le regole standard statunitensi stabilite dalla legge sulla politica energetica del 2005 (in vigore a partire dal 2007) e le norme statunitensi per gli anni precedenti.

Di seguito sono elencate le voci relative al fuso orario di esempio:

* Ora legale USA: Fuso orario = stringa: UTC -0500 DST
* Ora UTC senza offset e nessuna *ostriche* (corrispondente a GMT): Fuso orario = stringa: UTC -0000

Quando si utilizza questo formato, il fuso orario del sistema di [!DNL Insight Server], [!DNL Insight]e [!DNL Report] le macchine non devono essere uguali al fuso orario specificato. Inoltre, tutti i profili di set di dati attivi su un [!DNL Insight Server] la macchina non deve avere lo stesso fuso orario impostato.

La tabella seguente contiene l’elenco di codici che è possibile utilizzare per specificare i fusi orari nei parametri basati su tempo.

## Tabella dei codici del fuso orario {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Se si implementa l&#39;ora legale o un criterio simile per lo spostamento dell&#39;orologio, è necessario salvare il [!DNL .dst] file contenente le regole appropriate nel *nome profilo*\Dataset\Timezone directory in [!DNL Insight Server] macchina.

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
