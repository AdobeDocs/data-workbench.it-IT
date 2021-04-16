---
description: La funzionalità di filtraggio del tipo di contenuto di Sensor ha lo scopo di eliminare la necessità di memorizzare ed elaborare informazioni non utili a scopo di analisi.
title: Filtrare per tipo di contenuto
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# Filtrare per tipo di contenuto{#filtering-by-content-type}

La funzionalità di filtraggio del tipo di contenuto di Sensor ha lo scopo di eliminare la necessità di memorizzare ed elaborare informazioni non utili a scopo di analisi.

Gran parte dei dati di richiesta disponibili tramite l’API di un server web non è utile nell’analisi aziendale. L&#39;archiviazione e l&#39;elaborazione sono costose e il filtro [!DNL Sensor’s] del tipo di contenuto ti consente di evitare l&#39;archiviazione e l&#39;elaborazione non necessarie.

Per ottimizzare le prestazioni di elaborazione dei dati dei log web e ridurre la quantità di dati di misurazione da memorizzare, [!DNL Site] acquisisce i dati di misurazione (dati di richiesta, voci di registro, dati di registro e così via) per tutte le richieste di tipo contenuto web, ad eccezione dei tipi di contenuto elencati in modo specifico (come fogli di stile CSS, richieste di immagini e così via), che vengono filtrati prima che vengano trasmessi al server di Data Workbench da [!DNL Sensor]. Questo filtro può essere disabilitato per un intero server web e può essere sostituito per un particolare oggetto contenuto aggiungendo la coppia nome-valore &quot;Log=1&quot; alla stringa query di un particolare oggetto incorporato (ad esempio, [!DNL http://www.mysite.com/advertisement.gif?Log=1]).
