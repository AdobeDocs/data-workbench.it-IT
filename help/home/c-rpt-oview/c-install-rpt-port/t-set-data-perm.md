---
description: Per abilitare Report Portal per la scrittura nel database contenente le informazioni necessarie per l'autenticazione degli utenti, è necessario impostare le autorizzazioni corrette per il database.
solution: Analytics
title: Impostare le autorizzazioni per il database
topic: Data workbench
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Impostare le autorizzazioni per il database{#set-permissions-for-the-database}

Per abilitare Report Portal per la scrittura nel database contenente le informazioni necessarie per l&#39;autenticazione degli utenti, è necessario impostare le autorizzazioni corrette per il database.

1. Nel computer in cui è in esecuzione IIS, andate a \*PortalName*\data\users.mdb.
1. Fare clic con il pulsante destro del mouse sul **[!UICONTROL users.mdb]** file e selezionare **[!UICONTROL Properties]**.
1. Nella [!DNL Security] scheda, in Gruppi o nomi utente, fate clic su **[!UICONTROL Users]**.
1. In [!DNL Permission for User], nella riga Scrivi, selezionare **[!UICONTROL Allow]**.
1. Fare clic **[!UICONTROL OK]** e chiudere la [!DNL Properties] finestra di dialogo.
