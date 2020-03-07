---
description: Passaggi utilizzati per facilitare la raccolta di clic sul collegamento mediante l’uso del tag della pagina di riferimento.
solution: Analytics
title: Tracciamento dei clic dei collegamenti
topic: Data workbench
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tracciamento dei clic dei collegamenti{#tracking-link-clicks}

Passaggi utilizzati per facilitare la raccolta di clic sul collegamento mediante l’uso del tag della pagina di riferimento.

Attraverso la distribuzione di [!DNL Reference Page Tag], è possibile raccogliere dati di misurazione che denotano i collegamenti (o i valori href) su cui i visitatori fanno clic durante la visita a pagine particolari. In genere, questa raccolta non comporta l&#39;implementazione di identificatori di collegamento aggiuntivi nelle pagine HTML.

Per facilitare la raccolta dei clic di collegamento tramite l’uso di [!DNL Reference Page Tag], completa i seguenti passaggi:

1. Copiate il seguente codice nel file esistente denominato [!DNL zig.js]:

   ```
   //REFERENCE LINK AND FORM CLICK PAGE TAG 
   //INITIATE FUNCTIONS ONLOAD 
   function addEvent(obj, evType, fn){  
    if (obj.addEventListener){  
      obj.addEventListener(evType, fn, false);  
      return true;  
    } else if (obj.attachEvent){  
      var r = obj.attachEvent("on"+evType, fn);  
      return r;  
    } else {  
      return false;  
    }  
   } 
   addEvent(window, 'load', startCapture); 
   addEvent(window, 'load', startCapture); 
   function startCapture(){ 
   //TO CAPTURE LINK CLICKS 
     if (vlc == "1"){captureLink();} 
     //TO CAPTURE FORM FIELD CLICKS 
     if (vfc == "1"){captureForm();} 
   } 
   //BEGIN LINK CAPTURE PAGE TAG 
   function captureLink(){ 
     if (document.links[0]){ 
       if (document.links){ 
         var links = document.links, link, k=0; 
         while(link=links[k++]) { 
           link.onclick = captureLinkName; 
    } 
       } 
     } 
   } 
   function captureLinkName() { 
     var lc=new Image(); 
     this.parent = this.parentNode; 
     lc.src='zag2.gif?linkname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END LINK CAPTURE PAGE TAG 
   //BEGIN FORM CLICK CAPTURE PAGE TAG 
   function captureForm(){ 
     if (document.forms[0]) { 
       if(document.forms){ 
    for(i=0; i<document.forms[0].elements.length; i++){ 
           var forms = document.forms[0].elements[i]; 
           forms.onfocus = captureFormName; 
         } 
       } 
     } 
   } 
   function captureFormName() { 
     var fc=new Image(); 
     fc.src='zag3.gif?fieldname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END FORM CLICK CAPTURE PAGE TAG
   ```

1. Create o inserite il file immagine da 1 pixel per 1 pixel denominato [!DNL zag2.gif] in una directory presente sul server Web.
1. Modificate la [!DNL lc.src] variabile in modo che faccia riferimento al dominio appropriato del sito Web da cui viene fatto riferimento al [!DNL zag2.gif]file.

1. Assicurarsi che le intestazioni di controllo della cache appropriate siano stabilite per i [!DNL zag.gif] file e [!DNL zig.js] i file.

1. All&#39;interno dei file HTML da cui si desidera raccogliere i valori di clic del collegamento, [!DNL Reference Page Tag Execution Call] è necessario modificare il collegamento per informare l&#39;utente [!DNL Page Tag Execution Script] a catturare i clic del collegamento per quella pagina. A questo scopo, modificate il valore della variabile vlc in &quot;1&quot;, come evidenziato nel seguente esempio di codice:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE 
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE 
var v = {}; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_ln= | Valore che indica la campagna Impression | v_ln=&quot;About%20Us&quot; |

