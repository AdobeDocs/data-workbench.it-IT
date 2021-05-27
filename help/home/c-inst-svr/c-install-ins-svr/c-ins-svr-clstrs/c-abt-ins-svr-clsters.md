---
description: Un cluster di Insight Server è necessario quando la quantità di dati che desideri elaborare e rendere accessibili agli utenti di Insight e Report supera la capacità di un singolo Insight Server.
title: Informazioni sui cluster di Insight Server
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# Informazioni sui cluster di Insight Server{#about-insight-server-clusters}

Un cluster di Insight Server è necessario quando la quantità di dati che desideri elaborare e rendere accessibili agli utenti di Insight e Report supera la capacità di un singolo Insight Server.

Impostando un cluster [!DNL Insight Server], puoi distribuire un singolo set di dati di analisi su più computer in un cluster per sfruttare la potenza di elaborazione di più [!DNL Insight Servers].

Il primo passo nell&#39;implementazione di un cluster [!DNL Insight Server] è quello di allocare i computer [!DNL Insight Server] nel cluster. Il primo [!DNL Insight Server] computer configurato è il tuo principale [!DNL Insight Server] (a volte indicato come principale [!DNL Insight Server]).

>[!NOTE]
>
>Se si utilizza una [!DNL Insight Server] File Server Unit (FSU), Adobe consiglia di configurare la FSU come master [!DNL Insight Server]. Per informazioni sulla configurazione di una FSU, vedere la *Guida alla configurazione del set di dati*.

Il master [!DNL Insight Server] gestisce la comunicazione tra gli altri [!DNL Insight Servers] nel cluster (denominati server di elaborazione o, talvolta, server di query) e le istanze di [!DNL Insight] e [!DNL Report]. Per un dato set di dati, l’elaborazione dei file di registro avviene sul (uno o più) designato [!DNL Insight Servers] (master o elaborazione) come specificato nei file di configurazione [!DNL Insight Server]. Quando si lavora in un ambiente cluster, le installazioni [!DNL Insight] sono configurate per accedere al master [!DNL Insight Server], ma le query possono essere gestite da qualsiasi [!DNL Insight Servers] all&#39;interno del cluster.

>[!NOTE]
>
>Il file **PAServer.cfg**. Se desideri inviare i lavori di clustering Predictive Analytics a Insight Server, dovrai configurare il file [!DNL PAServer.cfg] per la gestione degli invii di clustering lato server. Il profilo personalizzato deve ereditare il valore [!DNL PAServer.cfg] dal profilo Predictive Analytics ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Imposta un *server principale* in questo file e salva il [!DNL PAServer.cfg] nel sito di implementazione.
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
>Le istruzioni contenute in questo capitolo non si applicano alla creazione di un cluster [!DNL Insight Server] costituito da più di cinque (5) [!DNL Insight Servers]. Contatta l&#39;Adobe per ottenere i requisiti di sistema e le raccomandazioni di configurazione del profilo per cluster di dimensioni superiori a cinque [!DNL Insight Servers].
