---
description: Informazioni sulla configurazione generale del sensore con un'istanza del server Web in esecuzione su un server Web.
solution: Analytics
title: Utilizzo di più istanze di un server web
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---


# Utilizzo di più istanze di un server web{#working-with-multiple-instances-of-a-web-server}

Informazioni sulla configurazione generale del sensore con un&#39;istanza del server Web in esecuzione su un server Web.

![](assets/web_inst.png)

In questo scenario, una singola istanza del server Web sta scrivendo i dati nel file della coda mappato della memoria, che viene letto dal trasmettitore e inviato al [!DNL data workbench server].

Quando [!DNL Sensor] è installato su un server Web che esegue più istanze di raccolta, è possibile configurarlo in uno dei due modi seguenti:

* È possibile che tutti i moduli di raccolta condividano un file di coda.

   Quando si utilizza un singolo file di coda, la gestione, la configurazione e l&#39;amministrazione sono in qualche modo semplificate perché l&#39;architettura stessa è meno complessa. Tuttavia, con un singolo file di coda, l&#39;intero server Web, indipendentemente dal numero di istanze, viene identificato come WEB1.

* È possibile replicare l&#39;architettura di cui sopra più volte e avere ogni istanza del server Web un file di coda separato.

   Questo consente di identificare in modo univoco ciascuna istanza del server Web. In altre parole, l&#39;identificazione del server Web (e il SensorID corrispondente nella [!DNL Sensor] configurazione) è una funzione di questa configurazione.

In ogni caso, i dati contengono ancora tutte le informazioni relative al nome host, in modo da poter distinguere tra [!DNL www.client.com], [!DNL www2.client.com]e così via. La configurazione corretta è determinata dagli obiettivi di analisi e dalla necessità per gli analisti di segmentare i dati in base a un&#39;istanza specifica in esecuzione su un server Web.

>[!NOTE]
>
>Questo tipo di segmentazione viene in genere utilizzato solo nell&#39;analisi operativa e non fornisce un utilizzo pratico al di fuori di tale area.

