---
description: Prima che il dashboard possa funzionare, è necessario consentire l'accesso a SQL Server.
title: Configurazione di SQL Server
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# Configurazione di SQL Server{#configuring-the-sql-server}

Prima che il dashboard possa funzionare, è necessario consentire l&#39;accesso a SQL Server.

1. Aprire SQL Management Studio come amministratore.
1. Aggiungi un nuovo accesso facendo clic con il pulsante destro del mouse su **[!UICONTROL Logins]** e selezionando **[!UICONTROL New Login]**.
1. Immettere il nome completo dell&#39;identità del pool di applicazioni.

   Per impostazione predefinita, l&#39;identità del pool di applicazioni viene denominata in base al pool di applicazioni. Se scegli `dashboard`, l&#39;identità verrà denominata `IIS AppPool\dashboard`. 1. Seleziona **[!UICONTROL Server Roles]** e controlla il ruolo **[!UICONTROL dbcreator]**.
1. Fai clic su **[!UICONTROL OK]** per aggiungere il nuovo utente.
