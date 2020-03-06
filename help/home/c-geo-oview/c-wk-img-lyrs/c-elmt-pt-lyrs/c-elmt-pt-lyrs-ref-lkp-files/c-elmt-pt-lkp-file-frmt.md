---
description: Informazioni sulle colonne del livello del punto elemento.
solution: Analytics
title: Formato file di ricerca punto elemento
topic: Data workbench
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Formato file di ricerca punto elemento{#element-point-lookup-file-format}

Informazioni sulle colonne del livello del punto elemento.

Il file di ricerca del livello del punto elemento deve contenere almeno tre colonne:

* **[!DNL Key]colonna:**Questa colonna deve contenere dati chiave comuni, che consentono al server workbench dati di collegare i dati nel file di ricerca a quelli nel dataset. La[!DNL Key]colonna deve essere la prima colonna del file di ricerca. Ogni riga in questa colonna identifica un elemento della dimensione.

* **[!DNL Longitude]colonna:**Questa colonna deve contenere la longitudine per ogni punto dati della[!DNL Key]colonna.

* **[!DNL Latitude]colonna:**Questa colonna deve contenere la latitudine per ogni punto dati della[!DNL Key]colonna.

* **[!DNL Name]colonna:**(Facoltativo). Se si desidera specificare un nome da visualizzare sulla mappa per ogni punto dati, è possibile includere una[!DNL Name]colonna nel file di ricerca.

Ogni riga del file di [!DNL Zip Points.txt] ricerca contiene un CAP nella prima colonna seguito da longitudine, latitudine e nome città associato.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

