---
description: Il parametro ExpCookieURL può essere utilizzato per verificare che l'esperimento controllato funzioni correttamente.
solution: Analytics
title: Modifica del parametro ExpCookieURL (facoltativo)
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---

# Modifica del parametro ExpCookieURL (facoltativo){#modifying-the-expcookieurl-paramter-optional}

{{eol}}

Il parametro ExpCookieURL può essere utilizzato per verificare che l&#39;esperimento controllato funzioni correttamente.

Questo parametro definisce l’URL di una pagina virtuale che, quando richiesto, inserisce in un esperimento e in un gruppo specifici e quindi reindirizza alla directory principale del sito web. Da quel punto fino alla fine dell&#39;esperimento, fai parte dell&#39;esperimento e del gruppo specificati.

La pagina predefinita per questo parametro è [!DNL setcookie.htm], ma puoi utilizzare qualsiasi URL virtuale valido.

>[!NOTE]
>
>Deve essere un URL virtuale e non deve essere una pagina reale o un elemento di contenuto esistente. Nessun file sul server Web nel percorso specificato con il nome specificato.

Di seguito è riportato un esempio del parametro ExpCookieURL :

[!DNL ExpCookieURL /setcookie.htm]
