---
description: Informazioni sull’installazione di un servizio dati su un server di Data Workbench.
title: Installazione di un servizio dati su un server di Data Workbench
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
exl-id: 414e93b7-4e9c-4c84-8fba-8052939240c5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 7%

---

# Installazione di un servizio dati su un server di Data Workbench{#installing-a-data-service-on-a-data-workbench-server}

Informazioni sull’installazione di un servizio dati su un server di Data Workbench.

Se utilizzi il servizio dati Geo-intelligence IP o il servizio dati di geolocalizzazione IP, devi installare il profilo [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] e i relativi file di ricerca sul server di Data Workbench. Dopo aver installato il profilo di Data Workbench [!DNL Geography] , devi completare le seguenti procedure. Consulta [Installazione della geografia di Data Workbench](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md). Se non hai installato Data Workbench, segui le istruzioni contenute nella *Data Workbench Guida utente* prima di procedere.

>[!NOTE]
>
>Per installare i file del servizio dati, è necessario disporre dell’accesso ai file sul server di Data Workbench.

Adobe distribuisce i servizi di dati di geolocalizzazione IP e i servizi di geolocalizzazione IP come file [!DNL .zip]. Ogni file [!DNL .zip] contiene due cartelle: Ricerche e profili. Per installare un servizio dati sul server di Data Workbench, è necessario eseguire i seguenti passaggi:

* Installa il profilo del servizio dati. Consulta [Installazione del profilo del servizio dati](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md).
* Installa le ricerche del servizio dati. Consulta [Installazione dei file di ricerca del servizio dati](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md).

È necessario installare il profilo del servizio dati e i file di ricerca nel computer server di Data Workbench in cui si sta elaborando ed eseguendo il profilo del set di dati. Se si esegue un cluster di server di Data Workbench, è necessario installare i file sul server master. Per informazioni sui profili dei set di dati, consulta la *Guida alla configurazione dei set di dati*.
