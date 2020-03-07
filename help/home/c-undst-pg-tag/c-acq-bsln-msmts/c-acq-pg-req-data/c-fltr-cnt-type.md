---
description: Lo scopo della funzionalità di filtraggio del tipo di contenuto Sensor è di eliminare la necessità di memorizzare ed elaborare informazioni non utili ai fini dell'analisi.
solution: Analytics
title: Filtrare Per Tipo Di Contenuto
topic: Data workbench
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Filtrare Per Tipo Di Contenuto{#filtering-by-content-type}

Lo scopo della funzionalità di filtraggio del tipo di contenuto Sensor è di eliminare la necessità di memorizzare ed elaborare informazioni non utili ai fini dell&#39;analisi.

Gran parte dei dati di richiesta disponibili tramite l&#39;API di un server Web non è utile per l&#39;analisi aziendale. L&#39;archiviazione e l&#39;elaborazione sono costose e il filtro di tipo [!DNL Sensor’s] contenuto consente di evitare inutili processi di storage ed elaborazione.

Per ottimizzare le prestazioni di elaborazione dei dati del registro web e ridurre la quantità di dati di misurazione da memorizzare, [!DNL Site] acquisisce i dati di misurazione (dati di richiesta, voci di registro, dati di registro e così via) per tutte le richieste di tipo contenuto Web, ad eccezione dei tipi di contenuto specificamente elencati (come fogli di stile CSS, richieste di immagini e così via), che vengono filtrati prima della loro trasmissione al server workbench dati da [!DNL Sensor]. Questo filtro può essere disattivato per un intero server Web e può essere sostituito per un particolare oggetto contenuto aggiungendo la coppia nome-valore &quot;Log=1&quot; alla stringa di query di un particolare oggetto incorporato (ad esempio, [!DNL http://www.mysite.com/advertisement.gif?Log=1]).
