---
description: Per alcuni siti, è necessario utilizzare le richieste di oggetti incorporati per trasmettere informazioni al server Web in modo che i dettagli sulla pagina effettivamente servita possano essere acquisiti dal sensore e utilizzati per reporting e analisi.
solution: Analytics
title: Acquisizione di nomi di pagina dinamici
topic: Data workbench
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Acquisizione di nomi di pagina dinamici{#acquiring-dynamic-page-names}

Per alcuni siti, è necessario utilizzare le richieste di oggetti incorporati per trasmettere informazioni al server Web in modo che i dettagli sulla pagina effettivamente servita possano essere acquisiti dal sensore e utilizzati per reporting e analisi.

Questo può essere richiesto se l’URL della pagina, come visualizzato dal server Web, non è indicativo del contenuto della pagina mostrato al browser. Questo caso spesso deriva dall’uso di sistemi di personalizzazione o di gestione dinamica dei contenuti in cui il contenuto effettivo distribuito in una pagina viene determinato al volo dall’URL, dal cookie, dai dati correlati e dalla logica dell’applicazione.

L&#39;implementazione di un oggetto incorporato per la raccolta di misurazioni aggiuntive dovrebbe avere un impatto minimo sulle prestazioni complessive del sito. Adobe consiglia di incorporare un file JavaScript come oggetto utilizzato per raccogliere gli attributi estesi. Un file JavaScript può essere incorporato senza alcun impatto potenziale sul layout e sulla presentazione della pagina Web, come risultato dell&#39;utilizzo di un&#39;immagine incorporata. Per acquisire con precisione le informazioni trasmesse all&#39;interno dell&#39;oggetto incorporato, Adobe consiglia inoltre di utilizzare un nome comune. Ai fini della denominazione, Adobe fa riferimento a questo oggetto come [!DNL zig.js]. Il [!DNL zig.js] file deve essere creato all&#39;interno della directory appropriata su un server Web in cui [!DNL Sensor] è installato. Questo file deve esistere in modo che la richiesta non restituisca un codice di errore 404. Il contenuto del file stesso non è importante. È consigliabile utilizzare un file vuoto denominato [!DNL zig.js] per ridurre al minimo la quantità di traffico di rete generato dalla richiesta.

Per [!DNL Sensor] raccogliere un nome utilizzabile per la pagina effettivamente servita, è necessario aggiungere alcune righe di codice JavaScript alle pagine dinamiche da monitorare o alle quali si desidera aggiungere un nome univoco per la pagina. Questo codice incorpora uno snippet di JavaScript nella pagina, causando la richiesta terziaria di oggetti incorporati al server Web durante il caricamento della pagina. Tale richiesta invia i dettagli sulla pagina specifica che è stata restituita al server Web. Il nome della pagina effettivamente servita viene riportato al server Web come variabile nella stringa di query della richiesta dell&#39;oggetto incorporato (in questo caso JavaScript).

In generale, la richiesta di oggetto incorporata in ciascuna di tali pagine HTML dovrebbe avere l&#39;aspetto seguente:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] verifica che [!DNL Sensor] la richiesta venga registrata nonostante le regole di filtro del tipo di [!DNL Sensor] contenuto siano al contrario, come il filtraggio fuori da JavaScript e le richieste di immagini prima che vengano memorizzate. La variabile v_pn dichiarata identifica il nome del contenuto effettivo della pagina che viene servita in modo da [!DNL Site] conoscere il nome della pagina effettivamente visualizzata dal visitatore. Il valore v_pn può essere stabilito manualmente o da altro codice script o applicazione.

Dopo aver raccolto il valore, è possibile configurare il server workbench dati in modo che utilizzi il contenuto della variabile della stringa di query (coppia nome=valore, ad esempio, v_pn=Modulo applicazione) aggiunta all’ [!DNL zag.gif] URI (ad esempio, [!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form]) come aumento dell’ [!DNL zag.gif] URI. Oltre alle misure di base acquisite con ogni richiesta HTTP, con questa richiesta si acquisirebbe una misura estesa.

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_pn= | Valore associato alla variabile della stringa di query v_pn | v_pn=Modulo applicazione |

