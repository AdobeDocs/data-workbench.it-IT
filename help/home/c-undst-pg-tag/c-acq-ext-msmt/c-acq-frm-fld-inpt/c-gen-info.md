---
description: I valori immessi in un modulo in una pagina Web possono essere raccolti e aggiunti nella stringa di query della pagina successivamente richiesta (all'invio del modulo) tramite l'uso di JavaScript.
solution: Analytics
title: Informazioni generali
topic: Data workbench
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informazioni generali{#general-information}

I valori immessi in un modulo in una pagina Web possono essere raccolti e aggiunti nella stringa di query della pagina successivamente richiesta (all&#39;invio del modulo) tramite l&#39;uso di JavaScript.

Questo è illustrato nell&#39;esempio seguente. Includere questo JavaScript dopo eventuali script di convalida dei moduli utilizzati nelle pagine HTML.

```
<html> 
<head> 
</head> 
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
for(var i = 0; i < document.formname.length; i++) 
{ 
var item = document.formname.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
formvalues += formitem + '=' + formvalue + '&'; 
} 
document.formname.action = document.formname.action + '?' + formvalues; 
 
} 
</script> 
<body> 
<form name="formname" action="thankyou.asp" method="POST" onSubmit="AppendFormValues();"> 
<input name="NAME" size="50" value=""></input>name<br/> 
<input name="CITY" size="50" value=""></input>city<br/> 
<input name="STATE" size="50" value=""></input>state<br/> 
<input name="ZIP" size="10" value=""></input>zip<br /> 
<input type="submit" name="submit" value="submit"/> 
</body> 
</html> 
```

In questo esempio i valori immessi nel modulo dall&#39;utente del browser vengono aggiunti alla pagina successiva &quot;thankyou.asp&quot; indicata nel valore dell&#39;azione FORM come segue:

```
http://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

Con questa richiesta, oltre alle misure di base raccolte da [!DNL Sensor]:

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_1 | Valore associato al campo del modulo NAME | v_1=John Smith |
| v_2 | Valore associato al campo modulo CITY | v_2=Los Angeles |
| v_3 | Valore associato al campo modulo STATE | v_3=California |
| v_4 | Valore associato al campo modulo ZIP | v_4=90210 |

