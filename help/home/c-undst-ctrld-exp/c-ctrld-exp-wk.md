---
description: In un esperimento, potete definire un numero qualsiasi di gruppi di test oltre al gruppo di controllo.
solution: Analytics,Analytics
title: Come funzionano gli esperimenti controllati?
topic: Data workbench
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---


# Come funzionano gli esperimenti controllati?{#how-do-controlled-experiments-work}

In un esperimento, potete definire un numero qualsiasi di gruppi di test oltre al gruppo di controllo.

Quando un esperimento è in esecuzione, tutti i visitatori del sito Web diventano parte dell’esperimento, sia nell’ambito di un gruppo di test che del gruppo di controllo, non appena accedono a qualsiasi pagina coinvolta nell’esperimento. I visitatori vengono assegnati ai gruppi di esperimenti in modo casuale, in proporzioni definite durante la configurazione dell’esperimento.

Gli esperimenti controllati vengono implementati utilizzando il [!DNL Sensor] software installato su ciascuno dei server di contenuto del cluster Web. Man mano che i server del contenuto ricevono le richieste, vengono selezionati [!DNL Sensor] in modo casuale i visitatori per i gruppi di test e le richieste di pagina vengono reindirizzate al contenuto sperimentale. Quando [!DNL Sensor] seleziona un visitatore per visualizzare il contenuto di prova, la barra dell&#39;indirizzo continua a elencare l&#39;URI richiesto originariamente, ma il visitatore viene instradato all&#39;URI di test. Poiché questo processo avviene internamente nell&#39;applicazione server, gli utenti non sono a conoscenza del momento in cui vengono testati, il che rappresenta una considerazione importante per una sperimentazione imparziale.

[!DNL Sensor] passa gli URI di prova, non l’URI originale visualizzato all’utente, ai file di registro da utilizzare nell’analisi.

I risultati degli esperimenti possono essere facilmente analizzati utilizzando [!DNL Insight] per determinare se l&#39;ipotesi sperimentale che si stava testando è corretta.

>[!NOTE]
>
> Adobe consiglia vivamente di coordinare ed eseguire esperimenti controllati con l&#39;input di quegli individui nell&#39;organizzazione che sono responsabili della configurazione e della manutenzione dei set di dati di analisi.

