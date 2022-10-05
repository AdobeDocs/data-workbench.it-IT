---
description: Se Insight non è in grado di connettersi a Insight Server utilizzando le impostazioni specificate, in Server Manager viene visualizzato un nodo rosso.
title: Risoluzione dei problemi di connessione
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
exl-id: 7938d4d6-e1ab-46d9-9ccb-cf79677c5688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 2%

---

# Risoluzione dei problemi di connessione{#connection-troubleshooting}

{{eol}}

Se Insight non è in grado di connettersi a Insight Server utilizzando le impostazioni specificate, in Server Manager viene visualizzato un nodo rosso.

Ciò potrebbe verificarsi, ad esempio, se la connessione viene configurata in modo errato o se non si dispone dell&#39;autorizzazione per visualizzare il [!DNL Insight Server’s] stato.

**Per determinare il motivo per cui Insight non è in grado di stabilire una connessione**

1. Fai clic con il pulsante destro del mouse sul nodo del server rosso e fai clic su **[!UICONTROL Detailed Status]**.
1. In [!DNL Detailed Status] interfaccia, fai clic su **[!UICONTROL Network Connections]** ed espandere gli elementi numerati. La [!DNL Status] Il parametro fornisce informazioni sul motivo per cui Insight non è in grado di stabilire una connessione:

   * Un codice di stato nel 500 indica un errore di configurazione.
   * Un codice di stato 403 in genere indica che non si dispone dell&#39;autorizzazione per visualizzare lo stato del server.

È possibile visualizzare informazioni aggiuntive sullo stato nel [!DNL insight.log] file. Questo file di log si trova nella [!DNL Trace] nella directory in cui è stato installato Insight. Per visualizzare il file, aprilo in un editor di testo come Blocco note.

Se hai bisogno di assistenza per comprendere le informazioni nel [!DNL insight.log] prima di tutto contattare l&#39;amministratore di sistema. Se hai bisogno di ulteriore assistenza, contatta l’Assistenza clienti Adobe.
