---
description: Per impostazione predefinita, Insight Server scrive il relativo set di dati (temp.db) nella stessa unità dei file di programma Insight Server.
title: Configurazione della posizione del set di dati (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# Configurazione della posizione del set di dati (temp.db){#configuring-the-location-of-the-dataset-temp-db}

{{eol}}

Per impostazione predefinita, Insight Server scrive il relativo set di dati (temp.db) nella stessa unità dei file di programma Insight Server.

Ad esempio, se installi [!DNL Insight Server] sull&#39;unità C, scrive il set di dati per guidare C.

Se vuoi [!DNL Insight Server] per mantenere il set di dati su un&#39;unità diversa o se la quantità di dati che si prevede di raccogliere richiede l&#39;utilizzo di più unità, è necessario aggiornare il [!DNL Disk Files.cfg] file per specificare la posizione desiderata [!DNL Insight Server] per scrivere [!DNL temp.db] file.

**Per configurare il percorso di temp.db**

1. Passa a [!DNL Components] nella directory in cui è stata installata [!DNL Insight Server].

   Esempio: [!DNL C:\Adobe\Server\Components]

1. Apri [!DNL Disk Files.cfg] in un editor di testo come Blocco note.

   Per impostazione predefinita, questo file contiene una singola voce nella struttura File disco come mostrato di seguito.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. Per modificare la posizione di [!DNL temp.db], modifica la definizione dei file di disco. L’esempio seguente illustra come modificare la configurazione per distribuire il [!DNL temp.db] file tra le unità C, D ed E:

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
   >Tenere presente l’uso delle barre rovesciate doppie nei nomi dei file indicati sopra. In [!DNL Insight Server] file di configurazione, il carattere barra rovesciata è un carattere escape. Viene utilizzato per esprimere sequenze di controllo speciali (ad esempio, \t per un carattere di tabulazione) nel testo. Per rappresentare una barra rovesciata effettiva, è necessario digitare la barra rovesciata due volte (ad esempio, \\) per sostituire la funzione escape. Questo si applica solo quando si modificano i file di configurazione in un editor di testo come Blocco note.
