---
description: Il sensore, se utilizzato su un server, può raccogliere i campi dei dati evento da qualsiasi intestazione o variabile di richiesta o risposta HTTP valida disponibile tramite l’API del server.
title: Campi estensibili
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# Campi estensibili{#extensible-fields}

Il sensore, se utilizzato su un server, può raccogliere i campi dei dati evento da qualsiasi intestazione o variabile di richiesta o risposta HTTP valida disponibile tramite l’API del server.

Per raccogliere tali campi di dati, devi specificare i campi di intestazione o le variabili desiderate nel file di configurazione [!DNL txlogd.conf] per [!DNL Sensor].

* [Intestazioni richieste](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [Variabili di server](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## Intestazioni richieste {#section-22766692b45546d8bfc93dbe3bc9368f}

Di seguito è riportata la sintassi per specificare un campo di intestazione della richiesta da raccogliere (ad esempio, Host, Accept-Encoding, Keep-Alive e così via) in [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

I dati raccolti vengono registrati da [!DNL Sensor] in un campo denominato &quot;cs(RequestHeaderName)&quot; nei file [!DNL .vsl] creati da [!DNL data workbench server]. Ad esempio, per raccogliere il valore specifico dell&#39;intestazione della richiesta dall&#39;intestazione della richiesta &quot;Host&quot;, digitare &quot;HostIntestazioneRegistro&quot; in [!DNL txlogd.conf]. I dati vengono registrati nel campo &quot;cs(Host)&quot; nel record di dati dell&#39;evento.

## Variabili del server {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] può raccogliere i campi di dati dalle intestazioni di risposta o dalle variabili del server con accesso API utilizzando le voci SpecialLogField incluse nel  [!DNL txlogd.conf] file. È inoltre possibile utilizzare le voci &quot;SpecialLogField&quot; in aggiunta o al posto delle voci &quot;LogHeader&quot; per raccogliere le intestazioni di richiesta. Consulta [Richiedi intestazioni](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). L’opzione intestazioni della richiesta rimane disponibile per la compatibilità con le versioni precedenti.

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
   <td colname="col1"> cs(log field) </td> 
   <td colname="col2"> Il nome del campo in cui vengono registrati i dati raccolti nel record di dati dell’evento e i file <span class="filepath"> .vsl </span> creati dal server di Data Workbench <span class="keyword"> </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>Qualsiasi variabile server disponibile per <span class="wintitle"> Sensor </span> tramite l'API del server </p> <p>Esempio: response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stadio </td> 
   <td colname="col2"> <p>Vys_log o vys_cookie </p> <p>Per specificare lo stadio è necessario sapere quali variabili del server sono disponibili per vys_log e vys_cookie. </p> <p>Esempio: Per la risposta serverVariable.p3p, immetti vys_log. </p> </td> 
  </tr> 
 </tbody> 
</table>

Per assistenza nella configurazione di [!DNL Sensor] per la raccolta dei campi di record dei dati evento estensibili, contatta Adobe Consulting Services.
