---
description: I parametri stringa e numerici assumono rispettivamente come valori stringa e numeri.
title: Parametri stringa e numerici
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
exl-id: 37d004da-cde7-4b67-b0cb-0acbb6d8ad68
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 5%

---

# Parametri stringa e numerici{#string-and-numeric-parameters}

{{eol}}

I parametri stringa e numerici assumono rispettivamente come valori stringa e numeri.

È possibile utilizzarli in modo intercambiabile, ma i parametri numerici devono essere definiti in modo da avere un valore numerico. È possibile fare riferimento a parametri numerici e di stringa durante la definizione di trasformazioni, condizioni e dimensioni estese e fare riferimento a più di un parametro nella stessa riga.

Non è possibile fare riferimento a parametri stringa e numerici in [!DNL Input] o [!DNL Output] ma puoi utilizzare un parametro di stringa per definire un campo di input costante. Inoltre, non è possibile fare riferimento a parametri stringa e numerici nei decoder o nei gruppi decoder.

Questo esempio mostra un [!DNL Log Processing Dataset Include] file che definisce un parametro stringa e un parametro numerico. Il parametro della stringa, denominato &quot;Ricerche di valore&quot;, definisce una posizione del file (Ricerche\Valori) relativa alla directory di installazione del server di Data Workbench.

![](assets/cfg_Parameters_StringNumeric.png)
