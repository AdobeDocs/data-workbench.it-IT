---
description: Regole di sintassi per le formule.
solution: Analytics
title: Sintassi per qualsiasi espressione
topic: Data workbench
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sintassi per qualsiasi espressione{#syntax-for-any-expression}

Regole di sintassi per le formule.

* In una formula, le parole chiave sono sensibili all&#39;uso di maiuscole e minuscole e devono essere digitate esattamente come appaiono.
* Quando si trovano in una formula, in una metrica, in una dimensione e in un filtro che include spazi, i nomi devono utilizzare caratteri di sottolineatura tra le parole. Ad esempio: [!DNL Page_Views]
* Per le stringhe all&#39;interno di espressioni, è necessario evitare determinate virgolette singole, virgolette doppie e barre rovesciate. Ad esempio:

   * [!DNL “can’t”] è accettabile e non deve essere fuggito, ma [!DNL ‘can’t’] è inaccettabile e deve essere evitato come [!DNL ‘can\’t’].

   * [!DNL c:\windows] deve essere fuggito come [!DNL c:\\windows].

