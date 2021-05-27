---
description: Istruzioni per ottimizzare le prestazioni DPU.
title: Impostazioni delle prestazioni DPU
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
exl-id: 738c3a76-f8b4-4d84-86ee-ce9b99f50dae
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 6%

---

# Impostazioni delle prestazioni DPU{#dpu-performance-settings}

Istruzioni per ottimizzare le prestazioni DPU.

Completa i seguenti parametri nel file * [!DNL Insight Server] installation directory*\Components\DPU.cfg .

| Parametro | Descrizione |
|---|---|
| Conteggio batch di esecuzione | Questo è un parametro di ottimizzazione. Il valore predefinito è 65536. È possibile specificare conteggi batch di esecuzione arbitrariamente piccoli. Contatta l&#39;Adobe prima di apportare modifiche a questo valore. |
| Batch di esecuzione | Questo è un parametro di ottimizzazione. Il valore predefinito è 128. Contatta l&#39;Adobe prima di apportare modifiche a questo valore. |
| Tempo di esecuzione | Questo è un parametro di ottimizzazione. Il valore predefinito è 0,100. Contatta Adobe prima di apportare eventuali modifiche a questo valore. |
| Immagine campo su errore | Questo parametro può essere impostato su true o false. Se impostato su true, [!DNL Insight Server] crea un file denominato [!DNL Field Dump number.txt] nella directory Trace ogni volta che si verificano errori nel motore di esecuzione. Il [!DNL Field Dump] &lt; [!DNL number]> [!DNL .txt] è utile per la risoluzione dei problemi. |
| Percorso profilo | Posizione in cui memorizzare i file per tutti i profili. Il percorso predefinito è Profiles\. |
| Limite di memoria query | Quantità di memoria (in byte) che [!DNL Insight Server] riserva per memorizzare i risultati delle query. Il valore predefinito è 100000000 (100 MB.) Se è necessario più spazio per i risultati della query (ad esempio, per consentire più utenti simultanei), l’impostazione può essere aumentata, ma è necessario continuare a controllare il [!DNL Insight Server’s] caricamento della memoria. |
| Percorso stato | Posizione dei file di stato del sistema. Il percorso predefinito è Stato\. |
| Thread | Un parametro di ottimizzazione delle prestazioni per i computer [!DNL Insight Server] con più processori. In generale, per qualsiasi sistema n-core, questo valore deve essere impostato su n. Il valore predefinito è 1. |
| Percorso utente | Posizione dei file degli utenti autorizzati. Il percorso predefinito è Users\. |
