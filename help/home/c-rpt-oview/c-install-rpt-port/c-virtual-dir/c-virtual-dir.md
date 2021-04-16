---
description: Per configurare Report Portal (Portale dei rapporti), è necessario mappare i relativi file di applicazione sulle directory virtuali.
title: Mappatura delle pagine del Report Portal (Portale dei rapporti) su directory virtuali
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
exl-id: 13e457d4-7039-491a-a65d-f23ad7e9fe77
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 18%

---

# Mappatura delle pagine del Report Portal (Portale dei rapporti) su directory virtuali{#map-the-report-portal-pages-to-virtual-directories}

Per configurare Report Portal (Portale dei rapporti), è necessario mappare i relativi file di applicazione sulle directory virtuali.

Una directory virtuale definisce l&#39;indirizzo utilizzato dai client del browser per individuare una risorsa fisica nel server dell&#39;applicazione IIS. Per accedere a [!DNL Report Portal], i client puntano i propri browser alla directory virtuale assegnata al portale.

Il nome della directory virtuale assegnata a [!DNL Report Portal] deve corrispondere al nome utilizzato per la cartella VSVirtualPortalName nel passaggio 3 della sezione precedente. Ad esempio, se desideri utilizzare &quot;Portal&quot; come nome del tuo [!DNL Report Portal], devi mappare i file del portale a una directory virtuale denominata &quot;Portal&quot;. L&#39;esempio seguente mostra l&#39;URI utilizzato dai client per accedere a una [!DNL Report Portal] assegnata alla directory virtuale [!DNL VisualReportPortal] su un server denominato myWebServer:

[!DNL http://myWebServer/VisualReportPortal]

Le procedure seguenti descrivono come mappare [!DNL Report Portal] a una directory virtuale in IIS 5.0, 6.0 e 7.0 o versione successiva.

Seguire il set di procedure per la versione di IIS in uso:

* [Mappatura del Report Portal (Portale dei rapporti) su una directory virtuale (IIS 7.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [Mappatura del Report Portal (Portale dei rapporti) su una directory virtuale (IIS 5.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ [Modifica del file di configurazione della sessione](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)
