---
description: Le espressioni metriche, dimensioni e filtri possono utilizzare identificatori per fare riferimento a metriche, dimensioni e filtri con nome.
title: Sintassi per gli identificatori
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
exl-id: 79bc5585-7b21-4a9d-b044-28ff4bc5a885
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 3%

---

# Sintassi per gli identificatori{#syntax-for-identifiers}

{{eol}}

Le espressioni metriche, dimensioni e filtri possono utilizzare identificatori per fare riferimento a metriche, dimensioni e filtri con nome.

Questi identificatori sono sensibili all&#39;uso di maiuscole e minuscole e devono essere digitati esattamente come sono definiti.

Un identificatore valido può contenere uno o più dei seguenti elementi:

* Sottolineato (_). I caratteri di sottolineatura in un identificatore rappresentano gli spazi nel nome della metrica, della dimensione o del filtro. Ad esempio, la dimensione Referente sessione viene indicata come [!DNL Session_Referrer] in un&#39;espressione.
* Indicatori percentuali (%)
* Lettere maiuscole (A-Z)
* Lettere minuscole (a-z)
* Simbolo del dollaro ($)
* Numeri (0-9), ad eccezione del primo carattere di un identificatore.
* Caratteri non ASCII

Tutti gli altri caratteri non sono validi in un identificatore.

Queste stesse regole si applicano ai nomi di metriche, dimensioni e filtri utilizzati al di fuori delle espressioni, tranne per il fatto che i nomi possono contenere spazi ma non caratteri di sottolineatura. Ad esempio, puoi definire la dimensione Referente sessione nel [!DNL Transformation.cfg] file come referente sessione, ma non [!DNL Session_Referrer].
