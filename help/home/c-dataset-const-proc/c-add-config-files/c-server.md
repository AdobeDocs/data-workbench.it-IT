---
description: Il parametro Sample Bytes nel file Server.cfg specifica la dimensione della cache dei dati (in byte) per Data Workbench.
title: Server.cfg
uuid: 7e789133-09fc-442d-b643-cca8620f4a97
exl-id: fb7667f6-4061-4bde-8a48-6489b24e0411
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 1%

---

# Server.cfg{#server-cfg}

{{eol}}

Il parametro Sample Bytes nel file Server.cfg specifica la dimensione della cache dei dati (in byte) per Data Workbench.

Il valore predefinito è 250e6. Istruzioni per l&#39;apertura e il salvataggio [!DNL Server.cfg] sono gli stessi di quelli per [!DNL Log Processing Mode.cfg]. Vedi [Elaborazione registro Mode.cfg](../../../home/c-dataset-const-proc/c-add-config-files/t-log-proc-mode.md#task-e530907cb34f488182afe625e6d9e44a).

>[!NOTE]
>
>Poiché il parametro di questo file influisce sulle prestazioni del sistema, contatta l&#39;Adobe prima di apportare eventuali modifiche.

È possibile limitare ulteriormente le dimensioni della cache dei dati per la macchina di Data Workbench che si connette al server di Data Workbench impostando il parametro Maximum Sample Size nel [!DNL Insight.cfg] file. Per ulteriori informazioni, consulta la sezione *Guida utente di Data Workbench*.
