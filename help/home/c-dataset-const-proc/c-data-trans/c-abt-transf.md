---
description: Le trasformazioni consentono di estrarre le informazioni disponibili nei file di dati e di manipolarle in un modulo più utile.
title: Informazioni sulle trasformazioni
uuid: 9366f607-741d-4512-9e1b-4165f4291246
exl-id: 9bd533ef-a87e-400a-9bb0-5af1851cca0a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 1%

---

# Informazioni sulle trasformazioni{#about-transformations}

Le trasformazioni consentono di estrarre le informazioni disponibili nei file di dati e di manipolarle in un modulo più utile.

Le trasformazioni funzionano sulle voci di log (è possibile considerare le voci di log come righe di dati) nelle origini di log. Per ogni riga di dati, la trasformazione prende il valore del campo di input specificato, esegue una serie di fasi di elaborazione e registra il risultato nel campo di output specificato. Puoi definire le trasformazioni da eseguire durante la fase di elaborazione del registro o di trasformazione del processo di costruzione del set di dati:

* **Durante l’elaborazione del registro:** le trasformazioni eseguite durante la fase di elaborazione del registro della costruzione del set di dati vengono applicate a ogni record di dati dell’evento (voce di registro) per aggiornare i campi di registro esistenti o produrre nuovi campi. I risultati delle trasformazioni vengono utilizzati insieme alle condizioni di ingresso del registro per valutare quali voci di registro vengono filtrate fuori dal set di dati durante l’elaborazione del registro.
* **Durante la trasformazione:** le trasformazioni eseguite durante la fase di trasformazione della costruzione del set di dati operano sui campi dei dati trasmessi dall’elaborazione del registro per creare dimensioni estese che è possibile utilizzare nelle analisi. Vedere [Dimension estesi](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

>[!NOTE]
>
>L’input di dati per la trasformazione dall’elaborazione del registro è ordinato per tempo e raggruppato per l’ID di tracciamento nei dati di origine. Diverse trasformazioni richiedono che i dati siano in questo modulo e funzionino solo quando sono definiti in durante la trasformazione.

Le modifiche alle trasformazioni devono essere fatte con attenzione. Le trasformazioni non influiscono sulle voci di registro che scorrono nel processo di costruzione del set di dati, ma influiscono sui risultati presentati. Ciò consente di apportare modifiche a ciò che viene analizzato senza modificare i dati su cui si basa l&#39;analisi. Tuttavia, i cambiamenti nelle trasformazioni possono alterare in modo sostanziale i valori prodotti nelle analisi.
