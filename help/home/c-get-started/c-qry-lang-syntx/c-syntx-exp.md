---
description: Regole di sintassi per le formule.
title: Sintassi per qualsiasi espressione
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%

---

# Sintassi per qualsiasi espressione{#syntax-for-any-expression}

{{eol}}

Regole di sintassi per le formule.

* In una formula, le parole chiave distinguono tra maiuscole e minuscole e devono essere digitate esattamente come appaiono.
* In una formula, i nomi delle metriche, delle dimensioni e dei filtri che includono spazi devono utilizzare caratteri di sottolineatura tra le parole. Ad esempio: [!DNL Page_Views]
* Per le stringhe all’interno di espressioni, è necessario applicare l’escape a determinate virgolette singole, virgolette doppie e barre rovesciate. Esempio:

   * [!DNL “can’t”] è accettabile e non deve essere evitato, ma [!DNL ‘can’t’] è inaccettabile e deve essere evitato come [!DNL ‘can\’t’].

   * [!DNL c:\windows] deve essere evitato come [!DNL c:\\windows].
