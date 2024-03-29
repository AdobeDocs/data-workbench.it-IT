---
description: Passaggi utilizzati per facilitare la raccolta di clic sui collegamenti tramite l’uso del tag della pagina di riferimento.
title: Tracciamento dei clic dei collegamenti
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
exl-id: 0cb743e6-5c6e-4f80-bc77-83d1e706c92b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 3%

---

# Tracciamento dei clic dei collegamenti{#tracking-link-clicks}

{{eol}}

Passaggi utilizzati per facilitare la raccolta di clic sui collegamenti tramite l’uso del tag della pagina di riferimento.

Attraverso l&#39;installazione di [!DNL Reference Page Tag], è possibile raccogliere dati di misurazione che denotano i collegamenti (o valori href) su cui i visitatori fanno clic durante la visita a determinate pagine. In genere, questa raccolta non richiede l’implementazione di identificatori di collegamento aggiuntivi nelle pagine di HTML.

Per facilitare la raccolta dei clic sui link attraverso l&#39;uso del [!DNL Reference Page Tag], completa i seguenti passaggi:

1. Copia il seguente codice nel file esistente denominato [!DNL zig.js]:

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

1. Crea o posiziona il file immagine da 1 pixel per 1 pixel denominato [!DNL zag2.gif] in una directory presente sul server web.
1. Modifica la [!DNL lc.src] per fare riferimento al dominio appropriato del sito web da cui [!DNL zag2.gif]file a cui si fa riferimento.

1. Assicurati che le intestazioni di controllo della cache appropriate siano stabilite per [!DNL zag.gif] e [!DNL zig.js] file.

1. Nei file HTML da cui desideri raccogliere i valori di clic del collegamento, la [!DNL Reference Page Tag Execution Call] devono essere modificati per informare [!DNL Page Tag Execution Script] per acquisire i clic sul collegamento per la pagina. A questo scopo, modifica il valore della variabile vlc in &quot;1&quot;, come evidenziato nel seguente esempio di codice:

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE
var v = {};
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_ln= | Valore che indica la campagna di impression | v_ln=&quot;Informazioni su%20Us&quot; |
