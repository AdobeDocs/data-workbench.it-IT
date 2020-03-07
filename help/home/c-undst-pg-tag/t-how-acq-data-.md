---
description: È necessario installare ed eseguire Sensor su ogni server Web che distribuisce il contenuto del sito per raccogliere tutte le richieste visualizzate da tali server.
solution: Analytics
title: Come posso acquisire questo dato_
topic: Data workbench
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Come posso acquisire questo dato_{#how-do-i-acquire-this-data}

È necessario installare ed eseguire Sensor su ogni server Web che distribuisce il contenuto del sito per raccogliere tutte le richieste visualizzate da tali server.

Queste richieste rappresentano il 90% o più delle richieste effettuate al sito e il 90% o più dei dati necessari per l&#39;analisi completa del traffico del sito. [!DNL Page Tags] deve essere quindi utilizzato per raccogliere il restante 10% o meno dei dati di traffico che non sono noti ai server Web. Tuttavia, le seguenti configurazioni valide per la raccolta di dati di richiesta Web dal sito, in ordine di preferenza, in base alla nostra esperienza operativa:

1. [!DNL Sensor] è installato in ogni server Web controllato e che supporta il sito. I contenuti provenienti da siti di terze parti, il contenuto distribuito dalla cache e alcuni tipi di contenuto dinamico devono essere contrassegnati con tag. Tali tag pagina devono inviare i dati raccolti a un server Web nel percorso in esecuzione [!DNL Sensor]. Potete aggiungere un server Web aggiuntivo se il livello di traffico di richiesta dei tag della pagina lo giustifica, o in casi speciali, dedicare un server Web alla raccolta di tali richieste di tag della pagina.
1. [!DNL Sensor] è installato su due server Web, denominati anche server di raccolta dati in questa guida, che si trovano nella posizione in cui si trovano e sono dedicati alla raccolta dei dati di richiesta dei tag della pagina dalle pagine con tag. Tutti i contenuti del sito dispongono di tag e tutti i tag delle pagine vengono indirizzati ai due server di raccolta dati.
1. [!DNL Sensor’s] i servizi di raccolta dati sono forniti da un outsourcing che esegue server di raccolta dati per raccogliere tutti i dati delle richieste Web. In questo caso, tutto il contenuto del sito viene contrassegnato con tag e i tag pagina inviano i propri dati ai server di raccolta dati in outsourcing.

   For more information about [!DNL Sensor], see the *Data Workbench[!DNL Sensor]Guide*.

