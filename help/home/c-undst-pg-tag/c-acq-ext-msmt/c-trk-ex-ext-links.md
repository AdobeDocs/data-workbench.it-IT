---
description: Acquisizione di attività tra collegamenti a siti web di terze parti per abilitare l’analisi di Esci da Target.
title: Tracciamento delle uscite sui collegamenti esterni
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 6%

---

# Tracciamento delle uscite sui collegamenti esterni{#tracking-exits-to-external-links}

Acquisizione di attività tra collegamenti a siti web di terze parti per abilitare l’analisi di Esci da Target.

Le pagine web possono contenere collegamenti a siti web di terze parti e l&#39;attività di tali collegamenti può essere acquisita per abilitare l&#39;analisi di Esci da Target, soprattutto nel caso in cui il sito di terze parti sia responsabile del pagamento delle tariffe di riferimento quando tali riferimenti vengono ricevuti. Poiché l’evento clic è scritto nei file di registro del sistema di terze parti per impostazione predefinita, è necessario apportare modifiche al collegamento per acquisire localmente l’evento clic. Il collegamento di terze parti presente nel sito web deve essere modificato come segue:

```
<A HREF=”https://www.myserver.com/PageExit.htm?v_eurl=https://www.othersite.com”>
```

Il file [!DNL PageExit.htm] a cui si fa riferimento deve essere creato e strutturato in modo da contenere il seguente script:

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

Facendo la richiesta per il file [!DNL PageExit.htm], il valore v_eurl viene raccolto a scopo di analisi. Inoltre, quando viene caricato [!DNL PageExit.htm], reindirizza immediatamente alla posizione di destinazione v_eurl specificata.

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_eurl | Valore associato alla variabile della stringa di query v_eurl. Questo valore rappresenta l’URL di destinazione del collegamento presente nella pagina HTML. | v_eurl=www.othersite.com |
