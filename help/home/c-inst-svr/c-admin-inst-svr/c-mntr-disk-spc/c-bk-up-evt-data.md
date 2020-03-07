---
description: I dati dell'evento devono essere sottoposti a backup tutti i giorni utilizzando i normali sistemi di backup e le procedure di disaster recovery aziendali.
solution: Insight
title: Backup Dei Dati Dell'Evento
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Backup Dei Dati Dell&#39;Evento{#backing-up-event-data}

I dati dell&#39;evento devono essere sottoposti a backup tutti i giorni utilizzando i normali sistemi di backup e le procedure di disaster recovery aziendali.

**Frequenza consigliata:** Giornaliero

[!DNL Insight Server] inizia nuovi file di registro alle 12:00 GMT al giorno. Adobe consiglia di eseguire il backup dei file di registro ogni giorno poco dopo le ore 12:00 GMT, in modo da acquisire tutti i dati del giorno precedente. Ad esempio, il backup di tutti i file di registro alle 12:05 AM GMT del 15 dicembre acquisisce tutti i dati dal 14 dicembre. [!DNL Insight Server] non deve essere arrestato durante il backup dei file di registro e tutte le funzionalità rimangono disponibili.

## Backup di integrazione, sistema operativo, output e dati di sistema {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Frequenza consigliata:** Giornaliero

Il backup dei dati di integrazione, sistema operativo, output e sistema deve essere effettuato regolarmente e con diligenza utilizzando i normali sistemi di backup e disaster recovery aziendali.