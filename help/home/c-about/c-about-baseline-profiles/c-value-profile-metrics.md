---
description: 'null'
solution: Analytics
title: Metriche del profilo di valore
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: 662bf8fdff196814e5a11c1f5e1ae12d4d57e1db
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 14%

---


# Metriche del profilo di valore{#value-profile-metrics}

| Metrica | Formula | Livello | Descrizione |
|---|---|---|---|
| Conversione | `Sessions[not Session_Value=#0]/Sessions` | Sessione | La percentuale di sessioni che ha generato il valore aziendale (come definito dal modello del valore commerciale). |
| Pct of Value | `Value/total(Value)` | Sessione | Percentuale del valore globale generato dal set selezionato di sessioni. |
| Valore | `sum(Session_Value, Session)*0.01` | Sessione | Il valore totale dell&#39;attività generato, in dollari (come definito dal modello del valore commerciale). |
| Eventi valore | `Sessions[not Session_Value=#0]` | Sessione | Il numero di sessioni che hanno generato il valore aziendale (come definito dal modello di valore commerciale). |
| Eventi di valore per visitatore | `(Value_Events/Visitors) by Visitor` | Visitatore | Il numero medio di sessioni per ogni visitatore che ha generato valore aziendale (come definito dal modello di valore commerciale). |
| Valore per visitatore | `(Value/Visitors) by Visitor` | Visitatore | Il valore commerciale medio generato, in dollari, da ogni visitatore. |
