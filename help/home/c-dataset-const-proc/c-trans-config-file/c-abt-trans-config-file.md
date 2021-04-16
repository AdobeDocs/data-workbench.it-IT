---
description: Il file Transformation.cfg controlla la fase di trasformazione della costruzione del set di dati durante la quale vengono applicate trasformazioni aggiuntive ai dati già elaborati durante l’elaborazione del registro per creare dimensioni estese da utilizzare nell’analisi.
title: Informazioni sul file di configurazione delle trasformazioni
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
exl-id: 860562d7-6ed3-486b-9f62-1bd06878bf7e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 5%

---

# Informazioni sul file di configurazione delle trasformazioni{#about-the-transformation-configuration-file}

Il file Transformation.cfg controlla la fase di trasformazione della costruzione del set di dati durante la quale vengono applicate trasformazioni aggiuntive ai dati già elaborati durante l’elaborazione del registro per creare dimensioni estese da utilizzare nell’analisi.

È necessario modificare il file [!DNL Transformation.cfg] per eseguire una delle seguenti attività di configurazione del set di dati:

* Filtrare i dati dall’elaborazione del registro definendo [!DNL log entry condition] per la trasformazione.
* Impostazione del fuso orario da utilizzare per la creazione di dimensioni temporali e per la conversione del tempo. Vedere [Fusi orari](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] I file possono contenere istruzioni aggiuntive per la fase di trasformazione della costruzione del set di dati. Questi file esistono nella directory Dataset\Transformation per qualsiasi profilo ereditato e in genere definiscono parametri specifici per l&#39;applicazione (ad esempio parametri di configurazione specifici per il Web per l&#39;applicazione [!DNL Site]). Per informazioni sui file [!DNL Transformation Dataset Include], consulta [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md) (File inclusi nel set di dati). Per informazioni sui parametri di configurazione specifici per il Web per il sito, vedere [Impostazioni di configurazione per i dati Web](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).
