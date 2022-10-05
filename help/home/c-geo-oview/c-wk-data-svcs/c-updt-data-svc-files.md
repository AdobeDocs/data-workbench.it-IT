---
description: Se ti abboni a uno dei due servizi dati, devi aggiornare periodicamente i file del servizio dati forniti da Adobe.
title: Aggiornamento dei file del servizio dati
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 1%

---

# Aggiornamento dei file del servizio dati{#updating-data-service-files}

{{eol}}

Se ti abboni a uno dei due servizi dati, devi aggiornare periodicamente i file del servizio dati forniti da Adobe.

A questo scopo, devi disporre dell’accesso ai file sul server di Data Workbench.

Per caricare [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] file di dati, è necessario completare le procedure seguenti.

## Sostituzione del file di dati {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. All’interno di Data Workbench, [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire la miniatura [!DNL Servers Manager] workspace.

1. All&#39;interno di [!DNL Servers Manager] fare clic con il pulsante destro del mouse sull’icona del server di Data Workbench in cui si desidera caricare i file e fare clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse in **[!UICONTROL Temp]** colonna per **[!UICONTROL Lookups\IP Geo-location]** o **[!UICONTROL Lookups\IP Geo-intelligence]** e fai clic su **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copia il [!DNL .bin] file di dati fornito dall&#39;Adobe alla finestra della cartella Ricerche\Geolocalizzazione IP o Ricerche\IP Geo-intelligence.
1. Salva il file nel server di Data Workbench facendo clic con il pulsante destro del mouse sul pulsante [!DNL Temp] per il file di dati e facendo clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   Se esegui un cluster, carica i file nel server di Data Workbench principale nel cluster.

## Aggiornamento della trasformazione IPLookup {#section-a8b99afe3eb04afabe88e15bd465f935}

1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** e **[!UICONTROL Geography]**.

1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL IP Lookup.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nel [!DNL User] colonna.

1. Fai clic con il pulsante destro del mouse sul nuovo segno di spunta e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene visualizzata una finestra di configurazione della trasformazione.

1. Nella finestra, fai clic su **[!UICONTROL Transformation]**, quindi fai clic su **[!UICONTROL Transformations]**.

1. Individua e fai clic su **[!UICONTROL IPLookup Quova]** o **[!UICONTROL IPLookup Digital Envoy]**.

1. Per il parametro File , aggiorna il nome del file in modo che corrisponda al nome dei nuovi dati ( [!DNL .bin]) fornito da Adobe.
1. Salva il file di configurazione della trasformazione facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra di configurazione e facendo clic su **[!UICONTROL Save]**.

1. Salva il file di configurazione modificato in ogni profilo che utilizza il servizio dati facendo clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL IP Lookup.cfg] in [!DNL User] colonna e clic **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. La riconversione dei dati inizia dopo la sincronizzazione del profilo del set di dati.

   Per informazioni sulla trasformazione del set di dati, consulta il capitolo Rielaborazione e ritrasformazione del *Guida alla configurazione del set di dati*.

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe (tra cui [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] (profilo), in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a questi profili.

Se hai installato [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] servizio dati per versione 5.1 o successiva, hai completato l’aggiornamento del servizio dati. Tuttavia, se hai installato il [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] servizio dati precedente alla versione 5.1, è necessario completare le seguenti procedure aggiuntive.

## Sostituzione del file di ricerca {#section-ced1efa38a76419d812edd35423dbff7}

Devi completare i seguenti passaggi solo se hai installato il [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] servizio dati precedente alla versione 5.1.

1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** o **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**, quindi fai clic su **[!UICONTROL Maps]** per visualizzarne il contenuto.

1. Fai clic con il pulsante destro del mouse nel **[!UICONTROL Temp]** colonna per **[!UICONTROL Maps]** e fai clic su **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copia il nuovo [!DNL .txt] file fornito da Adobe nella finestra della cartella Maps.
1. Salva il file nel computer server di Data Workbench facendo clic con il pulsante destro del mouse sul segno di spunta nel [!DNL Temp] per [!DNL .txt] file e clic **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Se esegui un cluster, carica i file nel server di Data Workbench principale nel cluster.

## Aggiornamento dei file di livello {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Devi completare i seguenti passaggi solo se hai installato il [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] servizio dati precedente alla versione 5.1.

Completa questi passaggi per ogni livello ( [!DNL .layer]) che fa riferimento al [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] lookup ( [!DNL .txt]).

1. Nella cartella Profiles\*data service name*\Maps all’interno della directory di installazione del server di Data Workbench, apri la [!DNL .layer] in un editor di testo come Blocco note.

1. In [!DNL Data Paths] vettore, aggiorna il nome del [!DNL .txt] file di ricerca che corrisponde al nome del nuovo [!DNL .txt] file fornito dall’Adobe, come mostrato nell’esempio di file seguente:

   ```
   Layer = ElementPointLayer:
     Data Paths = vector: 1 items
       0 = Path: Maps\\LookupFileName.txt
     Longitude Column = string: LongitudeColumnName
     Latitude Column = string: LatitudeColumnName
     Name Column = string: LocationColumnName
     Key Column = string: KeyColumnName
     Dimension = ref: wdata/model/dim/DimensionName
     Metric = ref: wdata/model/metric/MetricName
   ```

1. Salva il file di livello aggiornato.
1. Ripeti i passaggi 2 e 3 per ogni [!DNL .layer] file che fa riferimento a [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] [!DNL .txt] file.
