---
description: Il file Transformation.cfg controlla la fase di trasformazione della costruzione del set di dati durante la quale vengono applicate trasformazioni aggiuntive ai dati già elaborati durante l'elaborazione del registro per creare dimensioni estese da utilizzare nell'analisi.
solution: Analytics
title: Informazioni sul file di configurazione delle trasformazioni
topic: Data workbench
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Informazioni sul file di configurazione delle trasformazioni{#about-the-transformation-configuration-file}

Il file Transformation.cfg controlla la fase di trasformazione della costruzione del set di dati durante la quale vengono applicate trasformazioni aggiuntive ai dati già elaborati durante l&#39;elaborazione del registro per creare dimensioni estese da utilizzare nell&#39;analisi.

È necessario modificare il [!DNL Transformation.cfg] file per eseguire una delle seguenti attività di configurazione del dataset:

* Filtrare i dati dall’elaborazione del registro definendo la [!DNL log entry condition] trasformazione.
* Impostazione del fuso orario da utilizzare per creare dimensioni temporali e realizzare conversioni temporali. Consultate Fusi [temporali](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] i file possono contenere istruzioni aggiuntive per la fase di trasformazione della costruzione del dataset. Questi file esistono nella directory Dataset\Transformation per qualsiasi profilo ereditato e in genere definiscono parametri specifici dell&#39;applicazione (come i parametri di configurazione specifici per il Web dell&#39; [!DNL Site] applicazione). Per informazioni sui [!DNL Transformation Dataset Include] file, vedere [Set di dati Includi file](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Per informazioni sui parametri di configurazione specifici per il Web per il sito, vedere Impostazioni [di configurazione per i dati](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)Web.

