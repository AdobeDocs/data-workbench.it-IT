---
description: Istruzioni per l'aggiunta di visual_sciences.dll al percorso della libreria Tomcat java.
title: Modifica del percorso della libreria Java
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modifica del percorso della libreria Java{#modify-the-java-library-path}

Istruzioni per l&#39;aggiunta di visual_sciences.dll al percorso della libreria Tomcat java.

1. Nel server Windows, andate alla directory di installazione Tomcat. (Tomcat > bin)
1. In cartella bin, eseguire Tomcat9w.exe (comune gestore di servizi daemon).

Nella scheda Java, in Opzioni Java, aggiungere una nuova riga:

```
-Djava.library.path=C:\Sensor directory
```

Dove C:\Sensor directory is the directory containing the visual_sciences.dll il file.
