---
description: I set di dati includono file per configurare il set di dati in modo flessibile.
solution: Analytics
title: Utilizzo di DataSet Include Files
topic: Data workbench
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Utilizzo di DataSet Include Files{#working-with-dataset-include-files}

I set di dati includono file per configurare il set di dati in modo flessibile.

All’interno di ciascun file, potete definire un numero illimitato di campi, trasformazioni o dimensioni e organizzare i file di inclusione in base al profilo ereditato al quale appartengono. Durante la configurazione del set di dati, è possibile modificare il set di dati includendo i file forniti con i profili interni dell&#39;applicazione Adobe o creare nuovi set di dati includere file per qualsiasi profilo ereditato creato.

Quando si modificano i parametri di un set di dati, si includono un file per un profilo interno e si salva il file aggiornato nel profilo del set di dati o in un profilo ereditato creato, in effetti si sovrascrivono le impostazioni originali del file. Adobe consiglia di modificare un file di set di dati da includere per un profilo interno ogni volta che è necessario apportare lievi modifiche al contenuto del set di dati, ad esempio modificare un parametro Condition o l&#39;impostazione predefinita di un parametro. Consulta [Modifica dei set di dati esistenti Includi file](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). Tuttavia, se si desidera specificare un nuovo campo da passare dall&#39;elaborazione del registro alla trasformazione, aggiornare o creare nuovi campi utilizzando le trasformazioni o definire dimensioni estese, è consigliabile creare un nuovo set di dati che includa un file. Consultate [Creazione di nuovi set di dati con file](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e)di inclusione. Potete modificare il file creato ogni volta che lo ritenete opportuno o comunque lo ritenete opportuno.
