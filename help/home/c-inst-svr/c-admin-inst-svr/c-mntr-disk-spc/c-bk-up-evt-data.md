---
description: I dati degli eventi devono essere sottoposti a backup quotidianamente utilizzando i normali sistemi di backup e le procedure di disaster recovery della società.
title: Backup dei dati dell’evento
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
exl-id: 5afeb3a2-a2e7-4155-8fb9-1abc9c22c3c6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 5%

---

# Backup dei dati dell’evento{#backing-up-event-data}

I dati degli eventi devono essere sottoposti a backup quotidianamente utilizzando i normali sistemi di backup e le procedure di disaster recovery della società.

**Frequenza consigliata:** giornaliera

[!DNL Insight Server] inizia i nuovi file di log alle 12:00 GMT giornaliere. L’Adobe consiglia di eseguire il backup dei file di registro ogni giorno poco dopo le 12:00 GMT in modo da acquisire tutti i dati del giorno precedente. Ad esempio, il backup di tutti i file di registro alle 12:05 GMT del 15 dicembre acquisisce tutti i dati dal 14 dicembre. [!DNL Insight Server] non deve essere arrestato durante i backup dei file di registro e tutte le funzionalità rimangono disponibili.

## Backup di integrazione, sistemi operativi, output e dati di sistema {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Frequenza consigliata:** giornaliera

L&#39;integrazione, il sistema operativo, l&#39;output e i dati di sistema devono essere sottoposti a backup regolare e accurato utilizzando i normali sistemi di backup e disaster recovery della tua azienda.
