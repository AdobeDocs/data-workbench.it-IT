---
description: Come parte dei dati di misurazione della linea di base raccolti, Sensor raccoglie i cookie di dominio inviati dal computer di un visitatore quando effettua una richiesta dal server Web.
solution: Analytics
title: Acquisizione dei dati di misurazione tramite cookie
topic: Data workbench
uuid: 34cd6baf-6317-4774-8165-58208698b53c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Acquisizione dei dati di misurazione tramite cookie{#acquiring-measurement-data-through-cookies}

Come parte dei dati di misurazione della linea di base raccolti, Sensor raccoglie i cookie di dominio inviati dal computer di un visitatore quando effettua una richiesta dal server Web.

Questo include sia i cookie permanenti che i cookie di sessione impostati dal sito Web quando un visitatore interagisce con il sistema.

Nella maggior parte dei casi, i siti Web impostano cookie persistenti per identificare i visitatori o acquisire l&#39;input dell&#39;utente da utilizzare nelle sessioni dei visitatori successive. Qualsiasi informazione scritta e memorizzata all&#39;interno di cookie persistenti può essere acquisita e utilizzata insieme a tutti gli altri dati di misurazione all&#39;interno del server workbench dati.

Un esempio di tale cookie persistente potrebbe includere un identificatore cliente sotto forma di chiave numerica presente all&#39;interno di un cookie specifico del dominio che risiede nel computer del visitatore. Oltre a identificare l&#39;utente come visitatore di ritorno, il cookie persistente potrebbe essere utilizzato anche per identificare ulteriormente il visitatore come cliente di ritorno o per collegare il visitatore alle informazioni contenute in un database cliente per consentire la visualizzazione delle informazioni demografiche offline del cliente all&#39;interno [!DNL Site] e utilizzate per l&#39;analisi interattiva.

I cookie di sessione possono essere un buon meccanismo per raccogliere l&#39;input dell&#39;utente attraverso i campi del modulo o altri elementi interattivi dinamici all&#39;interno del sito Web. Nel caso di un sito Web che implementa moduli per acquisire dati di input specifici dell&#39;utente, le informazioni restano nel cookie di sessione solo fino a quando la sessione è attiva. Quando un utente esce dal sito Web o termina una sessione, le informazioni non vengono più memorizzate nel computer dell’utente. Tuttavia, le informazioni inserite vengono acquisite da [!DNL Sensor] e rese disponibili come dati di misurazione all’interno [!DNL Site].

Di seguito è riportato un esempio di utilizzo di un cookie di sessione per acquisire una singola variabile del modulo inserita da un visitatore.

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

In questo esempio, viene chiamata una funzione per impostare un cookie di sessione nel computer del visitatore con il nome del campo e il valore immesso nel campo del modulo. Quando il modulo viene inviato e viene richiesta la pagina Web successiva, il cookie di sessione viene passato al server Web e raccolto da [!DNL Sensor]. I seguenti dati sono quindi disponibili all&#39;interno del server workbench dati per l&#39;utilizzo nell&#39;analisi dei dati:

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_1 | Valore associato al cookie v_1. Questo valore rappresenta il NOME immesso nel campo modulo che ha determinato l&#39;impostazione del cookie di sessione. | v_1=John Smith |

I cookie di sessione possono essere utilizzati anche per acquisire in modo iterativo i campi del modulo o una serie di variabili JavaScript incorporate presenti in una pagina HTML. Nell&#39;esempio seguente, JavaScript viene utilizzato per acquisire in modo ricorsivo qualsiasi campo modulo presente in un file HTML e impostare un cookie di sessione con le coppie nome=valore appropriate.

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

In questo esempio, nel computer del visitatore viene impostato un cookie di sessione con il nome e il valore di ogni campo del modulo esistente all&#39;interno del modulo. Sono inclusi campi di input, caselle di controllo, pulsanti di scelta, caselle di selezione e aree di testo. Come si può notare in questo esempio, poiché il numero di campi del modulo è sconosciuto, è necessario acquisire tutti i nomi del modulo e i valori dei campi come una singola stringa, delimitata da una e-mail. Questa operazione deve essere eseguita a causa di un limite al numero di cookie che un utente può avere sul suo computer in un determinato momento. Microsoft Internet Explorer consente la presenza di soli venti (20) cookie di sessione prima che inizi il rilascio del meno recente.
