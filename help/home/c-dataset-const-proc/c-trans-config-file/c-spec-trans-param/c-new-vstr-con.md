---
description: La condizione Nuovo visitatore è un’operazione condizione utilizzata con i dati del sito web per determinare quali visitatori vengono considerati per l’inclusione nel set di dati.
title: Nuova condizione del visitatore (New Visitor Condition)
uuid: e9733109-5bf3-47ce-974c-d68264291f19
exl-id: a0520edd-bde3-4f55-858c-8974d4224435
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# Nuova condizione del visitatore (New Visitor Condition){#new-visitor-condition}

La condizione Nuovo visitatore è un’operazione condizione utilizzata con i dati del sito web per determinare quali visitatori vengono considerati per l’inclusione nel set di dati.

La [!DNL New Visitor Condition] definisce la prima voce di registro (ordinata per ora) per un visitatore da utilizzare nel set di dati, e tutte le voci di registro successive per questo visitatore sono incluse nel set di dati indipendentemente dal fatto che soddisfi questa condizione. Poiché il [!DNL New Visitor Condition] richiede che i dati siano ordinati dal visitatore e dall’ora, viene applicato solo durante la fase di trasformazione della costruzione del set di dati.

La [!DNL New Visitor Condition] mostrata in questo esempio crea un set di dati che include solo le voci di registro per i visitatori che rispondono alle campagne e-mail. A questo scopo, utilizza il test [!DNL NotEmptyCondition] (vedi [Non vuoto](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) e il campo [!DNL x-campaign-email] come input per l’espressione regolare. Una volta identificati i nuovi visitatori che soddisfano la condizione, vengono acquisite tutte le voci di registro per tali visitatori.

![](assets/cfg_Transformation_NewVisitorCondition.png)
