---
description: Per specificare i profili che si desidera rendere disponibili in Report Portal, è necessario configurare il file profile.xml.
solution: Analytics
title: Modificare il file Profiles.xml
topic: Data workbench
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modificare il file Profiles.xml{#edit-the-profiles-xml-file}

Per specificare i profili che si desidera rendere disponibili in Report Portal, è necessario configurare il file profile.xml.

Il [!DNL profiles.xml] file risiede nella cartella designata per l’output. Per impostazione predefinita si trova in \*PortalName*\PortalFiles\Output folder.

**Per aggiungere nomi di profilo al file profile.xml**

1. Nel computer in cui è in esecuzione IIS, aprite il [!DNL profiles.xml] file in un editor di testo come Blocco note.
1. Aggiungi un elemento e un tag di profilo per ciascun [!DNL Profile] nel portale, come nell&#39;esempio seguente:

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

1. Salvate e chiudete il file.
