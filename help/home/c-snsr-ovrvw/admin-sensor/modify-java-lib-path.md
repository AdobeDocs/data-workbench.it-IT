---
description: Istruzioni per l'aggiunta di visual_sciences.dll al percorso della libreria Java Tomcat.
title: Modifica del percorso della libreria Java
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
exl-id: bd853d95-3f44-4860-9965-c3210ec4adcf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 12%

---

# Modifica del percorso della libreria Java{#modify-the-java-library-path}

{{eol}}

Istruzioni per l&#39;aggiunta di visual_sciences.dll al percorso della libreria Java Tomcat.

1. Sul server Windows, passare alla directory di installazione Tomcat. (Tomcat > bin)
1. Sotto la cartella bin, eseguire Tomcat9w.exe (gestore di servizio daemon comune).

Nella scheda Java, sotto Opzioni Java, aggiungi una nuova riga:

```
-Djava.library.path=C:\Sensor directory
```

Dove file C:\Sensor directory is the directory containing the visual_sciences.dll .
