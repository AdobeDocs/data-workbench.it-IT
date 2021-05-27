---
description: Ogni DPU da cui il dashboard deve visualizzare i dati deve disporre di una licenza API query.
title: Verifica abilitazione API della query
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# Verifica abilitazione API della query{#verifying-query-api-enablement}

Ogni DPU da cui il dashboard deve visualizzare i dati deve disporre di una licenza API query.

Di seguito sono riportate alcune istruzioni su come convalidare l’API di query installata e abilitata.

1. Trova il certificato del server di Data Workbench.
1. Apri il certificato in un editor di testo.
1. Assicurati che la riga `Product = Query API` esista nel certificato.
1. Nella cartella **[!UICONTROL Trace]** , apri [!DNL InsightServer64.log] in un editor di testo.
1. Nelle ultime voci del registro di avvio, assicurati che venga visualizzata la riga `Enabling Query API (licensed)`.

* Se l’API di query non è abilitata, verrà visualizzata la voce `Not enabling Query API (not licensed)`.
* Se non trovi voci di registro o sospetti che il server di Data Workbench sia stato riavviato dopo l’aggiunta dell’API Query, riavvia il server di Data Workbench e controlla il registro.

   Se non riesci a convalidare l’abilitazione dell’API di query, contatta l’Assistenza clienti di Adobe.
