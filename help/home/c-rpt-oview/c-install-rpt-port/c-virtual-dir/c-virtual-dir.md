---
description: Per configurare il portale dei report, è necessario mappare i relativi file applicazione alle directory virtuali.
solution: Analytics
title: Mappatura delle pagine del portale di report su directory virtuali
topic: Data workbench
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mappatura delle pagine del portale di report su directory virtuali{#map-the-report-portal-pages-to-virtual-directories}

Per configurare il portale dei report, è necessario mappare i relativi file applicazione alle directory virtuali.

Una directory virtuale definisce l&#39;indirizzo che i client del browser utilizzano per individuare una risorsa fisica nel server dell&#39;applicazione IIS. Per accedere, [!DNL Report Portal]i client puntano i loro browser alla directory virtuale assegnata al portale.

Il nome della directory virtuale a cui si assegna [!DNL Report Portal] deve corrispondere al nome utilizzato per la cartella VSVirtualPortalName nel passaggio 3 della sezione precedente. Ad esempio, se desiderate utilizzare &quot;Portal&quot; come nome del vostro [!DNL Report Portal], dovete mappare i file del portale a una directory virtuale denominata &quot;Portal&quot;. L&#39;esempio seguente mostra l&#39;URI che i client utilizzerebbero per accedere a una [!DNL Report Portal] directory virtuale [!DNL VisualReportPortal] su un server denominato myWebServer:

[!DNL http://myWebServer/VisualReportPortal]

Nelle procedure seguenti viene descritto come eseguire il mapping [!DNL Report Portal] a una directory virtuale in IIS 5.0, 6.0 e 7.0 o versione successiva.

Seguire il set di procedure per la versione di IIS in uso:

* [Mappatura del portale di report su una directory virtuale (IIS 7.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [Mappatura del portale di report su una directory virtuale (IIS 5.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ [Modifica del file di configurazione della sessione](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)

