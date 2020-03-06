---
description: Istruzioni per ottimizzare le prestazioni DPU.
solution: Insight
title: Impostazioni prestazioni DPU
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Impostazioni prestazioni DPU{#dpu-performance-settings}

Istruzioni per ottimizzare le prestazioni DPU.

Completare i seguenti parametri nel file * [!DNL Insight Server] install directory*\Components\DPU.cfg.

| Parametro | Descrizione |
|---|---|
| Conteggio batch di esecuzione | Questo è un parametro di ottimizzazione. Il valore predefinito è 65536. È possibile specificare conteggi batch di esecuzione arbitrariamente ridotti. Contatta Adobe prima di apportare eventuali modifiche a questo valore. |
| Batch di esecuzione | Questo è un parametro di ottimizzazione. Il valore predefinito è 128. Contatta Adobe prima di apportare eventuali modifiche a questo valore. |
| Tempo di esecuzione | Questo è un parametro di ottimizzazione. Il valore predefinito è 0,100. Contatta Adobe prima di apportare eventuali modifiche a questo valore. |
| Distanza campo in caso di errore | Questo parametro può essere impostato su true o false. Se è impostato su true, [!DNL Insight Server] crea un file denominato [!DNL Field Dump number.txt] nella directory Trace ogni volta che si verificano errori del motore di esecuzione. Il [!DNL Field Dump] &lt; [!DNL number]> [!DNL .txt] è utile per la risoluzione dei problemi. |
| Percorso profilo | Posizione in cui memorizzare i file per tutti i profili. Il percorso predefinito è Profili\. |
| Limite memoria query | Quantità di memoria (in byte) [!DNL Insight Server] riservata per memorizzare i risultati della query. Il valore predefinito è 10000000 (100 MB). Se è necessario più spazio per i risultati delle query (ad esempio, per consentire più utenti simultanei), l&#39;impostazione può essere aumentata, ma è necessario continuare a controllare il carico di [!DNL Insight Server’s] memoria. |
| Percorso stato | Posizione dei file di stato del sistema. Il percorso predefinito è Stato\. |
| Thread | Un parametro di ottimizzazione delle prestazioni per [!DNL Insight Server] computer con più processori. In generale, per qualsiasi sistema n-core, questo valore deve essere impostato su n. Il valore predefinito è 1. |
| Percorso utente | Posizione dei file degli utenti autorizzati. Il percorso predefinito è Users\. |

