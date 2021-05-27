---
description: Il tag pagina di riferimento è costituito da uno script di esecuzione dei tag di pagina che si trova su un server web e, quando chiamato, restituisce la raccolta di tutti i dati lato client per la pagina richiesta dal visitatore del sito.
title: Modifica dello script di esecuzione dei tag della pagina di riferimento
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 7%

---

# Modifica dello script di esecuzione dei tag della pagina di riferimento{#editing-the-reference-page-tag-execution-script}

Il tag pagina di riferimento è costituito da uno script di esecuzione dei tag di pagina che si trova su un server web e, quando chiamato, restituisce la raccolta di tutti i dati lato client per la pagina richiesta dal visitatore del sito.

È possibile modificare il [!DNL Reference Page Tag Execution Script] per raccogliere informazioni aggiuntive che possono essere identificate durante le riunioni dei requisiti con il team Adobe Consulting Services. Le [!DNL Reference Page Tag Execution Script] sono di dimensioni relativamente ridotte per evitare aggiunte di download di grandi dimensioni alle pagine web.

In un file denominato [!DNL zig.js] ti viene fornito il seguente codice [!DNL Reference Page Tag Execution Script]:

```
//REFERENCE PAGE TAG 
// CONSTANTS 
var ct = "<img src="; 
var cd = "[PATH_TO_WEB_SERVER]"; //this should contain the domain of 
                               //the web site that will host the 
                                //page tag 
 
var cu = "[PATH_TO_WEB_PAGE_TAG_CODE]/zag.gif?Log=1";  
                                 //this should contain the full path to 
                                 //the zag.gif file (excluding domain) 
                                 //and include the query string of log=1 
var ce = ">"; 
var c = {}; 
c["sw"] = screen.width; 
c["sh"] = screen.height; 
c["cd"] = screen.colorDepth; 
var co = ""; 
 
for ( cKey in c ) { 
co = co+"&"+cKey+"="+escape(c[cKey]); 
} 
document.write(ct,cd,cu,co,ce); 
 
var d = {}; 
d["dt"] = document.title; 
d["dr"] = document.referrer; 
d["cb"] = new Date().getTime(); 
var vo = ""; 
 
if (typeof v != "undefined") { 
for ( vKey in v ) { 
vo = vo+"&"+vKey+"="+escape(v[vKey]); 
} 
} 
for ( dKey in d ) { 
vo = vo+"&"+dKey+"="+escape(d[dKey]); 
} 
document.write(ct,cd,cu,vo,ce); 
//END REFERENCE PAGE TAG 
```

Per facilitare la raccolta dei dati tramite l’uso di [!DNL Reference Page Tag], completa i seguenti passaggi:

1. Crea o inserisci il file immagine da 1 pixel per 1 pixel denominato [!DNL zag.gif] in una directory presente sul server web.
1. Modifica la variabile cd in modo che faccia riferimento al dominio appropriato del tuo sito web o del dominio dei servizi gestiti di Adobe dal quale viene fatto riferimento al file [!DNL zag.gif] . Il riferimento al file viene creato tramite l&#39;esecuzione delle funzioni del file [!DNL zig.js]. Ad esempio:

   ```
   //www.mysite.com
   ```

1. Modifica la variabile cu in modo che faccia riferimento al percorso appropriato per la posizione del file [!DNL zag.gif]. Ad esempio

   ```
   /scripts
   ```

1. Assicurati che le intestazioni di controllo della cache appropriate siano stabilite per i file [!DNL zag.gif] e [!DNL zig.js].
