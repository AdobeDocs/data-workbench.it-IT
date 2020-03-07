---
description: Le variabili stringa di query possono essere aggiunte a una richiesta JavaScript per raccogliere ulteriori misure quando viene effettuata una richiesta.
solution: Analytics
title: Acquisizione di informazioni aggiuntive
topic: Data workbench
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Acquisizione di informazioni aggiuntive{#acquiring-additional-information}

Le variabili stringa di query possono essere aggiunte a una richiesta JavaScript per raccogliere ulteriori misure quando viene effettuata una richiesta.

Queste variabili possono essere aggiunte manualmente o mediante script nella pagina stessa.

Ulteriori informazioni che è possibile acquisire da una pagina possono essere aggiunte all&#39;oggetto incorporato tramite script utilizzando il seguente codice come esempio:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
v["_1"] = “99.99”; 
v["_2"] = "visa"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
<noscript> 
 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
<!-- END REFERENCE PAGE TAG-->
```

In questo esempio, le variabili di script per v_1 e v_2 possono essere derivate da un&#39;altra funzione all&#39;interno della pagina Web. Le variabili sono state inserite come esempi. Oltre alle misure di base acquisite con ciascuna richiesta, con la richiesta dell’URL soprastante si acquisirebbero le seguenti misure estese:

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_pn= | Valore associato alla variabile della stringa di query v_pn | v_pn=Modulo applicazione |
| v_1= | Valore associato alla variabile della stringa della query v_1 | v_1=99.99 |
| v_2= | Valore associato alla variabile della stringa della query v_2 | v_2=visto |

