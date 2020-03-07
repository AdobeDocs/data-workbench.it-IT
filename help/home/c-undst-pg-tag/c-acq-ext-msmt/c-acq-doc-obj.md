---
description: Utilizzando il modello di oggetto documento JavaScript, è possibile utilizzare metodi di script aggiuntivi per espandere la richiesta per il file zig.js.
solution: Analytics
title: Acquisizione di oggetti documento
topic: Data workbench
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Acquisizione di oggetti documento{#acquiring-document-objects}

Utilizzando il modello di oggetto documento JavaScript, è possibile utilizzare metodi di script aggiuntivi per espandere la richiesta per il file zig.js.

Informazioni quali il valore dei tag META, i valori ID dei tag DIV e così via possono essere citati per nome e raccolti come variabili da utilizzare nell&#39;analisi. Ad esempio, per acquisire in modo dinamico le informazioni contenute nell&#39;elemento META del documento HTML, è possibile utilizzare la seguente sintassi JavaScript:

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
| v_1= | Valore associato alla variabile della stringa di query METAVALUE. Questo valore rappresenta i dati all&#39;interno dell&#39;elemento META del documento HTML. | v_1=Questa pagina contiene il contenuto correlato alla pagina di ringraziamento dell’ordine. |

Una volta raccolti i dati, puoi configurare il server workbench dati per elaborare i dati di misurazione ai fini dell&#39;analisi e del reporting.
