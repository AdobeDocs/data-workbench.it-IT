---
description: Utilizzando il modello di oggetto documento JavaScript, è possibile utilizzare metodi di script aggiuntivi per incrementare la richiesta del file zig.js.
title: Acquisizione di oggetti documento
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
exl-id: eae6609c-be86-44cf-a1a1-69ffb43231fa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# Acquisizione di oggetti documento{#acquiring-document-objects}

Utilizzando il modello di oggetto documento JavaScript, è possibile utilizzare metodi di script aggiuntivi per incrementare la richiesta del file zig.js.

Informazioni come il valore dei tag META, i valori ID dei tag DIV e così via possono essere referenziati per nome e raccolti come variabili da utilizzare nell’analisi. Ad esempio, per acquisire in modo dinamico le informazioni contenute nell’elemento META del documento HTML, è possibile utilizzare la seguente sintassi JavaScript:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var m0 = document.getElementsByTagName('META')[0]; //define the first instance of META 
var metacontent = m0.getAttribute('content'); //get the ‘content’ value of META 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_1"] = metacontent; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_1= | Valore associato alla variabile della stringa di query METAVALUE. Questo valore rappresenta i dati all’interno dell’elemento META del documento HTML. | v_1=Questa pagina fornisce il contenuto relativo alla pagina di ringraziamento dell&#39;ordine. |

Una volta raccolti i dati, puoi configurare il server di Data Workbench per elaborare i dati di misurazione ai fini dell’analisi e del reporting.
