---
description: Se ti iscrivi a uno dei due servizi dati, devi aggiornare periodicamente i file dei servizi dati forniti da Adobe.
solution: Analytics
title: Aggiornamento dei file del servizio dati
topic: Data workbench
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aggiornamento dei file del servizio dati{#updating-data-service-files}

Se ti iscrivi a uno dei due servizi dati, devi aggiornare periodicamente i file dei servizi dati forniti da Adobe.

A tal fine, è necessario avere accesso ai file sul server workbench dati.

Per caricare [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] caricare i file di dati, è necessario completare le seguenti procedure.

## Sostituzione del file di dati {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. Nel workbench dati, nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39; [!DNL Servers Manager] area di lavoro.

1. All&#39;interno della [!DNL Servers Manager] finestra, fare clic con il pulsante destro del mouse sull&#39;icona del server workbench dati sul quale si desidera caricare i file e fare clic **[!UICONTROL Server Files]**.

1. Fare clic con il pulsante destro del [!DNL Server Files Manager]mouse nella **[!UICONTROL Temp]** colonna per **[!UICONTROL Lookups\IP Geo-location]** oppure **[!UICONTROL Lookups\IP Geo-intelligence]** quindi scegliere **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copiate il file di [!DNL .bin] dati fornito da Adobe nella finestra delle cartelle Ricerche\Geolocalità IP o Ricerche\IP Geo-intelligence.
1. Salvare il file sul computer del server del workbench dati facendo clic con il pulsante destro del mouse sulla [!DNL Temp] colonna del file di dati e scegliendo **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   Se si sta eseguendo un cluster, caricare i file nel server workbench dati master del cluster.

## Aggiornamento della trasformazione IPLookup {#section-a8b99afe3eb04afabe88e15bd465f935}

1. In the [!DNL Profile Manager], click **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]**, and **[!UICONTROL Geography]**.

1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL IP Lookup.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.

1. Fare clic con il pulsante destro del mouse sul nuovo segno di spunta e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene visualizzata una finestra di configurazione della trasformazione.

1. Nella finestra, fare clic **[!UICONTROL Transformation]**, quindi fare clic su **[!UICONTROL Transformations]**.

1. Individuate e fate clic su **[!UICONTROL IPLookup Quova]** o **[!UICONTROL IPLookup Digital Envoy]**.

1. Per il parametro File, aggiornate il nome del file in modo che corrisponda al nome del nuovo file di dati ( [!DNL .bin]) fornito da Adobe.
1. Salvate il file di configurazione della trasformazione facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra di configurazione e facendo clic su **[!UICONTROL Save]**.

1. Salva il file di configurazione modificato in ciascun profilo che utilizza il servizio dati facendo clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL IP Lookup.cfg] nella [!DNL User] colonna e facendo clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. Il ripristino dei dati inizia dopo la sincronizzazione del profilo del set di dati.

   Per informazioni sulla riconversione del set di dati, consultare il capitolo Rielaborazione e trasformazione della Guida alla configurazione del set di *dati*.

   >[!NOTE]
   >
   >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe (incluso il [!DNL IP Geo-location] profilo o il [!DNL IP Geo-intelligence] profilo), in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti a tali profili.

Se hai installato il servizio [!DNL IP Geo-intelligence] dati e il servizio [!DNL IP Geo-location] dati per la versione 5.1 o successiva, hai completato l&#39;aggiornamento del servizio dati. Tuttavia, se avete installato il servizio [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] i dati prima della versione 5.1, dovete completare le seguenti procedure aggiuntive.

## Sostituzione del file di ricerca {#section-ced1efa38a76419d812edd35423dbff7}

Completare i seguenti passaggi solo se hai installato il servizio [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] dati prima della versione 5.1.

1. In [!DNL Server Files Manager], fate clic su **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** o **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**, quindi fate clic **[!UICONTROL Maps]** per visualizzarne il contenuto.

1. Fare clic con il pulsante destro del mouse nella **[!UICONTROL Temp]** colonna per **[!UICONTROL Maps]** e scegliere **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copiate il nuovo [!DNL .txt] file fornito da Adobe nella finestra della cartella Mappe.
1. Salvare il file sul computer del server workbench dati facendo clic con il pulsante destro del mouse sul segno di spunta nella [!DNL Temp] colonna del [!DNL .txt] file e facendo clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Se si sta eseguendo un cluster, caricare i file nel server workbench dati master del cluster.

## Aggiornamento dei file di livello {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Completare i seguenti passaggi solo se hai installato il servizio [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] dati prima della versione 5.1.

Completate questi passaggi per ogni file di livello ( [!DNL .layer]) che fa riferimento al file [!DNL IP Geo-intelligence] o di [!DNL IP Geo-location] ricerca ( [!DNL .txt]).

1. Nella cartella Profili\*nome servizio dati*\Mappe all&#39;interno della directory di installazione del server workbench dati, aprire il [!DNL .layer] file in un editor di testo come Blocco note.

1. Nel [!DNL Data Paths] vettore, aggiornate il nome del file di [!DNL .txt] ricerca in modo che corrisponda al nome del nuovo [!DNL .txt] file fornito da Adobe, come evidenziato nel seguente esempio di file:

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

1. Salvate il file di livello aggiornato.
1. Ripetere i passaggi 2 e 3 per ogni [!DNL .layer] file che fa riferimento al [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] al [!DNL .txt] file.

