---
description: Metriche del profilo di valore
title: Metriche del profilo di valore
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
exl-id: 9e95008c-1162-4f50-89d2-dcf5fcf8746a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 15%

---

# Metriche del profilo di valore{#value-profile-metrics}

| Metrica | Formula | Livello | Descrizione |
|---|---|---|---|
| Conversione | `Sessions[not Session_Value=#0]/Sessions` | Sessione | La percentuale di sessioni che ha generato il valore aziendale (come definito dal modello di valore aziendale). |
| Pct del valore | `Value/total(Value)` | Sessione | Percentuale del valore complessivo generato dal set di sessioni selezionato. |
| Valore | `sum(Session_Value, Session)*0.01` | Sessione | Il valore totale dell&#39;attività generato, in dollari (come definito dal modello del valore aziendale). |
| Eventi di valore | `Sessions[not Session_Value=#0]` | Sessione | Numero di sessioni che hanno generato valore aziendale (come definito dal modello di valore aziendale). |
| Eventi di valore per visitatore | `(Value_Events/Visitors) by Visitor` | Visitatore | Il numero medio di sessioni per ogni visitatore che ha generato valore aziendale (come definito dal modello di valore aziendale). |
| Valore per visitatore | `(Value/Visitors) by Visitor` | Visitatore | Valore aziendale medio generato, in dollari, da ogni visitatore. |
