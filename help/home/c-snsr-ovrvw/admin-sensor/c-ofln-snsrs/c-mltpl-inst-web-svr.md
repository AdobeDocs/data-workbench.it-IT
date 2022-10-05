---
description: Informazioni sulla configurazione generale del Sensor con un'istanza del server web in esecuzione su un server web.
title: Utilizzo di più istanze di un server web
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
exl-id: a371f9ed-6c27-4b3d-843f-ae5621013410
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# Utilizzo di più istanze di un server web{#working-with-multiple-instances-of-a-web-server}

{{eol}}

Informazioni sulla configurazione generale del Sensor con un&#39;istanza del server web in esecuzione su un server web.

![](assets/web_inst.png)

In questo scenario, una singola istanza del server web sta scrivendo dati al file di coda mappato in memoria, che viene letto dal trasmettitore e inviato al [!DNL data workbench server].

Quando [!DNL Sensor] è installato su un server web che esegue più istanze di raccolta, è possibile configurarlo in uno dei due modi seguenti:

* Tutti i moduli di raccolta possono condividere un file di coda.

   Quando si utilizza un singolo file di coda, la gestione, la configurazione e l’amministrazione sono in qualche modo semplificate perché l’architettura stessa è meno complessa. Tuttavia, con un singolo file di coda, l&#39;intero server web, indipendentemente dal numero di istanze, è identificato come WEB1.

* Puoi replicare l’architettura di cui sopra più volte e avere ogni istanza del server web un file di coda separato.

   Questo consente di identificare in modo univoco ciascuna istanza del server web. In altre parole, l’identificazione del server web (e del corrispondente SensorID nel [!DNL Sensor] configurazione) è una funzione di questa configurazione.

In ogni caso, i dati contengono ancora tutte le informazioni sul nome host in modo da poter distinguere tra [!DNL www.client.com], [!DNL www2.client.com]e così via. La configurazione corretta è determinata dagli obiettivi di analisi e dalla necessità per gli analisti di segmentare i dati in base a una specifica istanza in esecuzione su un server web.

>[!NOTE]
>
>Questo tipo di segmentazione viene generalmente utilizzato solo nell’analisi operativa e non fornisce un utilizzo molto pratico al di fuori di tale area.
