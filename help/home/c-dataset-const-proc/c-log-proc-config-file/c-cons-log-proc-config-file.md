---
description: Informazioni concettuali da tenere in considerazione durante la modifica del file Log Processing.cfg.
solution: Analytics
title: Considerazioni per il file di configurazione dell'elaborazione del registro
topic: Data workbench
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Considerazioni per il file di configurazione dell&#39;elaborazione del registro{#considerations-for-the-log-processing-configuration-file}

Informazioni concettuali da tenere in considerazione durante la modifica del file Log Processing.cfg.

* I file di dati non devono essere spostati tra directory dopo che sono state definite le origini di un dataset. Gli unici file aggiuntivi che una directory dovrebbe ricevere sono quelli appena creati che derivano dal server workbench dati che riceve i dati dal Sensor(s).
* La modifica di uno qualsiasi dei parametri in questo file richiede la rielaborazione di tutti i dati. Il parametro Pausa nel [!DNL Log Processing Mode.cfg] file deve essere impostato su false per consentire la rielaborazione. Tenete presente che il valore predefinito di questo parametro è false, pertanto la modifica del parametro potrebbe non essere necessaria. Per informazioni sul [!DNL Log Processing Mode.cfg] file, consultate File [di configurazione](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)aggiuntivi.

* Se si rielaborano i dati, è possibile controllare il parametro Stato elaborazione log nel workbench dati [!DNL Processing Legend].

   Per informazioni sulla rielaborazione dei dati, vedere [Rielaborazione e trasformazione](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Vedere [Elaborazione della legenda](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* Il [!DNL Log Processing.cfg] file può essere condiviso da più profili di set di dati. Le trasformazioni definite nel [!DNL Log Processing.cfg] file vengono applicate a tutti i profili di set di dati che condividono questo file di configurazione.

   >[!NOTE]
   >
   >Adobe consiglia di definire le trasformazioni per l’elaborazione del registro in uno o più [!DNL dataset include] file di elaborazione del registro. Per ulteriori informazioni, vedere [Log Processing Dataset Include Files (Includi file](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)nei set di dati di elaborazione dei registri).

* Potete aggiungere al [!DNL Log Processing.cfg] file uno qualsiasi dei parametri precedentemente descritti aprendo e modificando il file in Blocco note. Eventuali modifiche apportate e salvate vengono visualizzate quando si riapre il file nel workbench dati. Quando si aggiunge un nuovo parametro, utilizzate il tasto Space (non il tasto Tab) per applicare un rientro di due (2) spazi a destra del livello di intestazione precedente.

   Eventuali errori che si verificano durante la fase di elaborazione del log del processo di costruzione del dataset per un profilo dataset sono visualizzati nel [!DNL Profiles] nodo dell&#39;interfaccia nel workbench dati [!DNL Detailed Status] . Per informazioni sull&#39; [!DNL Detailed Status] interfaccia, vedere la Guida *utente di Workbench* dati.

