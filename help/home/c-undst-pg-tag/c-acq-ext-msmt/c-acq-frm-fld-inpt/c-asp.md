---
description: Le pagine web sono spesso strutturate utilizzando il linguaggio di programmazione ASP (Active Server Pages).
title: Informazioni specifiche ASP
uuid: 552288cb-b775-4121-8869-322f2a26932b
exl-id: f73235e1-d44a-4056-b1f4-a86879c19483
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# Informazioni specifiche ASP{#asp-specific-information}

Le pagine web sono spesso strutturate utilizzando il linguaggio di programmazione ASP (Active Server Pages).

ASP è una tecnologia Microsoft che viene eseguita in IIS (Internet Information Services). Quando un browser richiede un file ASP, IIS passa la richiesta al motore ASP. Il motore ASP legge il file ASP, riga per riga ed esegue gli script nel file. Infine, il file ASP viene restituito al browser come HTML semplice. ASP fornisce oggetti RESPOND o REQUEST che, oltre ad altri utilizzi, consentono la risposta o la richiesta di query utente o dati inviati da moduli HTML.

In alcuni casi, è possibile che non si desideri aggiungere i valori immessi nei moduli all’URL visualizzato nella barra degli indirizzi del browser di un utente o visualizzabile all’interno del codice HTML stesso. JavaScript lato server semplice consente di aggiungere al file di registro i nomi dei campi del modulo e i rispettivi valori senza renderli disponibili nel browser dell’utente o incorporarli nel file HTML. Per acquisire i valori effettivi del modulo immessi in particolari moduli all’interno del sito web, è necessario aggiungere alcune righe di codice per aggiungere i valori del modulo alla richiesta di registro.

Nella pagina di elaborazione di un modulo, includere il codice seguente per aggiungere i valori del modulo immesso ai dati della richiesta (oltre a scrivere i valori del modulo inviato in un database esterno o in un altro percorso):

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

Questo processo aggiunge i valori del modulo come definiti ai dati della richiesta per la pagina [!DNL Form Processing]. All&#39;interno dei dati di log, i valori aggiunti sarebbero disponibili come stringhe di query della pagina [!DNL Form Processing] come illustrato di seguito. Ad esempio, v_1, v_2, v_3 e v_4 sono stringhe di query contenenti i dati immessi nei campi modulo appropriati. La sintassi descritta nell’esempio sopra può essere duplicata per tutti i campi e i valori aggiuntivi del modulo che si desidera acquisire.

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Se si desidera acquisire e rendere disponibili per l’analisi tutti i campi e i valori del modulo, è possibile utilizzare la sintassi seguente:

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 
```

Questo esempio prende tutti i campi modulo presenti nell’HTML insieme ai rispettivi valori e li aggiunge come stringhe di query alla voce di registro per la pagina [!DNL Form Processing]. Va notato che questo includerebbe tutti i campi nascosti presenti all’interno del modulo.

I dati del registro vengono aumentati come descritto nella tabella seguente:

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_1 | Valore associato alla stringa di query NAME | v_1=John Smith |
| v_2 | Valore associato alla stringa di query CITY | v_2=Los Angeles |
| v_3 | Valore associato alla stringa di query STATE | v_3=California |
| v_4 | Valore associato alla stringa di query ZIP | v_4=90210 |
