---
description: Informazioni sulle colonne del livello del punto elemento.
title: Formato del file di ricerca del punto elemento
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
exl-id: da81da9e-0567-4f3a-bc0d-ab6c5e4a23b7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 6%

---

# Formato del file di ricerca del punto elemento{#element-point-lookup-file-format}

Informazioni sulle colonne del livello del punto elemento.

Il file di ricerca a livello di punto elemento deve contenere almeno le tre colonne seguenti:

* **[!DNL Key]colonna:** questa colonna deve contenere dati chiave comuni, che consentono al server di Data Workbench di collegare i dati nel file di ricerca a quelli nel set di dati. La colonna [!DNL Key] deve essere la prima colonna del file di ricerca. Ogni riga in questa colonna identifica un elemento della dimensione.

* **[!DNL Longitude]colonna:** questa colonna deve contenere la longitudine di ogni punto dati della  [!DNL Key] colonna.

* **[!DNL Latitude]colonna:** questa colonna deve contenere la latitudine di ciascun punto dati della  [!DNL Key] colonna.

* **[!DNL Name]Colonna:**  (facoltativo). Se desideri specificare un nome da visualizzare sulla mappa per ogni punto dati, puoi includere una colonna [!DNL Name] nel file di ricerca.

Ogni riga nel file di ricerca [!DNL Zip Points.txt] contiene un codice ZIP nella prima colonna seguito da longitudine, latitudine e nome della città associato.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```
