---
description: È necessario installare ed eseguire Sensor su ogni server web che distribuisce il contenuto del sito per raccogliere tutte le richieste visualizzate da tali server.
title: Come posso acquisire questo dato_
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
exl-id: 1c886f60-eae9-48c2-b641-396c622035d4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# Come posso acquisire questo dato_{#how-do-i-acquire-this-data}

{{eol}}

È necessario installare ed eseguire Sensor su ogni server web che distribuisce il contenuto del sito per raccogliere tutte le richieste visualizzate da tali server.

Queste richieste rappresentano il 90% o più delle richieste effettuate al tuo sito e il 90% o più dei dati necessari per l&#39;analisi completa del traffico del tuo sito. [!DNL Page Tags] dovrebbe quindi essere utilizzato per raccogliere il restante 10% o meno dei dati sul traffico che non sono noti ai tuoi server web. Le seguenti, tuttavia, sono configurazioni valide per la raccolta di dati di richiesta web dal tuo sito, in ordine di preferenza, in base alla nostra esperienza operativa:

1. [!DNL Sensor] è installato su ogni server Web controllato e che supporta il sito. È necessario assegnare tag al contenuto proveniente da siti di terze parti, al contenuto trasmesso dalla cache e a determinati tipi di contenuto dinamico. Tali tag di pagina devono inviare i dati raccolti a un server web nella posizione in cui è in esecuzione [!DNL Sensor]. Puoi aggiungere un server web aggiuntivo se il livello di traffico della richiesta di tag pagina lo giustifica, o in casi speciali, dedica un server web per raccogliere queste richieste di tag pagina.
1. [!DNL Sensor] è installato in due server web, denominati anche server di raccolta dati in questa guida, nella tua posizione che sono dedicati alla raccolta dei dati di richiesta dei tag della pagina dalle pagine con tag. Tutti i contenuti del sito vengono contrassegnati con tag e tutti i tag della pagina vengono indirizzati ai due server di raccolta dati.
1. [!DNL Sensor’s] i servizi di raccolta dati sono forniti da un outsourcer che esegue i server di raccolta dati per raccogliere tutti i dati della richiesta web. In questo caso, tutti i contenuti del sito vengono taggati e i tag della pagina inviano i propri dati ai server di raccolta dati esternalizzati.

   Per ulteriori informazioni [!DNL Sensor], vedi *Data Workbench [!DNL Sensor] Guida*.
