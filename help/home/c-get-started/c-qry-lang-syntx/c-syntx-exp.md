---
description: Regole di sintassi per le formule.
title: Sintassi per qualsiasi espressione
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%

---

# Sintassi per qualsiasi espressione{#syntax-for-any-expression}

Regole di sintassi per le formule.

* In una formula, le parole chiave distinguono tra maiuscole e minuscole e devono essere digitate esattamente come appaiono.
* In una formula, i nomi delle metriche, delle dimensioni e dei filtri che includono spazi devono utilizzare caratteri di sottolineatura tra le parole. Ad esempio: [!DNL Page_Views]
* Per le stringhe all’interno di espressioni, è necessario applicare l’escape a determinate virgolette singole, virgolette doppie e barre rovesciate. Ad esempio:

   * [!DNL “can’t”] è accettabile e non deve essere fuggito, ma  [!DNL ‘can’t’] è inaccettabile e deve essere evitato come  [!DNL ‘can\’t’].

   * [!DNL c:\windows] deve essere evitato come  [!DNL c:\\windows].
