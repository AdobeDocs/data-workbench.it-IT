---
description: Per rilevare gli errori di sistema e di applicazione il prima possibile e risolverli prima che causino problemi o interruzioni gravi, è necessario monitorare regolarmente i registri eventi.
solution: Analytics
title: Monitoraggio degli eventi alla ricerca di errori
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 6%

---


# Monitoraggio degli eventi alla ricerca di errori{#monitoring-events-for-errors}

Per rilevare gli errori di sistema e di applicazione il prima possibile e risolverli prima che causino problemi o interruzioni gravi, è necessario monitorare regolarmente i registri eventi.

**Frequenza consigliata:** Ogni 5-10 minuti

Per monitorare i prodotti software  server di Adobe, è possibile impostare lo strumento di gestione automatizzata per monitorare il registro eventi in caso di errori con il &quot;Adobe &quot; di origine e quindi avvisare il personale appropriato in caso di problemi che potrebbero richiedere l&#39;intervento.

In Windows, i messaggi di errore dell&#39;applicazione vengono inviati al registro eventi applicazione in Windows, a cui è possibile accedere mediante il visualizzatore eventi di Windows. In Unix, i messaggi di errore dell&#39;applicazione vengono inviati al syslog Unix utilizzando la funzione LOG_DAEMON.

**Per aprire il visualizzatore eventi di Windows**

* Fai clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

