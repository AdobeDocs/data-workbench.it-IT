---
description: I parametri stringa e numerici assumono come valori rispettivamente stringhe e numeri.
solution: Analytics
title: Parametri stringa e numerici
topic: Data workbench
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Parametri stringa e numerici{#string-and-numeric-parameters}

I parametri stringa e numerici assumono come valori rispettivamente stringhe e numeri.

È possibile utilizzarli in modo intercambiabile, ma i parametri numerici devono essere definiti in modo da avere un valore numerico. Potete fare riferimento a parametri numerici e di stringa durante la definizione di trasformazioni, condizioni e dimensioni estese e potete fare riferimento a più di un parametro nella stessa riga.

Non è possibile fare riferimento a parametri stringa e numerici in [!DNL Input] o [!DNL Output] campi, ma è possibile utilizzare un parametro stringa per definire un campo di input costante. Inoltre, non è possibile fare riferimento a parametri numerici e di stringa nei decoder o nei gruppi di decodificatori.

Questo esempio mostra un [!DNL Log Processing Dataset Include] file che definisce un parametro stringa e un parametro numerico. Il parametro della stringa, denominato &quot;Ricerche valore&quot;, definisce una posizione del file (Ricerche\Valori) relativa alla directory di installazione del server workbench dati.

![](assets/cfg_Parameters_StringNumeric.png)

