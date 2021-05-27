---
description: Per abilitare Report Portal alla scrittura nel database contenente le informazioni necessarie per l'autenticazione degli utenti, è necessario impostare le autorizzazioni appropriate per il database.
title: Impostare le autorizzazioni per il database
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# Impostare le autorizzazioni per il database{#set-permissions-for-the-database}

Per abilitare Report Portal alla scrittura nel database contenente le informazioni necessarie per l&#39;autenticazione degli utenti, è necessario impostare le autorizzazioni appropriate per il database.

1. Nel computer in cui è in esecuzione IIS, passa a \*PortalName*\data\users.mdb.
1. Fai clic con il pulsante destro del mouse sul file **[!UICONTROL users.mdb]** e seleziona **[!UICONTROL Properties]**.
1. Nella scheda [!DNL Security], in Gruppi o nomi utente fare clic su **[!UICONTROL Users]**.
1. In [!DNL Permission for User], nella riga Scrivi, selezionare **[!UICONTROL Allow]**.
1. Fare clic su **[!UICONTROL OK]** e chiudere la finestra di dialogo [!DNL Properties].
