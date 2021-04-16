---
description: La funzionalità di apertura consente di aprire elementi quali documenti o URI in applicazioni esterne quali un editor di testo o un browser Web.
title: Configurare la funzionalità di apertura
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 3%

---

# Configurare la funzionalità di apertura{#configure-open-functionality}

La funzionalità di apertura consente di aprire elementi quali documenti o URI in applicazioni esterne quali un editor di testo o un browser Web.

La funzionalità Open è attualmente configurata solo nell’applicazione [!DNL Site] e solo per l’apertura di URI. Questa sezione fornisce informazioni sulla configurazione della funzionalità Open URI per [!DNL Site]. Per informazioni sulla configurazione della funzionalità Apri per un’altra applicazione o per aprire altri elementi, contattare Adobe Consulting Services.

In [!DNL Site], è possibile fare clic con il pulsante destro del mouse su un URI da una sovrapposizione di pagina o da una tabella per visualizzare l’URI nell’applicazione per la quale è stato formattato. Ad esempio, dalla visualizzazione di una tabella URI è possibile fare clic su un URI per visualizzare una pagina Web in un browser Web.

Per aprire un URI da una visualizzazione, è innanzitutto necessario modificare il file [!DNL Open URI.cfg] della dimensione URI per identificare la posizione e le convenzioni di denominazione utilizzate dalla Data Workbench per aprire l’URI. Per visualizzare un URI nel formato nativo (ad esempio HTML), Data Workbench deve avere accesso alla posizione di riferimento e all&#39;applicazione necessaria per aprire l&#39;elemento. Ad esempio, per visualizzare una pagina web, Data Workbench dovrebbe avere accesso a Internet e disporre di un browser web installato.

**Per modificare Open URI.vw**

1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. Nella cartella URI, fare clic con il pulsante destro del mouse sul segno di spunta accanto al file [!DNL Open URI.vw]e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]** se il file è un file [!DNL .cfg] o **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** se è un file [!DNL .vw].
1. Fare clic su **[!UICONTROL Command]**, quindi **[!UICONTROL Parameters]** per visualizzare il contenuto del file.
1. Modifica il parametro [!DNL Site] e il parametro Template come necessario:

<table id="table_CDB316DB271F476AB9F9B557B86AFD25"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questo parametro.. </th> 
   <th colname="col2" class="entry"> Fornisci queste informazioni.. </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sito </p> </td> 
   <td colname="col2"> <p>Posizione degli URI che si desidera aprire. </p> <p>Esempio: miosito.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modello </p> </td> 
   <td colname="col2"> <p>Parametri che la Data Workbench deve utilizzare per individuare e aprire gli URI. </p> <p>Esempio: <span class="filepath"> http://%Site%%URI%</span> </p> <p>Il modello predefinito mostrato nell'esempio indica alla Data Workbench di aprire un browser Web, cercare la posizione definita nel parametro <span class="wintitle"> Site</span> , quindi individuare l'elemento della dimensione URI che si sta tentando di aprire. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Salvate il file.
1. Per rendere questa modifica disponibile a tutti gli utenti del profilo di lavoro, fai clic con il pulsante destro del mouse sul segno di spunta relativo al file [!DNL .vw] nella colonna [!DNL User] e fai clic su **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.
