---
description: Molti dei profili interni ricevuti con l’applicazione Adobe sono dotati di file di configurazione dei set di dati personalizzati.
title: Informazioni su Dataset Include Files (File inclusi nel set di dati)
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
exl-id: a23d3f83-4e92-4787-9f77-ee9914cb8893
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 4%

---

# Informazioni su Dataset Include Files (File inclusi nel set di dati){#about-dataset-include-files}

{{eol}}

Molti dei profili interni ricevuti con l’applicazione Adobe sono dotati di file di configurazione dei set di dati personalizzati.

Poiché i profili interni sono profili secondari del profilo di set di dati, i loro file di configurazione dei set di dati contengono regole che forniscono parametri aggiuntivi per le fasi di elaborazione del registro o di trasformazione della creazione dei set di dati. I file di configurazione del set di dati per i profili interni e per tutti i profili ereditati creati sono denominati file di set di dati includono.

Un file di inclusione di un set di dati contiene un sottoinsieme dei parametri contenuti nei file di configurazione del set di dati principale ( [!DNL Log Processing.cfg] o [!DNL Transformation.cfg]) per il profilo del set di dati. I file di Dataset include contenenti i parametri associati all’elaborazione del registro sono chiamati [!DNL Log Processing Dataset Include] file (vedere [Elaborazione del registro Dataset Include Files (File inclusi)](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)), mentre i set di dati includono i file associati alla trasformazione sono chiamati [!DNL Transformation Dataset Include] File. Vedi [File inclusi set di dati di trasformazione](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). Puoi creare più set di dati che includono file da utilizzare nel processo di creazione dei set di dati. Il set di dati completo include tutti i campi, le trasformazioni e le dimensioni estese definite in tutti i file di configurazione del set di dati per il profilo del set di dati ed eventuali profili ereditati.
