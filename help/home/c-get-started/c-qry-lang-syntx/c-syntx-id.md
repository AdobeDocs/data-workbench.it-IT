---
description: Le espressioni di metrica, dimensione e filtro possono utilizzare identificatori per fare riferimento a metriche, dimensioni e filtri denominati.
solution: Analytics
title: Sintassi per gli identificatori
topic: Data workbench
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sintassi per gli identificatori{#syntax-for-identifiers}

Le espressioni di metrica, dimensione e filtro possono utilizzare identificatori per fare riferimento a metriche, dimensioni e filtri denominati.

Questi identificatori sono con distinzione tra maiuscole e minuscole e devono essere digitati esattamente come sono definiti.

Un identificatore valido può contenere uno o più dei seguenti elementi:

* Punti di sottolineatura (_). I caratteri di sottolineatura in un identificatore rappresentano gli spazi nel nome della metrica, della dimensione o del filtro. Ad esempio, la dimensione Referente sessione viene definita come [!DNL Session_Referrer] in un&#39;espressione.
* Indicatori percentuali (%)
* Lettere maiuscole (A-Z)
* Lettere minuscole (a-z)
* Simbolo del dollaro ($)
* Numeri (0-9), ad eccezione del primo carattere di un identificatore.
* Caratteri non ASCII

Tutti gli altri caratteri non sono consentiti in un identificatore.

Queste stesse regole si applicano ai nomi di metriche, dimensioni e filtri quando vengono utilizzati al di fuori delle espressioni, con la differenza che i nomi possono contenere spazi ma non caratteri di sottolineatura. Ad esempio, puoi definire la dimensione Referente sessione nel [!DNL Transformation.cfg] file come Referente sessione, ma non [!DNL Session_Referrer].
