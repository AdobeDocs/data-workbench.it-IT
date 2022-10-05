---
description: Il file Transformation.cfg controlla la fase di trasformazione della costruzione del set di dati durante la quale vengono applicate trasformazioni aggiuntive ai dati già elaborati durante l’elaborazione del registro per creare dimensioni estese da utilizzare nell’analisi.
title: Informazioni sul file di configurazione delle trasformazioni
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
exl-id: 860562d7-6ed3-486b-9f62-1bd06878bf7e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 5%

---

# Informazioni sul file di configurazione delle trasformazioni{#about-the-transformation-configuration-file}

{{eol}}

Il file Transformation.cfg controlla la fase di trasformazione della costruzione del set di dati durante la quale vengono applicate trasformazioni aggiuntive ai dati già elaborati durante l’elaborazione del registro per creare dimensioni estese da utilizzare nell’analisi.

È necessario modificare le [!DNL Transformation.cfg] per eseguire una delle seguenti attività di configurazione del set di dati:

* Filtrare i dati dall’elaborazione del registro definendo la [!DNL log entry condition] per la trasformazione.
* Impostazione del fuso orario da utilizzare per la creazione di dimensioni temporali e per la conversione del tempo. Vedi [Fusi orari](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] I file possono contenere istruzioni aggiuntive per la fase di trasformazione della costruzione del set di dati. Questi file esistono all&#39;interno della directory Dataset\Transformation per qualsiasi profilo ereditato e in genere definiscono parametri specifici per l&#39;applicazione (ad esempio parametri di configurazione specifici per il Web) [!DNL Site] applicazione). Per informazioni su [!DNL Transformation Dataset Include] file, vedi [Dataset Include Files (File inclusi nel set di dati)](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Per informazioni sui parametri di configurazione specifici per il Web per il sito, consulta [Impostazioni di configurazione per i dati web](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).
