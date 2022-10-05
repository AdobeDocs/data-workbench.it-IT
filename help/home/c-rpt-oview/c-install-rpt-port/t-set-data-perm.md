---
description: Per abilitare Report Portal alla scrittura nel database contenente le informazioni necessarie per l'autenticazione degli utenti, è necessario impostare le autorizzazioni appropriate per il database.
title: Impostare le autorizzazioni per il database
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# Impostare le autorizzazioni per il database{#set-permissions-for-the-database}

{{eol}}

Per abilitare Report Portal alla scrittura nel database contenente le informazioni necessarie per l&#39;autenticazione degli utenti, è necessario impostare le autorizzazioni appropriate per il database.

1. Nel computer in cui è in esecuzione IIS, passare a \*PortalName*\data\users.mdb.
1. Fai clic con il pulsante destro del mouse sul pulsante **[!UICONTROL users.mdb]** e seleziona **[!UICONTROL Properties]**.
1. Sulla [!DNL Security] in Gruppi o nomi utente fare clic su **[!UICONTROL Users]**.
1. In [!DNL Permission for User], nella riga Scrivi, seleziona **[!UICONTROL Allow]**.
1. Fai clic su **[!UICONTROL OK]** e chiudere [!DNL Properties] finestra di dialogo.
