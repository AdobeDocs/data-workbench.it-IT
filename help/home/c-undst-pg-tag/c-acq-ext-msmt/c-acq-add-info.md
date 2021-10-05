---
description: Le variabili della stringa di query possono essere aggiunte a una richiesta JavaScript per raccogliere misurazioni aggiuntive quando viene effettuata una richiesta.
title: Acquisizione di informazioni aggiuntive
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
exl-id: ad4f5e08-b7b7-4de3-b0c2-71440facb2d1
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 4%

---

# Acquisizione di informazioni aggiuntive{#acquiring-additional-information}

Le variabili della stringa di query possono essere aggiunte a una richiesta JavaScript per raccogliere misurazioni aggiuntive quando viene effettuata una richiesta.

Queste variabili possono essere aggiunte manualmente o da uno script nella pagina stessa.

Ulteriori informazioni che possono essere acquisite da una pagina possono essere aggiunte all&#39;oggetto incorporato tramite script utilizzando il seguente codice come esempio:

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_pn"] = "Application Form";
v["_1"] = “99.99”;
v["_2"] = "visa";
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>
<noscript>

<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>
<!-- END REFERENCE PAGE TAG-->
```

In questo esempio, le variabili di script per v_1 e v_2 possono essere derivate da un&#39;altra funzione all&#39;interno della pagina web. Le variabili sono state inserite come esempi. Oltre alle misurazioni della linea di base acquisite con ciascuna richiesta, con la richiesta dell&#39;URL di cui sopra si acquisiscono le seguenti misurazioni estese:

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_pn= | Valore associato alla variabile della stringa di query v_pn | v_pn=Modulo di applicazione |
| v_1= | Valore associato alla variabile della stringa di query v_1 | v_1=99.99 |
| v_2= | Valore associato alla variabile della stringa di query v_2 | v_2=visto |
