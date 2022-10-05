---
description: Il passaggio finale consiste nell’eseguire il dashboard per la prima volta per consentirne l’inizializzazione.
title: Inizializzazione del dashboard
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---

# Inizializzazione del dashboard{#initializing-the-dashboard}

{{eol}}

Il passaggio finale consiste nell’eseguire il dashboard per la prima volta per consentirne l’inizializzazione.

1. Apri un browser web e immetti l’URL del sito appena distribuito (ad esempio, https://localhost/dashboard).
1. La connessione per la prima volta configurerà le tabelle del database, in modo che si possa verificare un leggero ritardo.
1. Le credenziali di accesso iniziali sono:

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. Al primo accesso, vai a **[!UICONTROL User]** > **[!UICONTROL Account Settings]** e seleziona **[!UICONTROL Change Password]** per modificare la password dell&#39;amministratore.

Installazione del dashboard completata. Se non lo hai già fatto, utilizza le istruzioni descritte nella sezione Preparazione Data Workbench di questa guida per configurare la comunicazione con i server di Data Workbench e per gestire utenti e gruppi.

>[!NOTE]
>
>Gli errori del dashboard e i registri di controllo si trovano nella [!DNL logs] all&#39;interno del percorso di installazione.

>[!NOTE]
>
>Se devi modificare l&#39;identità del pool di applicazioni in un account diverso, assicurati di concedere l&#39;accesso al database e di consentire all&#39;identità l&#39;accesso in lettura/scrittura al [!DNL logs] nel percorso di installazione.

>[!NOTE]
>
>Se devi modificare la stringa di connessione per il database, è sufficiente modificare il valore utilizzando il **[!UICONTROL IIS Management Console]**.
