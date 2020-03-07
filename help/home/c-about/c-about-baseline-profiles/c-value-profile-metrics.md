---
description: 'null'
solution: Analytics
title: Metriche profilo di valore
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Metriche profilo di valore{#value-profile-metrics}

| Metrica | Formula | Livello | Descrizione |
|---|---|---|---|
| Conversione | [![Sessioni DNL non valore_sessione=#0]/Sessioni] | Sessione | La percentuale di sessioni che ha generato il valore aziendale (come definito dal modello del valore commerciale). |
| Pct of Value | [!DNL Value/total(Value)] | Sessione | Percentuale del valore globale generato dal set selezionato di sessioni. |
| Valore | [!DNL sum(Session_Value, Session)*0.01] | Sessione | Il valore totale dell&#39;attività generato, in dollari (come definito dal modello del valore commerciale). |
| Eventi valore | [![Sessioni DNL non valore_sessione=#0]] | Sessione | Il numero di sessioni che hanno generato il valore aziendale (come definito dal modello di valore commerciale). |
| Eventi di valore per visitatore | [!DNL (Value_Events/Visitors) by Visitor] | Visitatore | Il numero medio di sessioni per ogni visitatore che ha generato valore aziendale (come definito dal modello di valore commerciale). |
| Valore per visitatore | [!DNL (Value/Visitors) by Visitor] | Visitatore | Il valore commerciale medio generato, in dollari, da ogni visitatore. |
