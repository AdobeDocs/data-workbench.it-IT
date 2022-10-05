---
description: Ogni DPU da cui il dashboard deve visualizzare i dati deve disporre di una licenza API query.
title: Verifica abilitazione API della query
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# Verifica abilitazione API della query{#verifying-query-api-enablement}

{{eol}}

Ogni DPU da cui il dashboard deve visualizzare i dati deve disporre di una licenza API query.

Di seguito sono riportate alcune istruzioni su come convalidare l’API di query installata e abilitata.

1. Trova il certificato del server di Data Workbench.
1. Apri il certificato in un editor di testo.
1. Assicurati che la linea `Product = Query API` esiste nel certificato.
1. In **[!UICONTROL Trace]** aprire la cartella [!DNL InsightServer64.log] in un editor di testo.
1. Nelle ultime voci del registro di avvio, assicurati che la riga `Enabling Query API (licensed)` appare.

* Se l’API di query non è abilitata, verrà visualizzata la voce `Not enabling Query API (not licensed)`.
* Se non trovi voci di registro o sospetti che il server di Data Workbench sia stato riavviato dopo l’aggiunta dell’API Query, riavvia il server di Data Workbench e controlla il registro.

   Se non riesci a convalidare l’abilitazione dell’API di query, contatta l’Assistenza clienti di Adobe.
