---
description: Per modificare il server workbench dati con il quale un sensore comunica (il server di destinazione), è necessario modificare il file txlogd.conf su ciascuno dei server Web in cui è installato Sensor.
solution: Analytics
title: Modifica del server target di Data Workbench
uuid: 931d376d-8622-4858-8290-19ce91538570
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---


# Modifica del server target di Data Workbench{#changing-the-target-data-workbench-server}

Per modificare il server workbench dati con il quale un sensore comunica (il server di destinazione), è necessario modificare il file txlogd.conf su ciascuno dei server Web in cui è installato Sensor.

**Per passare alla destinazione[!DNL data workbench server]**

1. Arrestate sia il server di destinazione originale che il nuovo server di destinazione.
1. Copiate il [!DNL .vsl] file più recente dal server di destinazione originale al nuovo server di destinazione. Quando si riavvia il nuovo server di destinazione in un passaggio successivo, tutti i nuovi [!DNL Sensor] dati vengono aggiunti al [!DNL .vsl] file corrente esistente invece di creare un nuovo [!DNL .vsl] file. Per eseguire questa operazione, completare i seguenti passaggi:

   1. Nel server di destinazione originale, individuate la [!DNL \Logs] cartella nella directory di [!DNL data workbench server] installazione.

   1. Copiate il [!DNL .vsl] file più recente nella cartella.
   1. Nel nuovo server di destinazione, individuate la [!DNL \Logs] cartella nella directory di [!DNL data workbench server] installazione e incollate il [!DNL .vsl] file in questa cartella.

1. In uno dei server Web in cui [!DNL Sensor] è installato, aprire e modificare il [!DNL txlogd.conf] file. Per eseguire questa operazione, completare i seguenti passaggi:

   1. Individuate la directory di [!DNL Sensor] installazione e aprite il [!DNL txlogd.conf] file in un editor di testo.

   1. Individuate il parametro ServerAddress e modificatelo per riflettere l&#39;indirizzo del nuovo server di destinazione.
   1. Salvate e chiudete il file.

1. Ripetere i passaggi da 2 a 3 su tutti i server Web rimanenti su cui [!DNL Sensor] è installato.
1. Riavviate il server di destinazione originale (se deve ancora essere utilizzato) e il nuovo server di destinazione.
1. I dati inizieranno a essere trasmessi al nuovo server di destinazione specificato.
