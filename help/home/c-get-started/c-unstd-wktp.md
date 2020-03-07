---
description: In Workspace puoi organizzare e accedere a tutte le aree di lavoro e ai rapporti.
solution: Analytics
title: Workshop
topic: Data workbench
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Workshop{#worktops}

In Workspace puoi organizzare e accedere a tutte le aree di lavoro e ai rapporti.

Nella maggior parte dei casi, il [!DNL Worktop] messaggio viene visualizzato immediatamente dopo l&#39;apertura di Workbench dati. Le funzioni della barra laterale [!DNL Worktop] includono l’interfaccia a schede. Inoltre, la barra laterale consente di aggiungere visualizzazioni e accedere a funzioni utilizzate regolarmente.

**Worktop**

![](assets/client-wktp.png)

Consente [!DNL Worktop] inoltre di creare e salvare aree di lavoro e rapporti nuovi e aggiornati, nonché di pubblicare aree di lavoro e rapporti sul server di Workbench dati, affinché altri possano accedervi.

La tabella [!DNL Worktop] degli elementi riportata di seguito descrive ogni elemento del [!DNL Worktop].

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689"> 
 <tbody> 
  <tr> 
   <td colname="col1"> Barra laterale </td> 
   <td colname="col2"> <p>La barra laterale fornisce contesto e controllo per le aree di lavoro, oltre alla conoscenza dello stato corrente di un’area di lavoro e all’accesso alle funzioni utilizzate regolarmente. Nella barra laterale sono disponibili le seguenti funzioni: </p> <p> <b>Connessione:</b> Indicatore di stato che mostra lo stato online. Fare clic sullo stato della connessione per attivare o disattivare <span class="wintitle"> Work Online</span>. Consultate <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Utilizzo offline e online</a>. </p> <p> <b>Profilo:</b> Indicatore del profilo corrente in uso. </p> <p> <b>A Partire Da: Indicatore </b>di stato che mostra l'aggiornamento dei dati nel set di dati del profilo. Questi dati vengono scaricati ed elaborati dal server DPU, che può verificarsi solo quando si lavora online. </p> <p> <b>Confidenza query/esempio:</b> Indicatore del completamento della query. Quando lo stato viene interrogato al 100%, tutti i dati sono stati interrogati. </p> <p> <b>Aggiungi:</b> Consente di aggiungere visualizzazioni quali pannelli, legende e tabelle alla barra laterale. Consulta <a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06"> Aggiunta di visualizzazioni alla barra laterale</a>. </p> <p> <b>Opzioni:</b> Consente di ripristinare una precedente impostazione della barra laterale e di nascondere automaticamente la barra laterale. </p> <p>Le impostazioni della barra laterale vengono salvate nel file <span class="filepath"> sidebar.vw</span> quando si chiude Workbench dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sottodirectory Tab e Subtab o Drop-down (non visualizzate) </p> </td> 
   <td colname="col2"> <p>Ogni scheda visualizzata sul <span class="wintitle"> piano di lavoro</span> corrisponde al nome del profilo di <i>lavoro della scheda</i>\Workspaces\<i>scheda name</i> folder all'interno della directory di installazione di Workbench dati e rappresenta un particolare tipo di informazioni, ad esempio dashboard, attività, acquisizione, visitatori e così via. Per impostazione predefinita, le sottocartelle nella cartella del nome della scheda sono visualizzate come sottoschede, ma possono anche essere visualizzate come sottodirectory. Consultate <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> Personalizzazione delle schede</a>del piano di lavoro. </p> <p> <p>Nota:  Ciascun profilo di Workbench dati viene fornito con un set standard di schede. Poiché l’implementazione può essere completamente personalizzata, le aree di lavoro (e, di conseguenza, le schede) visualizzate possono essere diverse da quanto documentato in questa guida. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stato profilo </td> 
   <td colname="col2"> Fornisce lo stato della connessione al server Workbench dati e il nome del profilo attualmente caricato. Sotto l’indicatore online, viene visualizzato il campo Data e ora di fine per i dati nel set di dati del profilo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Riduci a icona, Ingrandisci, Chiudi </td> 
   <td colname="col2"> Funzioni Windows standard. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniature </td> 
   <td colname="col2"> <p>Una miniatura è un'istantanea di un'area di lavoro visualizzata sul <span class="wintitle"> piano di lavoro</span>. Ogni volta che salvate l’area di lavoro, viene creata una nuova istantanea. Le miniature consentono di identificare rapidamente una particolare area di lavoro sul <span class="wintitle"> piano di lavoro</span>. </p> <p>Per aprire un’area di lavoro, fate clic sulla miniatura. </p> <p> <p>Nota:  Ciascun profilo di Workbench dati viene fornito con un set standard di aree di lavoro. Poiché l’implementazione può essere completamente personalizzata, le aree di lavoro (e, di conseguenza, le miniature) visualizzate possono essere diverse da quanto documentato in questa guida. </p> </p> <p>Per ulteriori informazioni sulle aree di lavoro, consultate <a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6"> Configurazione della barra laterale</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Messaggi di errore </td> 
   <td colname="col2"> <p>I messaggi di errore vengono visualizzati in rosso sotto lo stato. Per le descrizioni del codice di stato, vedete <a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>. </p> <p>Ad esempio: 403_Forbidden. </p> </td> 
  </tr> 
 </tbody> 
</table>

