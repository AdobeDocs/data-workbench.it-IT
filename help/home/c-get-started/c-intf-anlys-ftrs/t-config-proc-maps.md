---
description: Le mappe di processo possono essere configurate in modo da funzionare con qualsiasi combinazione di dimensione di base, dimensione di gruppo, dimensione di livello e metrica adatta all'applicazione e al set di dati.
solution: Analytics
title: Configurare una mappa di processo
topic: Data workbench
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurare una mappa di processo{#configure-a-process-map}

Le mappe di processo possono essere configurate in modo da funzionare con qualsiasi combinazione di dimensione di base, dimensione di gruppo, dimensione di livello e metrica adatta all&#39;applicazione e al set di dati.

Dopo aver configurato una mappa di processo, questa viene elencata con altre mappe di processo nella [!DNL Add Visualization menu].

1. In [!DNL Profile Manager], fate clic **[!UICONTROL Menu]**, fate clic **[!UICONTROL Add Visualization]**, quindi fate clic sul tipo di mappa del processo da configurare (Mappa della metrica 2D, Mappa del processo 2D o Mappa del processo 3D).

   Almeno un [!DNL *.vw] file risiede nella directory.

1. Fare clic con il pulsante destro del mouse sul segno di spunta per il file desiderato e fare clic **[!UICONTROL Make Local]**.
1. Fare clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL User] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Modificate i parametri del file utilizzando come guide il file di esempio e la tabella seguenti:

   ```
   window = simpleBorderWindow: 
     client = processMap: 
       Traffic Metric = ref: wdata/model/metric/metric name
       center = v3d: (-0.741014, 0, 0.0639476)
       color_links = bool: true
       Map = PrefixDim: 
         Name = string: Map
         Base Dimension = ref: wdata/model/dim/base dimension name
         Element Prefixes = vector: 0 items
         Element Names = vector: 0 items
       Map Level = ref: wdata/model/dim/level dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       node_label = vector<bool>: 
       node_positions = vector: 0 items
       quantify_links = int: 2
       range = double: 2.37386
       size = v3d: (430, 290, 0)
       xAxisMetric = ref: wdata/model/metric/metric name for metric map
     pos = v3d: (880, 595, 0)
     size = v3d: (430, 309, 0)
   ```

<table id="table_3F072DB1B68746C49DF9332718982EBE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questo parametro... </th> 
   <th colname="col2" class="entry"> Fornire queste informazioni... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Nome della metrica</i> </p> </td> 
   <td colname="col2"> <p>Nome della metrica il cui valore per un dato nodo è proporzionale alla dimensione del nodo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome dimensione di base</i> </p> </td> 
   <td colname="col2"> <p>Nome della dimensione i cui elementi appaiono come nodi sulla mappa di processo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome dimensione livello</i> </p> </td> 
   <td colname="col2"> <p>Il nome del livello (padre) della dimensione di base di cui trascinare gli elementi nella mappa di processo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome dimensione gruppo</i> </p> </td> 
   <td colname="col2"> <p>Nome della dimensione che determina il modo in cui gli elementi della dimensione livello vengono raggruppati per formare le connessioni tra i nodi. Una connessione tra due nodi non può estendersi su più di un elemento di una dimensione gruppo. Quando si effettua una selezione basata su un nodo all'interno di una mappa di processo, si selezionano tutti gli elementi della dimensione del gruppo che hanno interessato tale nodo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome della metrica per la mappa metrica</i> </p> </td> 
   <td colname="col2"> <p>Questo parametro si applica solo alle mappe metriche 2D. </p> <p>Nome della metrica il cui valore determina la posizione orizzontale dei nodi sulla mappa. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Per ulteriori informazioni sulla dimensione di base, la dimensione del gruppo, la dimensione del livello e la metrica per una mappa di processo, consultate [Mappe](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e)di processo.

1. In Blocco note, fare clic **[!UICONTROL File]** > **[!UICONTROL Save As]** per salvare il file con un nuovo nome basato sulla dimensione di base, ovvero Nome *dimensione di* base.vw.

   Se stai configurando una mappa metrica 2D, devi salvare il file con un nome basato sul nome della metrica per la mappa metrica, ovvero il nome della *metrica per la mappa* metrica. Accertatevi di salvare il file nella directory appropriata della mappa di processo.

   >[!NOTE]
   >
   >Per essere certi che la mappa del processo venga salvata come [!DNL *.vw] file, nella [!DNL Save As] finestra impostate Salva come tipo su Tutti i file.

1. (Facoltativo) Per rendere disponibili le modifiche a tutti gli utenti del profilo di lavoro, nel [!DNL Profile Manager]pannello fare clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL User] colonna e scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
