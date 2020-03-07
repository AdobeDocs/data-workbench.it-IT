---
description: Le trasformazioni consentono di estrarre le informazioni disponibili nei file di dati e di modificarle in un modulo più utile.
solution: Analytics
title: Informazioni sulle trasformazioni
topic: Data workbench
uuid: 9366f607-741d-4512-9e1b-4165f4291246
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Informazioni sulle trasformazioni{#about-transformations}

Le trasformazioni consentono di estrarre le informazioni disponibili nei file di dati e di modificarle in un modulo più utile.

Le trasformazioni funzionano sulle voci di registro (è possibile considerare le voci di registro come righe di dati) nelle origini di registro. Per ogni riga di dati, la trasformazione prende il valore del campo di input specificato, esegue una serie di fasi di elaborazione e registra il risultato nel campo di output specificato. È possibile definire le trasformazioni da eseguire durante la fase di elaborazione del registro o di trasformazione del processo di costruzione del dataset:

* **Durante l&#39;elaborazione del registro:** Le trasformazioni eseguite durante la fase di elaborazione del registro della costruzione del dataset vengono applicate a ciascun record di dati dell&#39;evento (voce di registro) per aggiornare i campi di registro esistenti o generare nuovi campi. I risultati delle trasformazioni vengono utilizzati insieme alle condizioni di immissione del registro per valutare quali voci di registro vengono filtrate dal dataset durante l&#39;elaborazione del registro.
* **Durante la trasformazione:** Le trasformazioni eseguite durante la fase di trasformazione della costruzione del set di dati operano sui campi di dati passati dall&#39;elaborazione del registro per creare dimensioni estese che è possibile utilizzare nelle analisi. Consultate Dimensioni [](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)estese.

>[!NOTE]
>
>L&#39;input di dati per la trasformazione dall&#39;elaborazione del registro è ordinato per tempo e raggruppato per l&#39;ID di tracciamento nei dati di origine. Diverse trasformazioni richiedono che i dati siano in questo modulo e funzionino solo se definiti durante la trasformazione.

Le modifiche alle trasformazioni devono essere fatte con attenzione. Le trasformazioni non influiscono sulle voci di registro che scorrono nel processo di costruzione del set di dati, ma influiscono sui risultati presentati. Ciò consente di apportare modifiche a ciò che viene analizzato senza modificare i dati su cui si basa l&#39;analisi. Tuttavia, le modifiche nelle trasformazioni possono alterare in modo sostanziale i valori prodotti nelle analisi.
