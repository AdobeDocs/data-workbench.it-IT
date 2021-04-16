---
description: Per modificare il server di Data Workbench con cui comunica un Sensor (il server di destinazione), devi modificare il file txlogd.conf su ciascuno dei server web in cui è installato Sensor.
title: Modifica del server target di Data Workbench
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# Modifica del server target di Data Workbench{#changing-the-target-data-workbench-server}

Per modificare il server di Data Workbench con cui comunica un Sensor (il server di destinazione), devi modificare il file txlogd.conf su ciascuno dei server web in cui è installato Sensor.

**Per cambiare destinazione[!DNL data workbench server]**

1. Arrestare sia il server di destinazione originale che il nuovo server di destinazione.
1. Copia il file [!DNL .vsl] più recente dal server di destinazione originale al nuovo server di destinazione. Quando si riavvia il nuovo server di destinazione in un passaggio successivo, tutti i nuovi dati [!DNL Sensor] vengono aggiunti al file [!DNL .vsl] esistente e non vengono creati nuovi file [!DNL .vsl]. A questo scopo, completa i seguenti passaggi:

   1. Sul server di destinazione originale, individua la cartella [!DNL \Logs] nella directory di installazione [!DNL data workbench server].

   1. Copia il file [!DNL .vsl] più recente nella cartella.
   1. Sul nuovo server di destinazione, individua la cartella [!DNL \Logs] nella directory di installazione [!DNL data workbench server] e incolla il file [!DNL .vsl] in questa cartella.

1. In uno dei server web in cui è installato [!DNL Sensor], apri e modifica il file [!DNL txlogd.conf]. A questo scopo, completa i seguenti passaggi:

   1. Individua la directory di installazione [!DNL Sensor] e apri il file [!DNL txlogd.conf] in un editor di testo.

   1. Individuare il parametro ServerAddress e modificarlo per riflettere l&#39;indirizzo del nuovo server di destinazione.
   1. Salva e chiudi il file.

1. Ripetere i passaggi da 2 a 3 su tutti i server Web rimanenti in cui è installato [!DNL Sensor].
1. Riavvia il server di destinazione originale (se deve ancora essere utilizzato) e il nuovo server di destinazione.
1. I dati inizieranno a essere trasmessi al nuovo server di destinazione specificato.
