---
description: 'null'
solution: Analytics,Analytics
title: Modifica del parametro ExpPartialMatch (facoltativo)
topic: Data workbench
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 14%

---


# Modifica del parametro ExpPartialMatch (facoltativo){#modifying-the-exppartialmatch-parameter-optional}

Se desiderate abilitare gli esperimenti controllati per rimappare l’intero sito Web o un’intera sottodirectory del sito Web in un’altra posizione, potete impostare il parametro ExpPartialMatch nel [!DNL txlogd.conf] file su &quot;on&quot;. Il valore predefinito è &quot;off&quot;.

Di seguito è riportato un esempio del parametro ExpPartialMatch:

[!DNL ExpPartialMatch off]

Prestate molta attenzione quando impostate questo parametro su &quot;on&quot;, perché potrebbe causare un remapping involontario dell’intero sito Web.
