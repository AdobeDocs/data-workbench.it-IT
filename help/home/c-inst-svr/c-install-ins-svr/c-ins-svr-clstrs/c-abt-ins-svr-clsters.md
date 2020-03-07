---
description: È necessario un cluster di Insight Server quando la quantità di dati da elaborare e rendere accessibili agli utenti di Insight e Report supera la capacità di un singolo server Insight.
solution: Insight
title: Informazioni su cluster di server Insight
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informazioni su cluster di server Insight{#about-insight-server-clusters}

È necessario un cluster di Insight Server quando la quantità di dati da elaborare e rendere accessibili agli utenti di Insight e Report supera la capacità di un singolo server Insight.

Configurando un [!DNL Insight Server] cluster, potete distribuire un singolo dataset di analisi su più computer in un cluster per sfruttare la potenza di elaborazione di più [!DNL Insight Servers].

Il primo passaggio nell&#39;implementazione di un [!DNL Insight Server] cluster consiste nell&#39;allocare i [!DNL Insight Server] computer del cluster. Il primo [!DNL Insight Server] computer configurato è il master [!DNL Insight Server] (a volte denominato primario [!DNL Insight Server]).

>[!NOTE]
>
>Se si utilizza un&#39;unità [!DNL Insight Server] File Server (FSU), Adobe consiglia di configurare l&#39;FSU come principale [!DNL Insight Server]. Per informazioni sulla configurazione di un FSU, vedere la Guida alla configurazione del *set di dati*.

Il master [!DNL Insight Server] gestisce la comunicazione tra l&#39;altro [!DNL Insight Servers] nel cluster (denominato server di elaborazione o, a volte, server di query) e le istanze di [!DNL Insight] e [!DNL Report]. Per un dato set di dati, l&#39;elaborazione del file di registro si verifica su uno o più dei dati [!DNL Insight Servers] (master o elaborazione) specificati nei file di [!DNL Insight Server] configurazione. Quando si lavora in un ambiente cluster, [!DNL Insight] le installazioni sono configurate per l&#39;accesso al master [!DNL Insight Server], ma le query possono essere gestite da qualsiasi [!DNL Insight Servers] utente all&#39;interno del cluster.

>[!NOTE]
>
>Il file **PAServer.cfg** . Se si desidera inviare i processi di clustering Predictive Analytics ai server Insight, sarà necessario configurare il [!DNL PAServer.cfg] file per la gestione degli invii del clustering lato server. Il profilo personalizzato deve ereditare il profilo [!DNL PAServer.cfg] dal profilo Predictive Analytics ( [!DNL Server\Profiles\Predictive Analytics\Dataset]). Impostate un server ** principale in questo file e salvate il file [!DNL PAServer.cfg] nel sito di implementazione. >
>
```>
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```>



>[!IMPORTANT]
>
>Le istruzioni di cui al presente capitolo non si applicano alla creazione di un [!DNL Insight Server] cluster costituito da più di cinque (5) [!DNL Insight Servers]. Contattate Adobe per ottenere i requisiti di sistema e le raccomandazioni di configurazione del profilo per cluster di dimensioni superiori a cinque [!DNL Insight Servers].

