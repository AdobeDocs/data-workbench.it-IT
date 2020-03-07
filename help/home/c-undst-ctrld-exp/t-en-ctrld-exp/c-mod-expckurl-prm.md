---
description: Il parametro ExpCookieURL può essere utilizzato per verificare che l’esperimento controllato funzioni correttamente.
solution: Insight,Analytics
title: Modifica del parametro ExpCookieURL (facoltativo)
topic: Data workbench
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modifica del parametro ExpCookieURL (facoltativo){#modifying-the-expcookieurl-paramter-optional}

Il parametro ExpCookieURL può essere utilizzato per verificare che l’esperimento controllato funzioni correttamente.

Questo parametro definisce l’URL di una pagina virtuale che, quando richiesto, inserisce in un esperimento e in un gruppo specifici e quindi reindirizzerà alla directory principale del sito Web. Da quel momento fino alla fine dell&#39;esperimento, fate parte dell&#39;esperimento e del gruppo specificati.

La pagina predefinita di questo parametro è [!DNL setcookie.htm], ma è possibile utilizzare qualsiasi URL virtuale valido.

>[!NOTE]
>
>Deve essere un URL virtuale e non deve essere una vera pagina o parte del contenuto esistente. Nel server Web non deve essere presente alcun file nel percorso specificato con il nome specificato.

Di seguito è riportato un esempio del parametro ExpCookieURL:

[!DNL ExpCookieURL /setcookie.htm]
