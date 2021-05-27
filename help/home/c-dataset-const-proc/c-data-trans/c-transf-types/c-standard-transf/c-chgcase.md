---
description: La trasformazione ChangeCase modifica il caso della stringa nel parametro Input come specificato dal parametro Action.
title: ChangeCase
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
exl-id: 2002fe22-d31c-4286-9f73-59ef205f1384
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 6%

---

# ChangeCase{#changecase}

La trasformazione ChangeCase modifica il caso della stringa nel parametro Input come specificato dal parametro Action.

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Azione | Superiore o inferiore. Specifica se il caso deve essere modificato in superiore o inferiore. | Lower |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| Ingresso | Nome del campo dalla voce di registro da utilizzare come input. |  |
| Uscita | Nome del campo di output. |  |

In questo esempio, che utilizza i campi di dati raccolti dal traffico del sito web, la stringa all’interno del campo s-dns viene modificata in minuscolo e il nuovo valore viene restituito nel nuovo campo x-lowercase-dns.

![](assets/cfg_TransformationType_ChangeCase.png)
