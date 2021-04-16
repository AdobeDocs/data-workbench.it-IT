---
description: Per rilevare gli errori di sistema e di applicazione il prima possibile e risolverli prima che causino problemi o interruzioni gravi, è necessario monitorare regolarmente i registri eventi.
title: Monitoraggio degli eventi alla ricerca di errori
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
exl-id: 88f48594-5c73-4ae3-8014-b8543e689426
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 5%

---

# Monitoraggio degli eventi alla ricerca di errori{#monitoring-events-for-errors}

Per rilevare gli errori di sistema e di applicazione il prima possibile e risolverli prima che causino problemi o interruzioni gravi, è necessario monitorare regolarmente i registri eventi.

**Frequenza consigliata:** ogni 5-10 minuti

Per monitorare i prodotti software del server di Adobe, è possibile impostare lo strumento di gestione automatizzata per monitorare il registro eventi per verificare la presenza di errori con l&#39;Adobe di origine e quindi avvisare il personale appropriato per i problemi che possono richiedere l&#39;intervento.

In Windows, i messaggi di errore dell&#39;applicazione vengono inviati al Registro eventi dell&#39;applicazione in Windows, a cui è possibile accedere utilizzando il Visualizzatore eventi di Windows. In Unix, i messaggi di errore dell&#39;applicazione vengono inviati al registro di sistema Unix utilizzando la funzione LOG_DAEMON.

**Per aprire il Visualizzatore eventi di Windows**

* Fai clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.
