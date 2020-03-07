---
description: Prima che il dashboard possa funzionare, è necessario consentirgli di accedere a SQL Server.
solution: Analytics
title: Configurazione di SQL Server
topic: Data workbench
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurazione di SQL Server{#configuring-the-sql-server}

Prima che il dashboard possa funzionare, è necessario consentirgli di accedere a SQL Server.

1. Aprite SQL Management Studio come amministratore.
1. Aggiungete un nuovo login facendo clic con il pulsante destro del mouse **[!UICONTROL Logins]** e selezionando **[!UICONTROL New Login]**.
1. Immettere il nome completo dell&#39;identità del pool di applicazioni.

   Per impostazione predefinita, l&#39;identità del pool di applicazioni è denominata in base al pool di applicazioni. Se scegliete `dashboard`, l&#39;identità verrà denominata `IIS AppPool\dashboard`. 1. Selezionare **[!UICONTROL Server Roles]** e controllare il **[!UICONTROL dbcreator]** ruolo.
1. Fate clic **[!UICONTROL OK]** per aggiungere il nuovo utente.
