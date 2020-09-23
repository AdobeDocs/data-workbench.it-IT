---
description: Passaggi per aggiornare la cartella Transform.
solution: Analytics
title: Aggiornamento di Transform
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---


# Aggiornamento di Transform{#upgrading-transform}

Passaggi per aggiornare la cartella Transform.

1. Aprite il [!DNL .zip] file per il pacchetto di [!DNL Insight Server] rilascio e aprite la [!DNL Profiles] cartella all’interno di tale [!DNL .zip] file.
1. Copiate la [!DNL Transform] cartella nella [!DNL Profiles] cartella della directory di [!DNL Insight Server] installazione. In questo modo viene sovrascritta la [!DNL Transform] cartella esistente.
1. Per ciascun profilo che eredita il [!DNL Transform] profilo, verificate che il [!DNL profile.cfg] file contenga una voce &quot;Trasforma&quot; nel vettore Directory.
La rielaborazione dei dati inizia dopo la sincronizzazione del profilo.
