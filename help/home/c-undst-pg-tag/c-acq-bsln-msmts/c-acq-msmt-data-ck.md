---
description: Come parte dei dati di misurazione della linea di base raccolti, Sensor raccoglie i cookie di dominio inviati dal computer di un visitatore quando effettua una richiesta dal server web.
title: Acquisizione dei dati di misurazione tramite cookie
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# Acquisizione dei dati di misurazione tramite cookie{#acquiring-measurement-data-through-cookies}

{{eol}}

Come parte dei dati di misurazione della linea di base raccolti, Sensor raccoglie i cookie di dominio inviati dal computer di un visitatore quando effettua una richiesta dal server web.

Questo include sia cookie persistenti che di sessione impostati dal sito web quando un visitatore interagisce con il sistema.

Nella maggior parte dei casi, i siti web impostano cookie persistenti per identificare i visitatori o acquisire gli input degli utenti da utilizzare nelle sessioni dei visitatori successive. Tutte le informazioni scritte e memorizzate nei cookie persistenti possono essere acquisite e utilizzate insieme a tutti gli altri dati di misurazione all’interno del server di Data Workbench.

Un esempio di cookie persistente di questo tipo potrebbe includere un identificatore del cliente sotto forma di una chiave numerica presente all’interno di un cookie specifico del dominio che risiede nel computer del visitatore. Oltre a identificare l’utente come visitatore di ritorno, il cookie persistente può anche essere utilizzato per identificare ulteriormente il visitatore come cliente di ritorno o per collegare il visitatore alle informazioni contenute in un database del cliente per consentire la visualizzazione offline delle informazioni demografiche dei clienti all’interno di [!DNL Site] e utilizzati per l’analisi interattiva.

I cookie di sessione possono essere un buon meccanismo per raccogliere l’input dell’utente tramite campi modulo o altri elementi dinamici interattivi all’interno del sito web. Nel caso di un sito web che implementa moduli per acquisire dati di input specifici dell’utente, le informazioni rimangono nel cookie di sessione solo per tutto il tempo in cui la sessione è attiva. Quando un utente abbandona il sito web o termina successivamente una sessione, le informazioni non vengono più memorizzate nel computer dell’utente. Tuttavia, le informazioni inserite vengono acquisite da [!DNL Sensor] e resi disponibili come dati di misurazione all&#39;interno di [!DNL Site].

Di seguito è riportato un esempio di utilizzo di un cookie di sessione per acquisire una singola variabile di modulo immessa da un visitatore.

```
<html> 
<head> 
<title>Cookie Collection </title> 
 
<script language="JavaScript"> 
function AppendFormValues() 
{ 
 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
document.cookie = cookie; 
 
testform.submit(); 
 
} 
</script> 
</head> 
<body> 
<form name="testform" method="post" action="nextpage.asp"> 
<input type="text" size=15 name="name"><br />enter name 
<br><br> 
 
<a href="javascript:AppendFormValues();">Click Here To </a><br /><br /> 
<br /><br /><br /> 
 
</body> 
</html> 
```

In questo esempio, viene chiamata una funzione per impostare un cookie di sessione sul computer del visitatore con il nome del campo e il valore inserito nel campo modulo. Quando il modulo viene inviato e viene richiesta la pagina Web successiva, il cookie di sessione viene passato al server web e raccolto da [!DNL Sensor]. I seguenti dati sono quindi disponibili all’interno del server di Data Workbench per l’utilizzo nell’analisi dei dati:

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_1 | Valore associato al cookie v_1. Questo valore rappresenta il NOME immesso nel campo modulo che ha determinato l’impostazione del cookie di sessione. | v_1=John Smith |

I cookie di sessione possono essere utilizzati anche per acquisire in modo iterativo i campi del modulo o una moltitudine di variabili JavaScript incorporate presenti in una pagina HTML. Nell’esempio seguente, JavaScript viene utilizzato per acquisire in modo ricorsivo qualsiasi campo del modulo presente all’interno di un file HTML e impostare un cookie di sessione con le coppie nome=valore appropriate.

```
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
var cookie="formcookie="; 
for (i=0; i<document.testform.length; i++){ 
if (document.testform.elements[i].type =="radio") {            
if (document.testform.elements[i].checked){ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
else if (document.testform.elements[i].type =="select") { 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var optionindex = eval(document.testform.elements[i].selectedIndex); 
var formvalue = document.testform.elements[i].options[optionindex].value;             
cookie += formitem + "=" + formvalue + "&"; 
} 
else{ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
document.cookie = cookie; 
document.testform.submit(); 
} 
 
</script>
```

In questo esempio, nel computer del visitatore viene impostato un cookie di sessione con il nome e il valore di ogni campo del modulo presente all’interno del modulo. Sono inclusi campi di input, caselle di controllo, pulsanti di scelta, caselle di selezione e aree di testo. Come si può notare in questo esempio, poiché il numero di campi modulo è sconosciuto, è necessario acquisire tutti i valori del nome modulo e del campo come una singola stringa, delimitata da una e commerciale. Questo passaggio deve essere effettuato a causa di un limite al numero di cookie che un utente può avere sul proprio computer in un determinato momento. Microsoft Internet Explorer consente la presenza di soli venti (20) cookie di sessione prima che inizi a eliminare il meno recente.
