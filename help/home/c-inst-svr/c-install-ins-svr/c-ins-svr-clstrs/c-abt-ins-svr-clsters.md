---
description: Un cluster di Insight Server è necessario quando la quantità di dati che desideri elaborare e rendere accessibili agli utenti di Insight e Report supera la capacità di un singolo Insight Server.
title: Informazioni sui cluster di Insight Server
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# Informazioni sui cluster di Insight Server{#about-insight-server-clusters}

{{eol}}

Un cluster di Insight Server è necessario quando la quantità di dati che desideri elaborare e rendere accessibili agli utenti di Insight e Report supera la capacità di un singolo Insight Server.

Impostando un [!DNL Insight Server] cluster, è possibile distribuire un singolo set di dati di analisi su più computer in un cluster per sfruttare la potenza di elaborazione di più computer [!DNL Insight Servers].

La prima fase dell&#39;attuazione di un [!DNL Insight Server] il cluster deve allocare [!DNL Insight Server] nel cluster. Il primo [!DNL Insight Server] la macchina che hai impostato è il tuo principale [!DNL Insight Server] (a volte indicato come principale [!DNL Insight Server]).

>[!NOTE]
>
>Se utilizzi un [!DNL Insight Server] File Server Unit (FSU), Adobe consiglia di configurare la FSU come master [!DNL Insight Server]. Per informazioni sulla configurazione di una FSU, consulta la *Guida alla configurazione del set di dati*.

Il maestro [!DNL Insight Server] gestisce la comunicazione tra gli altri [!DNL Insight Servers] nel cluster (server di elaborazione o, talvolta, server di query) e nelle istanze di [!DNL Insight] e [!DNL Report]. Per un dato set di dati, l’elaborazione dei file di registro avviene sul (uno o più) designato [!DNL Insight Servers] (master o elaborazione) come specificato nel [!DNL Insight Server] file di configurazione. Quando lavori in un ambiente cluster, [!DNL Insight] le installazioni sono configurate per accedere al master [!DNL Insight Server], ma le query possono essere gestite da uno qualsiasi dei [!DNL Insight Servers] all&#39;interno del cluster.

>[!NOTE]
>
>La **PAServer.cfg** file. Se desideri inviare i processi di clustering Predictive Analytics a Insight Server, dovrai configurare la [!DNL PAServer.cfg] file per la gestione degli invii di clustering lato server. Il profilo personalizzato deve ereditare il [!DNL PAServer.cfg] dal profilo Predictive Analytics ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Imposta un *Server principale* in questo file e salva il [!DNL PAServer.cfg] al sito di implementazione.
>
>
```
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```

>[!IMPORTANT]
>
>Le istruzioni del presente capitolo non si applicano alla creazione di un [!DNL Insight Server] cluster costituito da più di cinque (5) [!DNL Insight Servers]. Contatta l&#39;Adobe per ottenere i requisiti di sistema e le raccomandazioni di configurazione del profilo per cluster di dimensioni superiori a cinque [!DNL Insight Servers].
