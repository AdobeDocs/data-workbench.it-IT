---
description: Acquisizione dell'attività tra i collegamenti del sito Web di terze parti per abilitare l'analisi di Exit Target.
solution: Analytics
title: Tracciamento delle uscite sui collegamenti esterni
topic: Data workbench
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tracciamento delle uscite sui collegamenti esterni{#tracking-exits-to-external-links}

Acquisizione dell&#39;attività tra i collegamenti del sito Web di terze parti per abilitare l&#39;analisi di Exit Target.

Le pagine Web possono contenere collegamenti a siti Web di terze parti e l&#39;attività tra tali collegamenti può essere acquisita per abilitare l&#39;analisi di Exit Target, soprattutto nel caso in cui il sito di terze parti sia responsabile del pagamento delle commissioni di riferimento al ricevimento di tali riferimenti. Poiché l&#39;evento click è scritto nei file di registro del sistema di terze parti per impostazione predefinita, è necessario apportare delle modifiche al collegamento per l&#39;acquisizione locale dell&#39;evento click. Il collegamento di terze parti presente nel sito Web deve essere modificato come segue:

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

Il [!DNL PageExit.htm] file di riferimento deve essere creato e strutturato in modo da contenere lo script seguente:

```
<html> 
<head> 
 
<script> 
function getExitURLQuery(variable) 
{ 
 
var query = window.location.search.substring(1); 
var vars = query.split("&"); 
for (var i=0; i<vars.length; i++) 
{ 
var pair = vars[i].split("="); 
if (pair[0] == variable) 
{ 
return pair[1]; 
} 
 }  
} 
</script> 
 
<script> 
location.replace(getExitURLQuery("v_eurl")); 
</script>  
 
</head> 
</html>
```

Facendo la richiesta per il [!DNL PageExit.htm] file, il valore v_eurl viene raccolto a scopo di analisi. Inoltre, quando [!DNL PageExit.htm] viene caricato, viene reindirizzato immediatamente alla posizione di destinazione v_eurl specificata.

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_eurl | Valore associato alla variabile della stringa di query v_eurl. Questo valore rappresenta l&#39;URL di destinazione del collegamento presente nella pagina HTML. | v_eurl=www.othersite.com |

