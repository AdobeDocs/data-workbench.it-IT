---
description: Passaggi per installare i file di ricerca Geo-intelligence IP o Geolocalizzazione IP.
title: Installazione dei file di ricerca del servizio dati
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 6%

---

# Installazione dei file di ricerca del servizio dati{#installing-the-data-service-lookup-files}

Passaggi per installare i file di ricerca Geo-intelligence IP o Geolocalizzazione IP.

Il file di ricerca (Lookup\*profile name*\*data file name*) fornito con il profilo del servizio dati è un file binario ( [!DNL .bin]) che contiene dati geograficamente correlati basati sull&#39;indirizzo IP. È necessario sostituire periodicamente questo file per assicurarsi di disporre dei dati geografici più recenti. Consulta [Aggiornamento dei file del servizio dati](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c).

**Per installare i file di ricerca Geo-intelligence IP o Geolocalizzazione IP**

>[!NOTE]
>
>Tutti i file di dati [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] devono rientrare nella memoria fisica disponibile del server di Data Workbench.

1. Apri la cartella Ricerche dal file [!DNL .zip] ricevuto da Adobe.
1. Copia la cartella Geo-intelligence IP o Geo-location IP nella cartella Ricerche nella directory di installazione del server di Data Workbench (vuoi finire con un ...\Lookups\IP Geo-intelligence or a ..\Lookups\IP Geo-location folder on your data workbench server as shown in the following example. I nomi delle altre cartelle all’interno della cartella Ricerche possono essere diversi da quelli visualizzati.

   ![Informazioni sul passaggio](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >Periodicamente, Adobe invia file contenenti file di ricerca [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] aggiornati. Quando ricevi questi file, devi caricarli sul server di Data Workbench come indicato da Adobe. Per istruzioni, consulta la sezione seguente.
