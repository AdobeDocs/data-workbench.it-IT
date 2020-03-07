---
description: Per rilevare gli errori di sistema e di applicazione il prima possibile e risolverli prima che causino problemi o interruzioni gravi, è necessario monitorare regolarmente i registri eventi.
solution: Insight
title: Monitoraggio degli eventi per gli errori
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Monitoraggio degli eventi per gli errori{#monitoring-events-for-errors}

Per rilevare gli errori di sistema e di applicazione il prima possibile e risolverli prima che causino problemi o interruzioni gravi, è necessario monitorare regolarmente i registri eventi.

**Frequenza consigliata:** Ogni 5-10 minuti

Per monitorare i prodotti software del server Adobe, è possibile impostare lo strumento di gestione automatizzata per monitorare la presenza di errori nel registro eventi con l&#39;origine &quot;Adobe&quot; e avvisare il personale appropriato di eventuali problemi che richiedono l&#39;intervento.

In Windows, i messaggi di errore dell&#39;applicazione vengono inviati al registro eventi applicazione in Windows, a cui è possibile accedere mediante il visualizzatore eventi di Windows. In Unix, i messaggi di errore dell&#39;applicazione vengono inviati al syslog Unix utilizzando la funzione LOG_DAEMON.

**Per aprire il visualizzatore eventi di Windows**

* Fai clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

