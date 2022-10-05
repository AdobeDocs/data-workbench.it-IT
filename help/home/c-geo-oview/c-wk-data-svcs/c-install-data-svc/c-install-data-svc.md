---
description: Informazioni sull’installazione di un servizio dati su un server di Data Workbench.
title: Installazione di un servizio dati su un server di Data Workbench
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
exl-id: 414e93b7-4e9c-4c84-8fba-8052939240c5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 7%

---

# Installazione di un servizio dati su un server di Data Workbench{#installing-a-data-service-on-a-data-workbench-server}

{{eol}}

Informazioni sull’installazione di un servizio dati su un server di Data Workbench.

Se utilizzi il servizio dati Geo-intelligence IP o il servizio dati di geolocalizzazione IP, devi installare il [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] e i relativi file di ricerca sul server di Data Workbench. Dopo aver installato Data Workbench è necessario completare le procedure seguenti [!DNL Geography] profilo. Vedi [Installazione della geografia di Data Workbench](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md). Se non hai installato Data Workbench, segui le istruzioni contenute nella sezione *Guida utente di Data Workbench* prima di procedere.

>[!NOTE]
>
>Per installare i file del servizio dati, è necessario disporre dell’accesso ai file sul server di Data Workbench.

Adobe distribuisce i servizi di dati di geolocalizzazione IP e geolocalizzazione IP come [!DNL .zip] file. Ogni [!DNL .zip] il file contiene due cartelle: Ricerche e profili. Per installare un servizio dati sul server di Data Workbench, è necessario eseguire i seguenti passaggi:

* Installa il profilo del servizio dati. Vedi [Installazione del profilo del servizio dati](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md).
* Installa le ricerche del servizio dati. Vedi [Installazione dei file di ricerca del servizio dati](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md).

È necessario installare il profilo del servizio dati e i file di ricerca nel computer server di Data Workbench in cui si sta elaborando ed eseguendo il profilo del set di dati. Se si esegue un cluster di server di Data Workbench, è necessario installare i file sul server master. Per informazioni sui profili di set di dati, consulta la sezione *Guida alla configurazione del set di dati*.
