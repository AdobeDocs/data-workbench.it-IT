---
description: I parametri stringa e numerici assumono rispettivamente come valori stringa e numeri.
title: Parametri stringa e numerici
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
exl-id: 37d004da-cde7-4b67-b0cb-0acbb6d8ad68
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 5%

---

# Parametri stringa e numerici{#string-and-numeric-parameters}

I parametri stringa e numerici assumono rispettivamente come valori stringa e numeri.

È possibile utilizzarli in modo intercambiabile, ma i parametri numerici devono essere definiti in modo da avere un valore numerico. È possibile fare riferimento a parametri numerici e di stringa durante la definizione di trasformazioni, condizioni e dimensioni estese e fare riferimento a più di un parametro nella stessa riga.

Non è possibile fare riferimento a parametri stringa e numerici nei campi [!DNL Input] o [!DNL Output], ma è possibile utilizzare un parametro stringa per definire un campo di input costante. Inoltre, non è possibile fare riferimento a parametri stringa e numerici nei decoder o nei gruppi decoder.

Questo esempio mostra un file [!DNL Log Processing Dataset Include] che definisce un parametro stringa e un parametro numerico. Il parametro della stringa, denominato &quot;Ricerche di valore&quot;, definisce una posizione del file (Ricerche\Valori) relativa alla directory di installazione del server di Data Workbench.

![](assets/cfg_Parameters_StringNumeric.png)
