---
description: In un esperimento è possibile definire un numero qualsiasi di gruppi di test oltre al gruppo di controllo.
solution: Analytics
title: Come funzionano gli esperimenti controllati?
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# Come funzionano gli esperimenti controllati?{#how-do-controlled-experiments-work}

{{eol}}

In un esperimento è possibile definire un numero qualsiasi di gruppi di test oltre al gruppo di controllo.

Quando un esperimento è in esecuzione, tutti i visitatori del sito web partecipano all’esperimento, sia come parte di un gruppo di test o del gruppo di controllo, non appena accedono a una pagina coinvolta nell’esperimento. I visitatori vengono assegnati casualmente ai gruppi di esperimenti, in proporzioni definite durante la configurazione dell’esperimento.

Gli esperimenti controllati vengono implementati utilizzando [!DNL Sensor] software installato su ciascuno dei server di contenuto del cluster web. Man mano che i server di contenuti ricevono le richieste, [!DNL Sensor] seleziona in modo casuale i visitatori per i gruppi di test e reindirizza le richieste di pagina al contenuto sperimentale. Quando [!DNL Sensor] seleziona un visitatore per visualizzare il contenuto del test; la barra degli indirizzi continua a elencare l’URI richiesto originariamente, ma il visitatore viene indirizzato all’URI del test. Poiché questo processo avviene internamente nell’applicazione server, gli utenti non sono a conoscenza di quando vengono testati, il che rappresenta una considerazione importante per la sperimentazione imparziale.

[!DNL Sensor] passa gli URI di test, non l’URI originale visualizzato all’utente, ai file di log da utilizzare nell’analisi.

I risultati degli esperimenti possono essere facilmente analizzati utilizzando [!DNL Insight] per determinare se l&#39;ipotesi sperimentale che stavi testando è corretta.

>[!NOTE]
>
>L’Adobe consiglia vivamente di coordinare ed eseguire esperimenti controllati con l’input degli utenti dell’organizzazione responsabili della configurazione e della manutenzione dei set di dati di analisi.
