---
description: Passaggi per installare i file di ricerca Geo-intelligence IP o Geolocalizzazione IP.
title: Installazione dei file di ricerca del servizio dati
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 6%

---

# Installazione dei file di ricerca del servizio dati{#installing-the-data-service-lookup-files}

{{eol}}

Passaggi per installare i file di ricerca Geo-intelligence IP o Geolocalizzazione IP.

Il file di ricerca (Lookup\*profile name*\*data file name*) fornito con il profilo del servizio dati è un file binario ( [!DNL .bin]) che contiene dati geograficamente correlati basati sull’indirizzo IP. È necessario sostituire periodicamente questo file per assicurarsi di disporre dei dati geografici più recenti. Vedi [Aggiornamento dei file del servizio dati](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c).

**Per installare i file di ricerca Geo-intelligence IP o Geolocalizzazione IP**

>[!NOTE]
>
>Tutte le tue [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] i file di dati devono adattarsi alla memoria fisica disponibile del server di Data Workbench.

1. Apri la cartella Ricerche dal [!DNL .zip] file ricevuto da Adobe.
1. Copia la cartella Geo-intelligence IP o Geo-location IP nella cartella Ricerche nella directory di installazione del server di Data Workbench (vuoi finire con un ...\Ricerche\IP Geo-intelligence o ...\Searchups\IP Geo-location folder sul server di Data Workbench, come illustrato nell’esempio seguente. I nomi delle altre cartelle all’interno della cartella Ricerche possono essere diversi da quelli visualizzati.

   ![Informazioni sul passaggio](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >Periodicamente, Adobe invia i file contenenti aggiornato [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] file di ricerca. Quando ricevi questi file, devi caricarli sul server di Data Workbench come indicato da Adobe. Per istruzioni, consulta la sezione seguente.
