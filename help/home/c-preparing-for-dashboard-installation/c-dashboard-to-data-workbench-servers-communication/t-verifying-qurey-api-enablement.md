---
description: Ogni DPU da cui il dashboard deve visualizzare i dati deve disporre di una licenza API Query.
solution: Analytics
title: Verifica abilitazione API query
topic: Data workbench
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verifica abilitazione API query{#verifying-query-api-enablement}

Ogni DPU da cui il dashboard deve visualizzare i dati deve disporre di una licenza API Query.

Di seguito sono riportate alcune istruzioni su come convalidare l&#39;API Query installata e abilitata.

1. Trova il certificato del server workbench dati.
1. Aprite il certificato in un editor di testo.
1. Verificate che la riga `Product = Query API` esista nel certificato.
1. Nella **[!UICONTROL Trace]** cartella, aprite il file [!DNL InsightServer64.log] in un editor di testo.
1. Nelle ultime voci del registro di avvio, accertatevi che la riga `Enabling Query API (licensed)` venga visualizzata.

* Se l&#39;API Query non è abilitata, verrà visualizzata la voce `Not enabling Query API (not licensed)`.
* Se non vengono visualizzate voci di registro o si sospetta che il server workbench dati sia stato riavviato dall&#39;aggiunta dell&#39;API Query, riavviare il server workbench dati e controllare il registro.

   Se non riuscite a convalidare l&#39;abilitazione dell&#39;API Query, contattate Adobe ClientCare per assistenza.
