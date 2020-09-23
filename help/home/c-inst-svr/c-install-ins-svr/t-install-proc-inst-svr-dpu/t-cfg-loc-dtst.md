---
description: Per impostazione predefinita, Insight Server scrive il relativo dataset (temp.db) nella stessa unità dei file del programma Insight Server.
solution: Analytics
title: Configurazione della posizione del set di dati (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---


# Configurazione della posizione del set di dati (temp.db){#configuring-the-location-of-the-dataset-temp-db}

Per impostazione predefinita, Insight Server scrive il relativo dataset (temp.db) nella stessa unità dei file del programma Insight Server.

Ad esempio, se si installa [!DNL Insight Server] sull&#39;unità C, il dataset viene scritto nell&#39;unità C.

Se si desidera [!DNL Insight Server] mantenere il dataset su un&#39;unità diversa, o se la quantità di dati che si prevede di raccogliere richiede l&#39;uso di più unità, è necessario aggiornare il [!DNL Disk Files.cfg] file per specificare dove si desidera [!DNL Insight Server] scrivere il [!DNL temp.db] file.

**Per configurare il percorso di temp.db**

1. Andate alla [!DNL Components] cartella nella directory in cui avete installato [!DNL Insight Server].

   Esempio: [!DNL C:\Adobe\Server\Components]

1. Aprite il [!DNL Disk Files.cfg] file in un editor di testo come Blocco note.

   Per impostazione predefinita, questo file contiene una sola voce nella struttura File disco, come illustrato di seguito.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. Per cambiare la posizione di [!DNL temp.db], modificare la definizione dei file del disco. L&#39;esempio seguente illustra come modificare la configurazione per distribuire il [!DNL temp.db] file tra le unità C, D ed E:

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 3 items
       0 = string: C:\\Temp\\temp.db
       1 = string: D:\\Temp\\temp.db
       2 = string: E:\\Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

   >[!NOTE]
   >
   >Tenete presente l’uso delle doppie barre rovesciate nei nomi dei file riportati sopra. Nei file di [!DNL Insight Server] configurazione, il carattere barra rovesciata è un carattere escape. Viene utilizzato per esprimere sequenze di controllo speciali (ad esempio, \t per un carattere di tabulazione) nel testo. Per rappresentare una barra rovesciata effettiva, è necessario digitare la barra rovesciata due volte (ad esempio \\) per ignorare la funzione escape. Ciò si applica solo quando si modificano i file di configurazione in un editor di testo come Blocco note.

