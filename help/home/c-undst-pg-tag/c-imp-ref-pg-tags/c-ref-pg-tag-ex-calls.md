---
description: La chiamata di esecuzione dei tag della pagina di riferimento viene inserita nelle pagine web per le quali desideri raccogliere i dati di misurazione.
title: Aggiunta di chiamate di esecuzione dei tag della pagina di riferimento
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
exl-id: a4f9ab2b-50e8-4e0b-9c87-80dffb697316
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 3%

---

# Aggiunta di chiamate di esecuzione dei tag della pagina di riferimento{#adding-reference-page-tag-execution-calls}

La chiamata di esecuzione dei tag della pagina di riferimento viene inserita nelle pagine web per le quali desideri raccogliere i dati di misurazione.

Deve essere incluso nel corpo del documento HTML e può essere posizionato all’interno di un piè di pagina di inclusione globale, se applicabile. Il [!DNL Reference Page Tag Execution Call] può essere modificato dal tuo team per raccogliere informazioni aggiuntive che potrebbero essere identificate durante le riunioni dei requisiti per la raccolta di informazioni con il team Adobe Consulting Services.

Per facilitare la raccolta dei dati tramite l’uso di [!DNL Reference Page Tag], completa i seguenti passaggi:

1. Copia il seguente codice nel corpo del documento HTML:

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

1. Modifica il percorso della posizione dei file [!DNL zig.js] e [!DNL zag.gif]. Ad esempio:

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

Assicurati che le intestazioni HTTP Cache-Control appropriate siano state impostate sul server web per garantire che i file [!DNL zig.js]e [!DNL zag.gif] non siano memorizzati nella cache dal browser. È possibile impostare le informazioni dell&#39;intestazione HTTP Cache-Control utilizzando uno dei due metodi disponibili. Il primo metodo è quello di impostare un&#39;intestazione HTTP tramite il server web. Il secondo metodo consiste nell&#39;impostare un&#39;intestazione HTTP per ogni pagina specifica o oggetto incorporato utilizzando uno script. Con il metodo di script, la pagina Web deve essere stata creata utilizzando un linguaggio di programmazione come JSP o ASP. La pagina viene quindi script in modo da inviare le informazioni di intestazione appropriate. Due evidenti svantaggi accompagnano questo metodo: 1) tutte le pagine devono essere codificate per inviare l&#39;intestazione; 2) le pagine non possono essere HTML statico, il che ha qualche effetto sulle prestazioni del server web.

I siti Web in esecuzione su Microsoft IIS possono aggiungere l&#39;intestazione HTTP appropriata tramite Microsoft Management Console. I siti Web gestiti dai server Web Netscape iPlanet possono eseguire questa operazione modificando il file [!DNL obj.conf] all&#39;interno della directory di configurazione del sito. Apache Web Server offre ai webmaster la possibilità di personalizzare le intestazioni HTTP utilizzando il modulo mod_headers incluso in cui AOLServer diventa personalizzabile tramite l&#39;uso di moduli Tcl. Prima di implementare le intestazioni HTTP Cache-Control, è necessario fare riferimento alla documentazione specifica della piattaforma del server web.

In generale, l’intestazione HTTP deve essere strutturata come segue:

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```
