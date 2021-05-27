---
description: Informazioni concettuali da considerare durante la modifica del file Log Processing.cfg.
title: Considerazioni per il file di configurazione dell’elaborazione del registro
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
exl-id: 278a4a10-d382-4d9f-b3f4-bcc4783eb50c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# Considerazioni per il file di configurazione dell’elaborazione del registro{#considerations-for-the-log-processing-configuration-file}

Informazioni concettuali da considerare durante la modifica del file Log Processing.cfg.

* I file di dati non devono essere spostati tra le directory dopo che sono state definite le origini di un set di dati. Gli unici file aggiuntivi che una directory deve ricevere sono quelli appena creati che derivano dal server di Data Workbench che riceve i dati da Sensor(s).
* La modifica di uno qualsiasi dei parametri in questo file richiede la rielaborazione di tutti i dati. Il parametro Pause nel file [!DNL Log Processing Mode.cfg] deve essere impostato su false per consentire la rielaborazione. Tieni presente che il valore predefinito di questo parametro è false, pertanto la modifica del parametro potrebbe non essere necessaria. Per informazioni sul file [!DNL Log Processing Mode.cfg], consulta [File di configurazione aggiuntivi](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* Se rielabori i dati, puoi controllare il parametro Avanzamento elaborazione registro nel [!DNL Processing Legend] di Data Workbench.

   Per informazioni sulla rielaborazione dei dati, vedere [Rielaborazione e ritrasformazione](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Vedere [Legenda di elaborazione](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* Il file [!DNL Log Processing.cfg] può essere condiviso da più profili di set di dati. Le trasformazioni definite nel file [!DNL Log Processing.cfg] vengono applicate a tutti i profili di set di dati che condividono questo file di configurazione.

   >[!NOTE]
   >
   >L’Adobe consiglia di definire le trasformazioni per l’elaborazione del registro in uno o più file di elaborazione del registro [!DNL dataset include]. Per informazioni, consultare [Elaborazione del registro Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) (File inclusi nel set di dati di elaborazione del registro).

* È possibile aggiungere uno qualsiasi dei parametri descritti sopra al file [!DNL Log Processing.cfg] aprendo e modificando il file in Blocco note. Le modifiche apportate e salvate vengono visualizzate quando riapri il file in Data Workbench. Quando si aggiunge un nuovo parametro, utilizzare il tasto Space (non il tasto Tab) per far rientrare due (2) spazi a destra del livello di intestazione precedente.

   Eventuali errori che si verificano durante la fase di elaborazione del registro del processo di costruzione del set di dati per un profilo di set di dati vengono visualizzati nel nodo [!DNL Profiles] dell’interfaccia [!DNL Detailed Status] in Data Workbench. Per informazioni sull&#39;interfaccia [!DNL Detailed Status], vedere la *Guida utente Data Workbench*.
