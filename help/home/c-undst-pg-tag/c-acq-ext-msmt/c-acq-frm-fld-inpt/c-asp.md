---
description: Le pagine Web sono spesso strutturate utilizzando il linguaggio di programmazione ASP (Active Server Pages).
solution: Analytics
title: Informazioni specifiche ASP
topic: Data workbench
uuid: 552288cb-b775-4121-8869-322f2a26932b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informazioni specifiche ASP{#asp-specific-information}

Le pagine Web sono spesso strutturate utilizzando il linguaggio di programmazione ASP (Active Server Pages).

ASP è una tecnologia Microsoft che viene eseguita in IIS (Internet Information Services). Quando un browser richiede un file ASP, IIS trasmette la richiesta al motore ASP. Il motore ASP legge il file ASP, riga per riga ed esegue gli script nel file. Infine, il file ASP viene restituito al browser come HTML semplice. ASP fornisce oggetti RESPOND o REQUEST che, oltre ad altri usi, consentono la risposta o la richiesta di query utente o di dati inviati da moduli HTML.

In alcuni casi, è possibile che non si desideri aggiungere i valori immessi nei moduli all&#39;URL visualizzato nella barra degli indirizzi del browser di un utente o visibile all&#39;interno del codice HTML stesso. JavaScript semplice sul lato server consente di aggiungere al file di registro i nomi dei campi del modulo e i rispettivi valori senza renderli disponibili nel browser dell&#39;utente né incorporarli nel file HTML. Per acquisire i valori effettivi del modulo immessi in particolari moduli all&#39;interno del sito Web, è necessario aggiungere alcune righe di codice per aggiungere i valori del modulo alla richiesta di registro.

Nella pagina di elaborazione di un modulo, includere il seguente codice per aggiungere i valori del modulo immessi ai dati della richiesta (oltre a scrivere i valori del modulo inviato in un database esterno o in un&#39;altra posizione):

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

In questo modo i valori del modulo verranno aggiunti in base alla definizione data alla richiesta per la [!DNL Form Processing] pagina. All&#39;interno dei dati di registro, i valori aggiunti sarebbero disponibili come stringhe di query della [!DNL Form Processing] pagina, come illustrato di seguito. Ad esempio, v_1, v_2, v_3 e v_4 sono ora stringhe di query contenenti i dati immessi nei campi modulo appropriati. La sintassi descritta nell&#39;esempio sopra può essere duplicata per tutti i campi e i valori aggiuntivi del modulo che si desidera acquisire.

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Se si desidera acquisire tutti i campi e i valori del modulo e renderli disponibili per l&#39;analisi, è possibile utilizzare la sintassi seguente:

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 
```

Questo esempio considera tutti i campi modulo presenti nell’HTML insieme ai rispettivi valori e li aggiunge come stringhe di query alla voce di registro per la [!DNL Form Processing] pagina. Va notato che questo includerebbe tutti i campi nascosti presenti nel modulo.

I dati del registro verranno aumentati come descritto nella tabella seguente:

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_1 | Valore associato alla stringa query NAME | v_1=John Smith |
| v_2 | Valore associato alla stringa query CITY | v_2=Los Angeles |
| v_3 | Valore associato alla stringa di query STATE | v_3=California |
| v_4 | Valore associato alla stringa query ZIP | v_4=90210 |

