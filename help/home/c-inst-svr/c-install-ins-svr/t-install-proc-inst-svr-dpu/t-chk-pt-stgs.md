---
description: Per impostazione predefinita, Insight Server ascolta le porte 80 (per HTTP) e 443 (per HTTPS).
solution: Insight
title: Controllo delle impostazioni della porta
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Controllo delle impostazioni della porta{#checking-the-port-settings}

Per impostazione predefinita, Insight Server ascolta le porte 80 (per HTTP) e 443 (per HTTPS).

Se queste porte sono già allocate da un altro processo nel computer in cui è installato [!DNL Insight Server], utilizzare la procedura seguente per modificare le assegnazioni delle [!DNL Insight Server’s] porte.

**Per modificare le assegnazioni delle porte**

1. Andate alla [!DNL Components] cartella nella directory in cui avete installato [!DNL Insight Server].

   Esempio: [!DNL C:\Adobe\Server\Components]

1. Aprite il [!DNL Communications.cfg] file in un editor di testo come Blocco note.
1. Individuate le voci Porta e Porta SSL, come illustrato di seguito:

   ```
   component = CommServer: 
     Access Control File = Path: Access Control\\Access Control.cfg
     Access Log Directory = string: P:\\Audit\\
     IP Interface = string: 
     Port = int: 80
     SSL Port = int: 443
     Servers = vector: 17 items
       0 = InitServer: 
         Client Type = string: Sensor
         URI = string: /SensorInit.vsp
     . . .
   ```

1. Se non si tratta delle porte che desiderate [!DNL Insight Server] utilizzare, modificate le assegnazioni delle porte, quindi salvate e chiudete il file.
