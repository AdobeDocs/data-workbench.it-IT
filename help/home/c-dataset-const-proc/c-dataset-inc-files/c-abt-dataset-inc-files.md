---
description: Molti dei profili interni ricevuti con l'applicazione Adobe sono dotati di file di configurazione dataset personalizzati.
solution: Analytics
title: Info sui set di dati Includi file
topic: Data workbench
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Info sui set di dati Includi file{#about-dataset-include-files}

Molti dei profili interni ricevuti con l&#39;applicazione Adobe sono dotati di file di configurazione dataset personalizzati.

Poiché i profili interni sono profili secondari del profilo di set di dati, i relativi file di configurazione dei set di dati contengono regole che forniscono parametri aggiuntivi per le fasi di elaborazione del registro o di trasformazione della creazione dei set di dati. I file di configurazione dei dataset per i profili interni e per tutti i profili ereditati creati sono denominati dataset e includono i file.

Un file di set di dati include un sottoinsieme dei parametri contenuti nei file di configurazione del dataset principale ( [!DNL Log Processing.cfg] o [!DNL Transformation.cfg]) per il profilo del dataset. I set di dati includono file contenenti parametri associati all&#39;elaborazione del registro chiamati [!DNL Log Processing Dataset Include] file (vedere [Log Processing Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)), mentre i dataset includono file associati alla trasformazione sono denominati [!DNL Transformation Dataset Include] File. Consulta [Set di dati per le trasformazioni Includi file](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). È possibile creare più set di dati con file da utilizzare nel processo di creazione dei set di dati. Il set di dati completo include tutti i campi, le trasformazioni e le dimensioni estese definiti in tutti i file di configurazione del dataset per il profilo del dataset ed eventuali profili ereditati.
