---
description: Il tag di pagina di riferimento è costituito da uno script di esecuzione dei tag di pagina che si trova su un server Web e, se chiamato, restituisce la raccolta di tutti i dati lato client per la pagina richiesta dal visitatore del sito.
solution: Analytics
title: Modifica dello script di esecuzione dei tag della pagina di riferimento
topic: Data workbench
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modifica dello script di esecuzione dei tag della pagina di riferimento{#editing-the-reference-page-tag-execution-script}

Il tag di pagina di riferimento è costituito da uno script di esecuzione dei tag di pagina che si trova su un server Web e, se chiamato, restituisce la raccolta di tutti i dati lato client per la pagina richiesta dal visitatore del sito.

Potete modificare le informazioni [!DNL Reference Page Tag Execution Script] per raccogliere informazioni aggiuntive che possono essere identificate durante la raccolta di requisiti per riunioni con il team Adobe Consulting Services. Le dimensioni [!DNL Reference Page Tag Execution Script] sono relativamente ridotte per evitare di dover aggiungere alle pagine Web numerosi download.

Il seguente [!DNL Reference Page Tag Execution Script] codice viene fornito in un file denominato [!DNL zig.js]:

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

Per facilitare la raccolta dei dati attraverso l&#39;utilizzo di [!DNL Reference Page Tag], completare i seguenti passaggi:

1. Create o inserite il file immagine da 1 pixel per 1 pixel denominato [!DNL zag.gif] in una directory presente sul server Web.
1. Modificate la variabile cd per fare riferimento al dominio appropriato del sito Web o del dominio di servizi gestiti Adobe dal quale viene fatto riferimento al [!DNL zag.gif] file. Il riferimento al file viene creato mediante l&#39;esecuzione delle funzioni del [!DNL zig.js] file. Ad esempio:

   ```
   //www.mysite.com
   ```

1. Modificate la variabile cu in modo che faccia riferimento al percorso appropriato per la posizione del [!DNL zag.gif] file. Ad esempio

   ```
   /scripts
   ```

1. Assicurarsi che le intestazioni di controllo della cache appropriate siano stabilite per i [!DNL zag.gif] file e [!DNL zig.js] i file.
