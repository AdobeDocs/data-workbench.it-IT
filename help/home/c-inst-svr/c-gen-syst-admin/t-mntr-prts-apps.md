---
description: Per monitorare più accuratamente l'implementazione, è possibile monitorare tutte le porte sui computer server e i prodotti software in esecuzione su ciascuna di queste porte.
solution: Analytics
title: Monitoraggio di porte e applicazioni
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 4%

---


# Monitoraggio di porte e applicazioni{#monitoring-ports-and-applications}

Per monitorare più accuratamente l&#39;implementazione, è possibile monitorare tutte le porte sui computer server e i prodotti software in esecuzione su ciascuna di queste porte.

**Frequenza consigliata:** Ogni 5-10 minuti

Utilizzando un&#39;applicazione o uno script, è possibile monitorare la porta TCP su cui è in esecuzione ogni applicazione (in genere la porta 80 o 443) per assicurarsi che l&#39;applicazione sia associata a tale porta. A questo scopo, è necessario richiedere una pagina di stato dell&#39;applicazione dal computer da monitorare.

**Per richiedere la pagina dello stato dell&#39;applicazione**

1. Nel computer da monitorare, modificare i controlli di accesso per consentire all&#39;applicazione di monitoraggio o script di accedere al computer. Per istruzioni, vedere [Configurazione del controllo](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)di accesso.
1. Connettiti a [!DNL https://IP Address/Status/], dove Indirizzo IP è l&#39;indirizzo IP del computer per il quale si desidera ricevere lo stato.

   Esempio: [!DNL https://127.0.0.1/Status/]

   Il computer deve rispondere con una descrizione dello stato del server. In caso contrario, controllate i registri eventi e contattate &#39;Assistenza clienti del Adobe.

   Per maggiori informazioni su questo tipo di monitoraggio avanzato, contattare  Adobe Consulting Services.

