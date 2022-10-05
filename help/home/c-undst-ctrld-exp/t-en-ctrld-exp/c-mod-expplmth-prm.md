---
description: Modifica del parametro ExpPartialMatch (facoltativo)
title: Modifica del parametro ExpPartialMatch (facoltativo)
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 18%

---

# Modifica del parametro ExpPartialMatch (facoltativo){#modifying-the-exppartialmatch-parameter-optional}

{{eol}}

Se desideri abilitare gli esperimenti controllati per mappare nuovamente l’intero sito web o un’intera sottodirectory del sito web in un’altra posizione, puoi impostare il parametro ExpPartialMatch nella sezione [!DNL txlogd.conf] su &quot;on&quot;. Il valore predefinito è &quot;off&quot;.

Di seguito è riportato un esempio del parametro ExpPartialMatch :

[!DNL ExpPartialMatch off]

Presta molta attenzione quando imposti questo parametro su &quot;on&quot; perché può causare un remapping involontario dell&#39;intero sito web.
