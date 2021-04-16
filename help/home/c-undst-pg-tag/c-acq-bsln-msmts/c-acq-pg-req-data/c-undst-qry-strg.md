---
description: La stringa query (cs-uri-query) viene spesso utilizzata dalle applicazioni web e dagli sviluppatori di siti per trasmettere informazioni da pagina a pagina a causa della natura senza stato di HTTP.
title: Informazioni sulla stringa di query
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 2%

---

# Informazioni sulla stringa di query{#understanding-the-query-string}

La stringa query (cs-uri-query) viene spesso utilizzata dalle applicazioni web e dagli sviluppatori di siti per trasmettere informazioni da pagina a pagina a causa della natura senza stato di HTTP.

In molti casi, le informazioni possono essere passate nella stringa di query quando viene acquisita da [!DNL Sensor] nel server web. Tali informazioni possono essere utilizzate da [!DNL Site] per illuminare la vera struttura del sito, il percorso dei visitatori attraverso di esso, nonché altre informazioni.

In alcuni siti web dinamici, le coppie nome=valore (variabili) nella stringa query sono importanti per determinare la pagina effettiva richiesta da un visitatore. In tali casi, gli URL possono essere strutturati nel modo seguente o simile:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

In questo esempio, PAGENAME è in realtà l’indicatore di quale pagina verrà servita al richiedente di questo URL. Molti strumenti e servizi di analisi dei log web limitano la capacità dell’operatore del sito di definire ciò che una pagina è nel loro sito in base alle variabili delle stringhe query che si verificano nelle stringhe query degli URL del sito. Il server di Data Workbench e Data Workbench possono essere configurati in modo da utilizzare tali nomi di query per definire pagine univoche. Questo è importante perché molti sistemi interpreterebbero i seguenti URL come la stessa pagina, ma [!DNL Site] no.

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

Allo stesso modo, gli sviluppatori di siti e le applicazioni spesso aggiungono molte variabili di stringa di query agli URL di un sito che non hanno nulla a che fare con l’identificazione della pagina effettiva richiesta. Di seguito sono riportati alcuni esempi:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

In questo esempio, la variabile della stringa di query CAMPAIGN= è stata aggiunta all&#39;URL. Questa variabile CAMPAIGN viene utilizzata per indicare quale campagna di marketing ha causato la selezione di questo URL da parte di un visitatore. [!DNL Site] può essere configurato per utilizzare queste informazioni di CAMPAIGN, ma separalo dalla definizione della pagina visualizzata da un visitatore, in modo che nell’elenco delle pagine a scopo di reporting e analisi vengano semplicemente visualizzati i seguenti elementi:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
