---
description: La chiamata di esecuzione tag pagina di riferimento viene inserita nelle pagine Web per le quali si desidera raccogliere i dati di misurazione.
solution: Analytics
title: Aggiunta di chiamate di esecuzione tag pagina di riferimento
topic: Data workbench
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aggiunta di chiamate di esecuzione tag pagina di riferimento{#adding-reference-page-tag-execution-calls}

La chiamata di esecuzione tag pagina di riferimento viene inserita nelle pagine Web per le quali si desidera raccogliere i dati di misurazione.

Deve essere incluso nel corpo del documento HTML e può essere posizionato all’interno di un piè di pagina di inclusione globale, se applicabile. Il team [!DNL Reference Page Tag Execution Call] può modificare le informazioni aggiuntive che potrebbero essere identificate durante le riunioni dei requisiti con il team dei servizi di consulenza Adobe.

Per facilitare la raccolta dei dati attraverso l&#39;utilizzo di [!DNL Reference Page Tag], completare i seguenti passaggi:

1. Copiate il seguente codice nel corpo del documento HTML:

   ```
   <!--//BEGIN REFERENCE PAGE TAG--> 
   <script language="javascript"> 
   var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
   var v = {}; 
   </script> 
   
   <!--//MODIFIY PATH TO ZIG.JS--> 
   <script language="javascript" src="/path/to/zig.js" type="text/javascript"></script> 
   <!--//END REFERENCE PAGE TAG--> 
   
   <noscript> 
   <img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
   </noscript> 
   <!-- END REFERENCE PAGE TAG-->
   ```

1. Modificate il percorso della posizione dei [!DNL zig.js] file e [!DNL zag.gif] dei file. Ad esempio:

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

Verificate che le intestazioni HTTP Cache-Control appropriate siano state impostate sul server Web per garantire che i file [!DNL zig.js]e [!DNL zag.gif] i file non siano memorizzati nella cache dal browser. Potete impostare le informazioni dell&#39;intestazione Cache-Control HTTP utilizzando uno dei due metodi. Il primo metodo consiste nell’impostare un’intestazione HTTP tramite il server Web. Il secondo metodo consiste nell’impostare un’intestazione HTTP per ciascuna pagina o oggetto incorporato utilizzando uno script. Con il metodo di scripting, la pagina Web deve essere stata creata utilizzando un linguaggio di programmazione quale JSP o ASP. Viene quindi creato uno script per inviare le informazioni di intestazione appropriate. Due evidenti svantaggi accompagnano questo metodo: 1) tutte le pagine devono essere codificate per inviare l&#39;intestazione, e 2) le pagine non possono essere HTML statico, il che ha qualche effetto sulle prestazioni del server Web.

I siti Web in esecuzione su Microsoft IIS possono aggiungere l’intestazione HTTP appropriata tramite la console di gestione Microsoft. I siti Web gestiti dai server Web Netscape iPlanet possono ottenere questo risultato modificando il [!DNL obj.conf] file all&#39;interno della directory di configurazione del sito. Il server Web Apache offre ai webmaster la possibilità di personalizzare le intestazioni HTTP utilizzando il modulo mod_header incluso in cui AOLServer diventa personalizzabile tramite l&#39;uso di moduli Tcl. Prima di implementare le intestazioni HTTP Cache-Control, fare riferimento alla documentazione specifica per la piattaforma del server Web.

In generale, l’intestazione HTTP deve essere strutturata come segue:

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```

