---
description: Se Insight non è in grado di connettersi ai server di Insight utilizzando le impostazioni specificate, in Server Manager viene visualizzato un nodo rosso.
title: Risoluzione dei problemi di connessione
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Risoluzione dei problemi di connessione{#connection-troubleshooting}

Se Insight non è in grado di connettersi ai server di Insight utilizzando le impostazioni specificate, in Server Manager viene visualizzato un nodo rosso.

Ciò potrebbe verificarsi, ad esempio, se la connessione viene configurata in modo errato o se non si dispone dell&#39;autorizzazione per visualizzare lo [!DNL Insight Server’s] stato.

**Per determinare il motivo per cui Insight non è in grado di stabilire una connessione**

1. Fare clic con il pulsante destro del mouse sul nodo del server rosso e scegliere **[!UICONTROL Detailed Status]**.
1. Nell&#39; [!DNL Detailed Status] interfaccia, fare clic **[!UICONTROL Network Connections]** ed espandere gli elementi numerati. Il [!DNL Status] parametro fornisce informazioni sul motivo per cui Insight non è in grado di stabilire una connessione:

   * Un codice di stato negli anni 500 indica un errore di configurazione.
   * Un codice di stato 403 in genere indica che non disponete dell&#39;autorizzazione per visualizzare lo stato del server.

Potete visualizzare informazioni di stato aggiuntive nel [!DNL insight.log] file. Questo file di registro si trova nella [!DNL Trace] cartella nella directory in cui è installato Insight. Per visualizzare il file, apritelo in un editor di testo come Blocco note.

Per assistenza nella comprensione delle informazioni contenute nel [!DNL insight.log] file, contattate prima l&#39;amministratore di sistema. Per ulteriore assistenza, contatta l’Assistenza clienti Adobe.
