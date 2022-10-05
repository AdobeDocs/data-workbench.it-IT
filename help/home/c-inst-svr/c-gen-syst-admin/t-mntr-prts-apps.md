---
description: Per monitorare più accuratamente l'implementazione, è possibile monitorare tutte le porte sui computer server e i prodotti software in esecuzione su ciascuna di queste porte.
title: Monitoraggio di porte e applicazioni
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
exl-id: 418b2e5c-42ec-40f0-9cae-375194288143
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 4%

---

# Monitoraggio di porte e applicazioni{#monitoring-ports-and-applications}

{{eol}}

Per monitorare più accuratamente l&#39;implementazione, è possibile monitorare tutte le porte sui computer server e i prodotti software in esecuzione su ciascuna di queste porte.

**Frequenza consigliata:** Ogni 5-10 minuti

Utilizzando un&#39;applicazione o uno script, è possibile monitorare la porta TCP su cui è in esecuzione ogni applicazione (in genere le porte 80 o 443) per assicurarsi che l&#39;applicazione sia associata a tale porta. A tale scopo, è necessario richiedere una pagina dello stato dell&#39;applicazione dal computer che si desidera monitorare.

**Per richiedere la pagina dello stato dell&#39;applicazione**

1. Sul computer che si desidera monitorare, modificare i controlli di accesso per consentire all&#39;applicazione o allo script di monitoraggio di accedere al computer. Per istruzioni, consulta [Configurazione del controllo di accesso](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).
1. Connetti a [!DNL https://IP Address/Status/], dove indirizzo IP è l’indirizzo IP del computer per il quale si desidera ricevere lo stato.

   Esempio: [!DNL https://127.0.0.1/Status/]

   Il computer deve rispondere con una descrizione dello stato del server. Se non risponde, controlla i registri eventi e contatta l’Assistenza clienti Adobe.

   Per ulteriori informazioni su questo tipo di monitoraggio avanzato, contattare i servizi di consulenza Adobe.
