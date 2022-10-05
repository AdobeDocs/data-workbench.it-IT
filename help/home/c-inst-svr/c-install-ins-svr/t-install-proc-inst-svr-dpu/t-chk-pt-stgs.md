---
description: Per impostazione predefinita, Insight Server ascolta le porte 80 (per HTTP) e 443 (per HTTPS).
title: Controllo delle impostazioni della porta
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
exl-id: 924860e3-5afa-4c0f-bb7a-d38d5c1355b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---

# Controllo delle impostazioni della porta{#checking-the-port-settings}

{{eol}}

Per impostazione predefinita, Insight Server ascolta le porte 80 (per HTTP) e 443 (per HTTPS).

Se queste porte sono già allocate da un altro processo nel computer in cui è installato [!DNL Insight Server], utilizza la seguente procedura per modificare [!DNL Insight Server’s] assegnazioni di porte.

**Per modificare le assegnazioni delle porte**

1. Passa a [!DNL Components] nella directory in cui è stata installata [!DNL Insight Server].

   Esempio: [!DNL C:\Adobe\Server\Components]

1. Apri [!DNL Communications.cfg] in un editor di testo come Blocco note.
1. Individua le voci Porta e Porta SSL, come illustrato di seguito:

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

1. Se non si tratta delle porte desiderate [!DNL Insight Server] per utilizzare, modificare le assegnazioni delle porte, quindi salvare e chiudere il file.
