---
description: Il passaggio finale consiste nell'eseguire il dashboard per la prima volta per consentirne l'inizializzazione.
solution: Analytics
title: Inizializzazione del dashboard
topic: Data workbench
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Inizializzazione del dashboard{#initializing-the-dashboard}

Il passaggio finale consiste nell&#39;eseguire il dashboard per la prima volta per consentirne l&#39;inizializzazione.

1. Aprite un browser Web e immettete l’URL del sito appena distribuito (ad esempio, http://localhost/dashboard).
1. La connessione per la prima volta configurerà le tabelle del database, in modo che si possa verificare un leggero ritardo.
1. Le credenziali di accesso iniziali sono:

* **[!UICONTROL Username]**: admin
* **[!UICONTROL Password]**: password

1. Al primo login, andate a **[!UICONTROL User]** > **[!UICONTROL Account Settings]** e selezionate **[!UICONTROL Change Password]** per cambiare la password dell&#39;amministratore.
>L&#39;installazione del dashboard ora è completa. Se non lo avete già fatto, usate le istruzioni dettagliate in >
><!-->
>Preparazione del lavoro dati>
>-->
>questa sezione descrive come configurare la comunicazione con i server workbench dati e gestire utenti e gruppi. >
>>[!NOTE]
>>
>>Gli errori del dashboard e i registri di controllo si trovano nella [!DNL logs] directory all&#39;interno del percorso di installazione.
>[!NOTE]
Se è necessario modificare l&#39;identità del pool di applicazioni in un account diverso, assicurarsi di concedere l&#39;accesso al database e concedere l&#39;accesso in lettura/scrittura dell&#39;identità alla [!DNL logs] cartella nel percorso di installazione.
>[!NOTE]
Se è necessario modificare la stringa di connessione per il database, è sufficiente modificare il valore utilizzando il **[!UICONTROL IIS Management Console]**.
>
>
>
