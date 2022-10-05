---
description: I file di inclusione del set di dati forniscono un modo flessibile per configurare il set di dati.
title: Utilizzo di Dataset Include Files (File inclusi nel set di dati)
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
exl-id: 94044c85-030c-4912-9546-d4a34b4115e0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 4%

---

# Utilizzo di Dataset Include Files (File inclusi nel set di dati){#working-with-dataset-include-files}

{{eol}}

I file di inclusione del set di dati forniscono un modo flessibile per configurare il set di dati.

All’interno di ciascun file, puoi definire un numero illimitato di campi, trasformazioni o dimensioni e organizzare i file di inclusione in base al profilo ereditato a cui appartengono. Durante la configurazione del set di dati, puoi modificare il set di dati e includere i file forniti con i profili interni dell’applicazione Adobe oppure creare un nuovo set di dati che includa i file per tutti i profili ereditati creati.

Quando modifichi i parametri di un set di dati, includi un file per un profilo interno e salva il file aggiornato nel profilo del set di dati o in un profilo ereditato creato, stai in effetti ignorando le impostazioni originali del file. Adobe consiglia di modificare un file di inclusione di un set di dati per un profilo interno ogni volta che è necessario apportare modifiche minori al contenuto del set di dati, ad esempio la modifica di un parametro Condition o dell’impostazione predefinita di un parametro. Vedi [Modifica di Dataset Include Files (File) esistenti](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). Tuttavia, quando si desidera specificare un nuovo campo da passare dall’elaborazione del registro alla trasformazione, aggiornare o creare nuovi campi utilizzando le trasformazioni o definire dimensioni estese, è consigliabile creare un nuovo set di dati che includa file. Vedi [Creazione di nuovi Dataset Include Files (File inclusi nel set di dati)](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e). È possibile modificare il file creato ogni volta o comunque lo si ritenga appropriato.
