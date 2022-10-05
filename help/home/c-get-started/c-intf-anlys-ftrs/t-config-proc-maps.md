---
description: Le mappe dei processi possono essere configurate in modo da funzionare con qualsiasi combinazione di dimensioni di base, dimensioni di gruppo, dimensione di livello e metrica significativa per l’applicazione e il set di dati.
title: Configurare una mappa del processo
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
exl-id: 0b37e942-4596-45cc-bc31-db147626f4eb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 1%

---

# Configurare una mappa del processo{#configure-a-process-map}

{{eol}}

Le mappe dei processi possono essere configurate in modo da funzionare con qualsiasi combinazione di dimensioni di base, dimensioni di gruppo, dimensione di livello e metrica significativa per l’applicazione e il set di dati.

Dopo aver configurato una mappa del processo, questa viene elencata con altre mappe del processo nel [!DNL Add Visualization menu].

1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Menu]**, fai clic su **[!UICONTROL Add Visualization]**, quindi fai clic sul tipo di mappa del processo da configurare (Mappa della metrica 2D, Mappa del processo 2D o Mappa del processo 3D).

   Almeno uno [!DNL *.vw] il file si trova nella directory.

1. Fai clic con il pulsante destro del mouse sul segno di spunta per il file desiderato e fai clic su **[!UICONTROL Make Local]**.
1. Fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL User] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Modifica i parametri del file utilizzando il file di esempio e la tabella seguenti come guide:

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
   <th colname="col1" class="entry"> Per questo parametro.. </th> 
   <th colname="col2" class="entry"> Fornisci queste informazioni.. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Nome della metrica</i> </p> </td> 
   <td colname="col2"> <p>Nome della metrica il cui valore per un dato nodo è proporzionale alla dimensione del nodo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome dimensione di base</i> </p> </td> 
   <td colname="col2"> <p>Nome della dimensione i cui elementi vengono visualizzati come nodi nella mappa del processo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome dimensione livello</i> </p> </td> 
   <td colname="col2"> <p>Nome del livello (padre) della dimensione di base di cui si trascinano gli elementi nella mappa del processo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome dimensione gruppo</i> </p> </td> 
   <td colname="col2"> <p>Nome della dimensione che determina il modo in cui gli elementi della dimensione di livello vengono raggruppati per formare le connessioni tra nodi. Una connessione tra due nodi non può estendersi su più di un elemento di una dimensione di gruppo. Quando effettui una selezione basata su un nodo all’interno di una mappa del processo, stai selezionando tutti gli elementi della dimensione del gruppo che coinvolgono quel nodo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome della metrica per la mappa metrica</i> </p> </td> 
   <td colname="col2"> <p>Questo parametro si applica solo alle mappe metriche 2D. </p> <p>Nome della metrica il cui valore determina la posizione orizzontale dei nodi sulla mappa. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Per ulteriori informazioni sulla dimensione di base, la dimensione di gruppo, la dimensione di livello e la metrica per una mappa del processo, consulta [Mappe del processo](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

1. In Blocco note, fai clic su **[!UICONTROL File]** > **[!UICONTROL Save As]** per salvare il file con un nuovo nome basato sulla dimensione di base, ovvero: *Nome dimensione di base* vw.

   (Se stai configurando una mappa metrica 2D, devi salvare il file con un nome basato sul nome della metrica per la mappa metrica, ovvero: *Nome della metrica per la mappa metrica*.vw.) Assicurati di salvare il file nella directory di mappa del processo appropriata.

   >[!NOTE]
   >
   >Per assicurarti che la mappa del processo sia salvata come [!DNL *.vw] nel [!DNL Save As] impostare il tipo Salva con nome su Tutti i file.

1. (Facoltativo) Per rendere le modifiche disponibili a tutti gli utenti del profilo di lavoro, nella [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL User] e fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
