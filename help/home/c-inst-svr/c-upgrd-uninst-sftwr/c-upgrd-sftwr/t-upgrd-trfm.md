---
description: Passaggi per aggiornare la cartella Transform.
title: Aggiornamento di Transform
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# Aggiornamento di Transform{#upgrading-transform}

{{eol}}

Passaggi per aggiornare la cartella Transform.

1. Apri [!DNL .zip] per [!DNL Insight Server] e apri il pacchetto [!DNL Profiles] cartella [!DNL .zip] file.
1. Copia il [!DNL Transform] nella cartella [!DNL Profiles] nella cartella [!DNL Insight Server] directory di installazione. In questo modo si sovrascrive l&#39;esistente [!DNL Transform] cartella.
1. Per ogni profilo che eredita il [!DNL Transform] conferma che [!DNL profile.cfg] il file ha una voce &quot;Transform&quot; nel vettore Directory.
La rielaborazione dei dati inizia dopo la sincronizzazione del profilo.
