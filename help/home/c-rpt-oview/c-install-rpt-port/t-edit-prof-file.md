---
description: Per specificare i profili che si desidera rendere disponibili nel Report Portal (Portale dei rapporti), è necessario configurare il file profiles.xml.
title: Modificare il file Profiles.xml
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 7%

---

# Modificare il file Profiles.xml{#edit-the-profiles-xml-file}

Per specificare i profili che si desidera rendere disponibili nel Report Portal (Portale dei rapporti), è necessario configurare il file profiles.xml.

Il file [!DNL profiles.xml] si trova nella cartella designata per l&#39;output. Per impostazione predefinita si trova in \*PortalName*\PortalFiles\Output folder.

**Per aggiungere nomi di profilo al file profiles.xml**

1. Sul computer in cui è in esecuzione IIS, apri il file [!DNL profiles.xml] in un editor di testo come Blocco note.
1. Aggiungi un elemento di profilo e un tag per ogni elemento [!DNL Profile] nel portale, come nell’esempio seguente:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <PROFILES>
     <PROFILE>
       <NAME>Product Sales</NAME>
     </PROFILE>
     <PROFILE>
       <NAME>Product Marketing</NAME>
     </PROFILE>
   </PROFILES>
   ```

1. Salva e chiudi il file.
