---
description: I browser del percorso possono essere configurati in modo da funzionare con qualsiasi combinazione di dimensione di base, dimensione di gruppo, dimensione di livello e metrica significativa per l’applicazione e il set di dati.
title: Configurare un browser del percorso
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
exl-id: be6a68f7-e3e3-4207-a112-3a4fdd5c5f57
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 1%

---

# Configurare un browser del percorso{#configure-a-path-browser}

I browser del percorso possono essere configurati in modo da funzionare con qualsiasi combinazione di dimensione di base, dimensione di gruppo, dimensione di livello e metrica significativa per l’applicazione e il set di dati.

Dopo aver configurato un browser del percorso, questo viene elencato con altri browser del percorso nel menu [!DNL Add Visualization] .

1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Menu]**, quindi su **[!UICONTROL Add Visualization]** e **[!UICONTROL Path Browser]**.

   Almeno un file [!DNL *.vw] risiede nella directory del browser del percorso.

1. Fai clic con il pulsante destro del mouse sul segno di spunta per il file desiderato e fai clic su **[!UICONTROL Make Local]**.
1. Fai clic con il pulsante destro del mouse sul segno di spunta del file nella colonna [!DNL User] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Modifica i parametri del file utilizzando il file di esempio e la tabella seguenti come guide:

   ```
   window = simpleBorderWindow: 
     client = pathBrowser: 
       Left Path = vector: 0 items
       Map = ref: wdata/model/dim/base dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       Map Level = ref: wdata/model/dim/level dimension name
       Metric = ref: wdata/model/metric/metric name
       Right Path = vector: 0 items
       size = v3d: (673, 279, 0)
     pos = v3d: (714, 143, 0)
     size = v3d: (673, 298, 0)
   ```

<table id="table_1DCCB4B24B554B72A781B304B5EB155E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questo parametro.. </th> 
   <th colname="col2" class="entry"> Fornisci queste informazioni.. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Nome dimensione di base</i> </p> </td> 
   <td colname="col2"> <p>Nome della dimensione i cui elementi vengono visualizzati nel browser percorsi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome dimensione gruppo</i> </p> </td> 
   <td colname="col2"> <p>Nome della dimensione che determina il modo in cui gli elementi della dimensione di livello vengono raggruppati per formare i percorsi in un browser percorsi. In particolare, gli elementi dimensionali di livello associati a un singolo percorso in un browser percorsi non possono estendersi su più di un elemento di una dimensione di gruppo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome dimensione livello</i> </p> </td> 
   <td colname="col2"> <p>Nome del livello (padre) della dimensione di base di cui trascinate gli elementi nel browser percorsi. Seguendo un percorso da un elemento dimensionale di base a quello successivo, ci si sposta da un elemento dimensionale di livello a quello successivo. Quando selezioni un percorso di elementi dimensionali di base, selezioni i dati per gli elementi corrispondenti della dimensione di livello. La selezione include sempre gli elementi della dimensione di livello che si riferiscono alla radice e viene perfezionata aggiungendo più elementi al percorso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome della metrica</i> </p> </td> 
   <td colname="col2"> <p>Nome della metrica il cui valore per un dato elemento è proporzionale allo spessore del percorso che porta a tale elemento. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Per ulteriori informazioni sulla dimensione di base, la dimensione di gruppo, la dimensione di livello e la metrica per un browser percorsi, consulta [Browser percorsi](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b).

1. Nel Blocco note, fai clic su **[!UICONTROL File]** > **[!UICONTROL Save As]** per salvare il file con un nuovo nome basato sulla dimensione del gruppo, ovvero *Nome della dimensione del gruppo*.vw.

   Assicurati di salvare il file nella directory del browser del percorso.

   >[!NOTE]
   >
   >Per assicurarti che il browser percorsi sia salvato come file [!DNL *.vw], nella finestra [!DNL Save As] imposta il tipo Salva come su Tutti i file.

1. (Facoltativo) Per rendere le modifiche disponibili a tutti gli utenti del profilo di lavoro, nella sezione [!DNL Profile Manager] fai clic con il pulsante destro del mouse sul segno di spunta del file nella colonna [!DNL User] e fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
