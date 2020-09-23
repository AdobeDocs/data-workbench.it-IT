---
description: Il sensore, se utilizzato su un server, può raccogliere i campi dei dati evento da qualsiasi intestazione o variabile di risposta HTTP valida, disponibile tramite l'API del server.
solution: Analytics
title: Campi estensibili
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---


# Campi estensibili{#extensible-fields}

Il sensore, se utilizzato su un server, può raccogliere i campi dei dati evento da qualsiasi intestazione o variabile di risposta HTTP valida, disponibile tramite l&#39;API del server.

Per raccogliere tali campi di dati, è necessario specificare i campi di intestazione o le variabili desiderate nel file di [!DNL txlogd.conf] configurazione per [!DNL Sensor].

* [Richiedi intestazioni](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [Variabili server](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## Richiedi intestazioni {#section-22766692b45546d8bfc93dbe3bc9368f}

Di seguito è riportata la sintassi per specificare un campo di intestazione della richiesta da raccogliere (ad esempio, Host, Accetta codifica, Mantieni vivo e così via) in [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

I dati raccolti vengono registrati da [!DNL Sensor] un campo denominato &quot;cs(RequestHeaderName)&quot; nei [!DNL .vsl] file creati dal [!DNL data workbench server]. Ad esempio, per raccogliere il valore dell&#39;intestazione della richiesta specifico dall&#39;intestazione della richiesta &quot;Host&quot;, digitare &quot;Host di intestazione log&quot; in [!DNL txlogd.conf]. I dati vengono registrati nel campo &quot;cs(Host)&quot; nel record di dati dell&#39;evento.

## Variabili server {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] è possibile raccogliere i campi di dati dalle intestazioni di risposta o dalle variabili del server accessibili tramite API utilizzando le voci SpecialLogField incluse nel [!DNL txlogd.conf] file. Per raccogliere le intestazioni delle richieste è inoltre possibile utilizzare le voci &quot;SpecialLogField&quot;, oltre alle voci &quot;LogHeader&quot; o al posto di tali voci. Consultate [Richiedi intestazioni](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). L&#39;opzione intestazioni richiesta rimane disponibile per la compatibilità con le versioni precedenti.

Di seguito è riportata la sintassi per specificare un &quot;SpecialLogField&quot; in [!DNL txlogd.conf]:

```
SpecialLogField cs(log field) = serverVariable stage
```

La tabella seguente include le descrizioni dei componenti di una voce &quot;SpecialLogField&quot;.

<table id="table_053D5F34D56E4B15A85CA3B4FAD6E1B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(campo di registro) </td> 
   <td colname="col2"> Il nome del campo in cui vengono registrati i dati raccolti nel record di dati dell'evento e i <span class="filepath"> file </span> .vsl creati dal server workbench <span class="keyword"> dati </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>Qualsiasi variabile server disponibile per <span class="wintitle"> Sensor </span> tramite l'API del server </p> <p>Esempio: response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>Vys_log o vys_cookie </p> <p>Per specificare l’area di visualizzazione è necessario conoscere le variabili del server disponibili per vys_log e vys_cookie. </p> <p>Esempio: Per serverVariable response.p3p, è necessario immettere vys_log. </p> </td> 
  </tr> 
 </tbody> 
</table>

Per assistenza nella configurazione [!DNL Sensor] per la raccolta dei campi dei record di dati di eventi estensibili, contattare  Adobe Consulting Services.
