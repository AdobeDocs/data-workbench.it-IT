---
description: Gli esperimenti controllati sono test che consentono di confrontare i risultati ottenuti da un gruppo di campioni sperimentali con quelli di un gruppo di controllo standard.
solution: Insight,Analytics
title: Esperimenti controllati da Workbench dati
topic: Data workbench
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Esperimenti controllati da Workbench dati{#data-workbench-controlled-experiments}

Gli esperimenti controllati sono test che consentono di confrontare i risultati ottenuti da un gruppo di campioni sperimentali con quelli di un gruppo di controllo standard.

Site consente di implementare, misurare e analizzare esperimenti controllati e i relativi risultati in relazione a diversi aspetti del sito Web. In questo modo è possibile testare le ipotesi relative al miglioramento delle prestazioni del sito Web prima di spendere tempo significativo o denaro completamente implementando le modifiche proposte.

>[!NOTE]
>
>Gli esperimenti sul sito possono essere analizzati solo nei set di dati in cui l&#39;unico metodo di identificazione del visitatore in uso è il metodo di cookie persistente [!DNL Sensor] impostato. I sensori in esecuzione su server J2EE (JBoss, Tomcat, WebLogic e WebSphere) non supportano la sperimentazione controllata. Per ulteriori informazioni, consulta la sezione seguente.

Utilizzando Site, potete implementare esperimenti A/B, A/B/A e controllati multivariati per raccogliere dati di test sufficienti a fornire dati statisticamente precisi per una valutazione dettagliata delle ipotesi, senza influire sulle prestazioni correnti del sito Web.
