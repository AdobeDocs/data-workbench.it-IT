---
description: Per modificare il server di Data Workbench con cui comunica un Sensor (il server di destinazione), devi modificare il file txlogd.conf su ciascuno dei server web in cui è installato Sensor.
title: Modifica del server target di Data Workbench
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# Modifica del server target di Data Workbench{#changing-the-target-data-workbench-server}

{{eol}}

Per modificare il server di Data Workbench con cui comunica un Sensor (il server di destinazione), devi modificare il file txlogd.conf su ciascuno dei server web in cui è installato Sensor.

**Per cambiare destinazione[!DNL data workbench server]**

1. Arrestare sia il server di destinazione originale che il nuovo server di destinazione.
1. Copia il più recente [!DNL .vsl] dal server di destinazione originale al nuovo server di destinazione. Quando si riavvia il nuovo server di destinazione in un passaggio successivo, questo determina l&#39;esecuzione di tutte le nuove [!DNL Sensor] dati da aggiungere all&#39;attuale, esistente [!DNL .vsl] anziché creare un nuovo file [!DNL .vsl] file. A questo scopo, completa i seguenti passaggi:

   1. Nel server di destinazione originale, seleziona [!DNL \Logs] nella cartella [!DNL data workbench server] directory di installazione.

   1. Copia il più recente [!DNL .vsl] nella cartella.
   1. Nel nuovo server di destinazione, seleziona [!DNL \Logs] nella cartella [!DNL data workbench server] directory di installazione e incollare [!DNL .vsl] in questa cartella.

1. Su uno dei server web su cui [!DNL Sensor] è installato, apre e modifica il [!DNL txlogd.conf] file. A questo scopo, completa i seguenti passaggi:

   1. Sfoglia il [!DNL Sensor] directory di installazione e aprire [!DNL txlogd.conf] in un editor di testo.

   1. Individuare il parametro ServerAddress e modificarlo per riflettere l&#39;indirizzo del nuovo server di destinazione.
   1. Salva e chiudi il file.

1. Ripeti i passaggi 2-3 su tutti i server web rimanenti su cui [!DNL Sensor] è installato.
1. Riavvia il server di destinazione originale (se deve ancora essere utilizzato) e il nuovo server di destinazione.
1. I dati inizieranno a essere trasmessi al nuovo server di destinazione specificato.
