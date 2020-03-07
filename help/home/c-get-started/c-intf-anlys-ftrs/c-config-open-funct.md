---
description: La funzionalità di apertura consente di aprire elementi quali documenti o URI in applicazioni esterne quali un editor di testo o un browser Web.
solution: Analytics
title: Configurare la funzionalità di apertura
topic: Data workbench
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurare la funzionalità di apertura{#configure-open-functionality}

La funzionalità di apertura consente di aprire elementi quali documenti o URI in applicazioni esterne quali un editor di testo o un browser Web.

La funzionalità di apertura è attualmente configurata solo nell&#39; [!DNL Site] applicazione e solo per l&#39;apertura degli URI. Questa sezione fornisce informazioni sulla configurazione della funzionalità Open URI per [!DNL Site]. Per informazioni sulla configurazione della funzionalità Apri per un’altra applicazione o per aprire altri elementi, contattare i servizi di consulenza Adobe.

In [!DNL Site], potete fare clic con il pulsante destro del mouse su un URI da una sovrapposizione di pagina o da una tabella per visualizzare l’URI nell’applicazione per la quale è stato formattato. Ad esempio, da una visualizzazione tabella URI, potete fare clic su un URI per visualizzare una pagina Web in un browser Web.

Per aprire un URI da una visualizzazione, è innanzitutto necessario modificare il [!DNL Open URI.cfg] file della dimensione URI per identificare la posizione e le convenzioni di denominazione utilizzate da Workbench dati per aprire l&#39;URI. Per visualizzare un URI nel suo formato nativo (ad esempio HTML), Workbench dati deve avere accesso alla posizione di riferimento e all&#39;applicazione necessaria per aprire tale elemento. Ad esempio, per visualizzare una pagina Web, Workbench dati dovrà disporre dell&#39;accesso a Internet e disporre di un browser Web installato.

**Per modificare Open URI.vw**

1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. Nella cartella URI, fare clic con il pulsante destro del mouse sul segno di spunta accanto al [!DNL Open URI.vw]file e fare clic **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]** se il file è un [!DNL .cfg] file o **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** se è un [!DNL .vw] file.
1. Fate clic **[!UICONTROL Command]**, quindi **[!UICONTROL Parameters]** per visualizzare il contenuto del file.
1. Modificate il [!DNL Site] parametro e il parametro Template come necessario:

<table id="table_CDB316DB271F476AB9F9B557B86AFD25"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questo parametro... </th> 
   <th colname="col2" class="entry"> Fornire queste informazioni... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sito </p> </td> 
   <td colname="col2"> <p>Posizione degli URI che si desidera aprire. </p> <p>Esempio: miosito.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modello </p> </td> 
   <td colname="col2"> <p>Parametri che Workbench dati deve utilizzare per individuare e aprire gli URI. </p> <p>Esempio: <span class="filepath"> http://%Site%%URI%</span> </p> <p>Il modello predefinito mostrato nell'esempio indica a Workbench dati di aprire un browser Web, di cercare la posizione definita nel parametro <span class="wintitle"> Sito</span> e quindi di individuare l'elemento dimensione URI che si sta tentando di aprire. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Salvate il file.
1. Per rendere disponibile questa modifica a tutti gli utenti del profilo di lavoro, fare clic con il pulsante destro del mouse sul [!DNL .vw] file nella [!DNL User] colonna e scegliere **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.

