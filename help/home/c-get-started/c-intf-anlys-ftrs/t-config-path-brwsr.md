---
description: I browser percorso possono essere configurati per lavorare con qualsiasi combinazione di dimensione di base, dimensione di gruppo, dimensione di livello e metrica adatta all'applicazione e al set di dati.
solution: Analytics
title: Configurare un browser di percorsi
topic: Data workbench
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurare un browser di percorsi{#configure-a-path-browser}

I browser percorso possono essere configurati per lavorare con qualsiasi combinazione di dimensione di base, dimensione di gruppo, dimensione di livello e metrica adatta all&#39;applicazione e al set di dati.

Dopo aver configurato un browser di percorsi, questo viene elencato con altri browser di percorsi nel [!DNL Add Visualization] menu.

1. In [!DNL Profile Manager], fare clic su **[!UICONTROL Menu]**, quindi su **[!UICONTROL Add Visualization]** e **[!UICONTROL Path Browser]**.

   Almeno un [!DNL *.vw] file risiede nella directory del browser percorso.

1. Fare clic con il pulsante destro del mouse sul segno di spunta per il file desiderato e fare clic **[!UICONTROL Make Local]**.
1. Fare clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL User] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Modificate i parametri del file utilizzando come guide il file di esempio e la tabella seguenti:

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
   <th colname="col1" class="entry"> Per questo parametro... </th> 
   <th colname="col2" class="entry"> Fornire queste informazioni... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Nome dimensione di base</i> </p> </td> 
   <td colname="col2"> <p>Nome della dimensione i cui elementi vengono visualizzati nel browser percorso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome dimensione gruppo</i> </p> </td> 
   <td colname="col2"> <p>Nome della dimensione che determina il modo in cui gli elementi della dimensione livello vengono raggruppati per formare i percorsi in un browser percorso. Nello specifico, gli elementi dimensione livello associati a un singolo percorso in un browser percorso non possono estendersi su più di un elemento di una dimensione gruppo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome dimensione livello</i> </p> </td> 
   <td colname="col2"> <p>Il nome del livello (elemento padre) della dimensione di base di cui trascinate gli elementi nel browser del percorso. Seguendo un percorso da un elemento della dimensione di base a quello successivo, si passa da un elemento della dimensione di livello a quello successivo. Quando si seleziona un percorso di elementi dimensionali di base, si selezionano i dati per gli elementi corrispondenti della dimensione di livello. La selezione include sempre gli elementi della dimensione del livello che si riferiscono al livello principale, ed è ridefinita aggiungendo più elementi al percorso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome della metrica</i> </p> </td> 
   <td colname="col2"> <p>Nome della metrica il cui valore per un dato elemento è proporzionale allo spessore del percorso che porta all'elemento. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Per ulteriori informazioni sulla dimensione di base, la dimensione del gruppo, la dimensione del livello e la metrica per un browser di percorsi, vedi Browser [percorsi](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b).

1. In Blocco note, fare clic **[!UICONTROL File]** > **[!UICONTROL Save As]** per salvare il file con un nuovo nome basato sulla dimensione del gruppo, ovvero Nome *dimensione* Gruppo.vw.

   Assicurarsi di salvare il file nella directory del browser Percorso.

   >[!NOTE]
   >
   >Per essere certi che il browser dei percorsi sia salvato come [!DNL *.vw] file, nella [!DNL Save As] finestra impostate Salva come tipo su Tutti i file.

1. (Facoltativo) Per rendere disponibili le modifiche a tutti gli utenti del profilo di lavoro, nel [!DNL Profile Manager]pannello fare clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL User] colonna e scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
