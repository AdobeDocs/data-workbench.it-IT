---
description: La nuova condizione del visitatore è un'operazione di condizione utilizzata con i dati del sito Web per determinare quali visitatori vengono considerati per l'inclusione nel set di dati.
solution: Analytics
title: Nuova condizione del visitatore
topic: Data workbench
uuid: e9733109-5bf3-47ce-974c-d68264291f19
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Nuova condizione del visitatore{#new-visitor-condition}

La nuova condizione del visitatore è un&#39;operazione di condizione utilizzata con i dati del sito Web per determinare quali visitatori vengono considerati per l&#39;inclusione nel set di dati.

Definisce [!DNL New Visitor Condition] la prima voce di registro (ordinata per ora) per un visitatore da utilizzare nel set di dati, e tutte le voci di registro successive per questo visitatore sono incluse nel set di dati, a prescindere dal fatto che soddisfi o meno questa condizione. Poiché [!DNL New Visitor Condition] richiede che i dati siano ordinati dal visitatore e dall&#39;ora, vengono applicati solo durante la fase di trasformazione della costruzione del set di dati.

L&#39; [!DNL New Visitor Condition] esempio seguente crea un set di dati che include solo le voci di registro per i visitatori che rispondono alle campagne e-mail. Questo risultato viene ottenuto utilizzando il [!DNL NotEmptyCondition] test (vedere [Non vuoto](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) e il [!DNL x-campaign-email] campo come input per l&#39;espressione regolare. Una volta identificati i nuovi visitatori che soddisfano la condizione, vengono acquisite tutte le voci di registro relative a tali visitatori.

![](assets/cfg_Transformation_NewVisitorCondition.png)

