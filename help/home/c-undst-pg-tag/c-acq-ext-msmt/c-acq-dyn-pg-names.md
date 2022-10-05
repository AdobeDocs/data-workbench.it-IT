---
description: Per alcuni siti, è necessario utilizzare richieste di oggetti incorporati per trasmettere informazioni al server web in modo che i dettagli su quale pagina è stata effettivamente servita possano essere acquisiti da Sensor e utilizzati per il reporting e l’analisi.
title: Acquisizione di nomi di pagina dinamici
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
exl-id: cd94caf0-b0dc-46c1-8f59-3ebb2f703286
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# Acquisizione di nomi di pagina dinamici{#acquiring-dynamic-page-names}

{{eol}}

Per alcuni siti, è necessario utilizzare richieste di oggetti incorporati per trasmettere informazioni al server web in modo che i dettagli su quale pagina è stata effettivamente servita possano essere acquisiti da Sensor e utilizzati per il reporting e l’analisi.

Questo potrebbe essere necessario se l’URL della pagina, come visualizzato dal server web, non è indicativo del contenuto della pagina mostrato al browser. Questo caso spesso deriva dall’uso di sistemi di personalizzazione o di gestione dei contenuti dinamici in cui il contenuto effettivo servito in una pagina è determinato al volo dall’URL, dal cookie, dai dati correlati e dalla logica dell’applicazione.

L’implementazione di un oggetto incorporato per raccogliere ulteriori misurazioni dovrebbe avere un impatto minimo sulle prestazioni complessive del sito. L&#39;Adobe suggerisce di incorporare un file JavaScript come oggetto utilizzato per raccogliere gli attributi estesi. (Tenere presente che un file JavaScript può essere incorporato senza alcun potenziale impatto sul layout e sulla presentazione della pagina web, in quanto potrebbe risultare dall’utilizzo di un’immagine incorporata.) Per acquisire con precisione le informazioni trasmesse all&#39;interno dell&#39;oggetto incorporato, l&#39;Adobe suggerisce anche l&#39;utilizzo di un nome comune. A scopo di denominazione, l&#39;Adobe fa riferimento a questo oggetto come [!DNL zig.js]. La [!DNL zig.js] creare il file all&#39;interno della directory appropriata su un server web su cui [!DNL Sensor] è installato. Questo file deve esistere in modo che la richiesta non restituisca un codice di errore 404. Il contenuto del file stesso non è importante. Utilizzare un file vuoto denominato [!DNL zig.js] ridurre al minimo il traffico di rete dovuto alla richiesta.

Per [!DNL Sensor] per raccogliere un nome utilizzabile per la pagina effettivamente servita, è necessario aggiungere alcune righe di codice JavaScript alle pagine dinamiche che si desidera monitorare o alle quali si desidera aggiungere un nome di pagina univoco. Questo codice incorpora uno snippet di JavaScript nella pagina, causando la richiesta di un oggetto terziario incorporato al server web durante il caricamento della pagina. Tale richiesta invia i dettagli sulla pagina specifica che è stata nuovamente trasmessa al server web. Il nome della pagina effettivamente distribuita viene riportato al server web come variabile nella stringa di query della richiesta di oggetto incorporato (in questo caso JavaScript).

In generale, la richiesta di oggetto incorporata in ciascuna pagina di HTML di questo tipo dovrebbe avere un aspetto simile al seguente:

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_pn"] = "Application Form";
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] assicura che [!DNL Sensor] registra la richiesta nonostante [!DNL Sensor] regole di filtro del tipo di contenuto al contrario, come il filtraggio da JavaScript e le richieste di immagini prima che vengano memorizzate. La variabile v_pn dichiarata identifica il nome del contenuto della pagina effettivo che viene servito in modo che [!DNL Site] conosce il nome della pagina effettivamente visualizzata dal visitatore. Il valore v_pn può essere stabilito manualmente o da un altro script o codice dell&#39;applicazione.

Dopo aver raccolto il valore, puoi configurare il server di Data Workbench in modo che utilizzi il contenuto della variabile della stringa di query (coppia nome=valore, ad esempio, v_pn=Modulo applicazione) aggiunta al [!DNL zag.gif] URI (ad esempio, [!DNL https://www.mysite.com/pageserved.asp?v_pn=Application%20Form]), come aumento del [!DNL zag.gif] URI Oltre alle misurazioni della linea di base acquisite con ogni richiesta HTTP, con questa richiesta si acquisirebbe una misura estesa.

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_pn= | Valore associato alla variabile della stringa di query v_pn | v_pn=Modulo di applicazione |
