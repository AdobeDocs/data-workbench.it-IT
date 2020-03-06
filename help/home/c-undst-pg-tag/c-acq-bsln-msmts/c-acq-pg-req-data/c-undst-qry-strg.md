---
description: La stringa di query (cs-uri-query) viene spesso utilizzata dalle applicazioni Web e dagli sviluppatori di siti per trasmettere informazioni da una pagina all’altra a causa della natura senza stato di HTTP.
solution: Analytics
title: Informazioni sulla stringa di query
topic: Data workbench
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informazioni sulla stringa di query{#understanding-the-query-string}

La stringa di query (cs-uri-query) viene spesso utilizzata dalle applicazioni Web e dagli sviluppatori di siti per trasmettere informazioni da una pagina all’altra a causa della natura senza stato di HTTP.

In molti casi, le informazioni possono essere trasmesse nella stringa di query quando vengono acquisite dal server [!DNL Sensor] Web. Tali informazioni possono essere utilizzate [!DNL Site] per illuminare la vera struttura del sito e il percorso dei visitatori attraverso di esso, nonché altre informazioni.

In alcuni siti Web dinamici, le coppie nome=valore (variabili) nella stringa query sono importanti per determinare la pagina effettiva richiesta da un visitatore. In tali casi, gli URL possono essere strutturati nel modo seguente o simile:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

In questo esempio, PAGENAME è in realtà l’indicatore della pagina che verrà servita al richiedente di questo URL. Molti strumenti e servizi di analisi dei registri Web limitano la capacità dell&#39;operatore del sito di definire la pagina nel proprio sito in base alle variabili delle stringhe di query presenti nelle stringhe di query degli URL del sito. Il server workbench dati e il workbench dati possono essere configurati per utilizzare tali nomi di query per definire pagine univoche. Questo è importante perché molti sistemi interpretano gli URL seguenti come la stessa pagina, ma [!DNL Site] non lo è.

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

Allo stesso modo, gli sviluppatori di siti e le applicazioni spesso aggiungono molte variabili stringa di query agli URL di un sito che non hanno nulla a che fare con l&#39;identificazione della pagina effettiva richiesta. Di seguito sono riportati alcuni esempi:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

In questo esempio, la variabile della stringa di query CAMPAIGN= è stata aggiunta all’URL. Questa variabile CAMPAIGN viene utilizzata per indicare quale campagna di marketing ha fatto sì che un visitatore selezionasse questo URL. [!DNL Site] può essere configurato per utilizzare queste informazioni CAMPAIGN, ma separarlo dalla definizione della pagina visualizzata da un visitatore, in modo che nell’elenco delle pagine a scopo di reporting e analisi vengano semplicemente visualizzati i seguenti elementi:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

