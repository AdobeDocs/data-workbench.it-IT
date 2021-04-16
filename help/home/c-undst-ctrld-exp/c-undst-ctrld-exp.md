---
description: Gli esperimenti controllati sono test che consentono di confrontare i risultati ottenuti da un gruppo di campioni sperimentali con quelli di un gruppo di controllo standard.
solution: Analytics,Analytics
title: Esperimenti controllati da Data Workbench
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
exl-id: 40bcf6a4-c722-427c-81ac-45dec1eae0b5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Data Workbench esperimenti controllati{#data-workbench-controlled-experiments}

Gli esperimenti controllati sono test che consentono di confrontare i risultati ottenuti da un gruppo di campioni sperimentali con quelli di un gruppo di controllo standard.

Il sito consente di implementare, misurare e analizzare gli esperimenti controllati e i relativi risultati in relazione a diversi aspetti del sito web. In questo modo è possibile testare le ipotesi sul miglioramento delle prestazioni del sito web prima di trascorrere molto tempo o denaro implementando completamente le modifiche proposte.

>[!NOTE]
>
>Gli esperimenti del sito possono essere analizzati solo nei set di dati in cui l’unico metodo di identificazione del visitatore in uso è il [!DNL Sensor] imposta il metodo di cookie persistente. I sensori in esecuzione su server J2EE (JBoss, Tomcat, WebLogic e WebSphere) non supportano la sperimentazione controllata. Per ulteriori informazioni, consulta la sezione seguente.

Utilizzando Sito, puoi implementare esperimenti A/B, A/B/A e controllati multivariati per raccogliere dati di test sufficienti a fornire dati statisticamente precisi per una valutazione dettagliata della tua ipotesi, senza influire sulle prestazioni correnti del sito web.
