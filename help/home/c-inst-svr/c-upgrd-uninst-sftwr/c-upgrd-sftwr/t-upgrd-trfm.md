---
description: Passaggi per aggiornare la cartella Transform.
title: Aggiornamento di Transform
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# Aggiornamento di Transform{#upgrading-transform}

Passaggi per aggiornare la cartella Transform.

1. Apri il file [!DNL .zip] per il pacchetto di versione [!DNL Insight Server] e apri la cartella [!DNL Profiles] all’interno del file [!DNL .zip].
1. Copia la cartella [!DNL Transform] nella cartella [!DNL Profiles] nella directory di installazione [!DNL Insight Server]. In questo modo viene sovrascritta la cartella [!DNL Transform] esistente.
1. Per ogni profilo che eredita il profilo [!DNL Transform], verifica che il file [!DNL profile.cfg] abbia una voce &quot;Trasforma&quot; nel vettore Directory.
La rielaborazione dei dati inizia dopo la sincronizzazione del profilo.
