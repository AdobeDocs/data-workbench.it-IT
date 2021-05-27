---
description: Se ti abboni a uno dei due servizi dati, devi aggiornare periodicamente i file del servizio dati forniti da Adobe.
title: Aggiornamento dei file del servizio dati
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 1%

---

# Aggiornamento dei file del servizio dati{#updating-data-service-files}

Se ti abboni a uno dei due servizi dati, devi aggiornare periodicamente i file del servizio dati forniti da Adobe.

A questo scopo, devi disporre dell’accesso ai file sul server di Data Workbench.

Per caricare i file di dati [!DNL IP Geo-location] o [!DNL IP Geo-intelligence], è necessario completare le procedure seguenti.

## Sostituzione del file di dati {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. All’interno di Data Workbench, nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fai clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l’area di lavoro [!DNL Servers Manager].

1. Nella finestra [!DNL Servers Manager] fare clic con il pulsante destro del mouse sull’icona del server di Data Workbench in cui si desidera caricare i file e fare clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse nella colonna **[!UICONTROL Temp]** per **[!UICONTROL Lookups\IP Geo-location]** o **[!UICONTROL Lookups\IP Geo-intelligence]** e fai clic su **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]***.

1. Copia il file di dati [!DNL .bin] fornito dall&#39;Adobe nella finestra della cartella Ricerche\Geolocalizzazione IP o Ricerche\IP Geo-intelligence.
1. Salva il file nel server di Data Workbench facendo clic con il pulsante destro del mouse sulla colonna [!DNL Temp] relativa al file di dati e facendo clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   Se esegui un cluster, carica i file nel server di Data Workbench principale nel cluster.

## Aggiornamento della trasformazione IPLookup {#section-a8b99afe3eb04afabe88e15bd465f935}

1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** e **[!UICONTROL Geography]**.

1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL IP Lookup.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].

1. Fai clic con il pulsante destro del mouse sul nuovo segno di spunta e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene visualizzata una finestra di configurazione della trasformazione.

1. Nella finestra, fai clic su **[!UICONTROL Transformation]**, quindi su **[!UICONTROL Transformations]**.

1. Individua e fai clic su **[!UICONTROL IPLookup Quova]** o **[!UICONTROL IPLookup Digital Envoy]**.

1. Per il parametro File , aggiorna il nome del file in modo che corrisponda al nome del nuovo file di dati ( [!DNL .bin]) fornito da Adobe.
1. Salva il file di configurazione della trasformazione facendo clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra di configurazione e facendo clic su **[!UICONTROL Save]**.

1. Salva il file di configurazione modificato in ciascun profilo che utilizza il servizio dati facendo clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL IP Lookup.cfg] nella colonna [!DNL User] e facendo clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. La riconversione dei dati inizia dopo la sincronizzazione del profilo del set di dati.

   Per informazioni sulla riconversione del set di dati, consulta il capitolo Rielaborazione e ritrasformazione della *Guida alla configurazione del set di dati*.

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe (incluso il profilo [!DNL IP Geo-location] o [!DNL IP Geo-intelligence]), in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.

Se hai installato il servizio dati [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] per la versione 5.1 o successiva, hai completato l’aggiornamento del servizio dati. Tuttavia, se hai installato il servizio dati [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] prima della versione 5.1, devi completare le seguenti procedure aggiuntive.

## Sostituzione del file di ricerca {#section-ced1efa38a76419d812edd35423dbff7}

Devi completare i seguenti passaggi solo se hai installato il servizio dati [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] prima della versione 5.1.

1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** o **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**, quindi fai clic su **[!UICONTROL Maps]** per visualizzarne il contenuto.

1. Fai clic con il pulsante destro del mouse nella colonna **[!UICONTROL Temp]** per **[!UICONTROL Maps]** e fai clic su **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copia il nuovo file [!DNL .txt] fornito da Adobe nella finestra della cartella Maps.
1. Salva il file nel server di Data Workbench facendo clic con il pulsante destro del mouse sul segno di spunta nella colonna [!DNL Temp] del file [!DNL .txt] e facendo clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

>[!NOTE]
>
>Se esegui un cluster, carica i file nel server di Data Workbench principale nel cluster.

## Aggiornamento dei file di livello {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Devi completare i seguenti passaggi solo se hai installato il servizio dati [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] prima della versione 5.1.

Completa questi passaggi per ogni file di livello ( [!DNL .layer]) che fa riferimento al file di ricerca [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] ( [!DNL .txt]).

1. Nella cartella Profiles\*data service name*\Maps all’interno della directory di installazione del server di Data Workbench, apri il file [!DNL .layer] in un editor di testo come Blocco note.

1. Nel vettore [!DNL Data Paths] , aggiorna il nome del file di ricerca [!DNL .txt] in modo che corrisponda al nome del nuovo file [!DNL .txt] fornito dall’Adobe, come mostrato nell’esempio di file seguente:

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
1. Ripetere i passaggi 2 e 3 per ogni file [!DNL .layer] che fa riferimento al file [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] [!DNL .txt].
