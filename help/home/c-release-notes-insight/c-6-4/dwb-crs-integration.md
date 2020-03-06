---
description: La funzione di esportazione CRS (Customer Record Service) consente di esportare i dati di Workbench dati nei servizi core di Adobe Analytics per l'integrazione con altre funzionalità di Analytics, tra cui Reporting e analisi.
title: Esportazione nei servizi di base di Analytics
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Esportazione nei servizi di base di Analytics{#exporting-to-analytics-core-services}

La funzione di esportazione CRS (Customer Record Service) consente di esportare i dati di Workbench dati nei servizi core di Adobe Analytics per l&#39;integrazione con altre funzionalità di Analytics, tra cui Reporting e analisi.

>[!NOTE]
>
>Affinché la funzione di esportazione CRS funzioni correttamente, l’ID Analytics di un visitatore deve essere basato sul servizio Experience Cloud ID (ECID). Anche se ECID può essere popolato in Workbench dati per un visitatore, se il client è nel periodo di tolleranza o il cookie del visitatore non è stato sostituito con ECID, l&#39;esportazione CRS non funzionerà per quel visitatore. Per ulteriori informazioni, consulta [Identificazione dei visitatori](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html) e Periodo [di tolleranza per il servizio](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/grace-period.html)ID.

Da una tabella **** dei dettagli (clic con il pulsante destro del mouse **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]** in un&#39;area di lavoro), potete impostare i valori degli attributi e le variabili necessarie per l&#39;integrazione con Reporting e analisi di Analytics (tramite Adobe Pipeline Services).

1. **Fare clic con il pulsante destro del mouse sull&#39;intestazione della tabella e scegliere Nuovo servizio Record cliente.**

   ![](assets/6_4_CRS.png)

1. **Denominate il file di esportazione e salvate.**

   Viene aperta la finestra di modifica del file di esportazione.

1. **Aprite** **Query > Configurazione** CRS.
1. **Fare clic con il pulsante destro del mouse su Attributi CRS > Aggiungi nuovo.**
1. **Immettere** ***i parametri*** degli attributi **** CRS.

   Aprite la nuova voce e immettete o verificate i valori nella sezione Attributi ** CRS del file di esportazione:

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>Nome attributo</b> </p> </td> 
      <td colname="col2">Nome della variabile Attributi <i></i> cliente visualizzata in <i>Reporting e analisi</i>. </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>Tipo attributo</b> </td> 
      <td colname="col2"> <p>Questo parametro accetta i valori di (<i>int</i>, <i>stringa</i>). </p> <p>Nota: Se un attributo <b>non</b> è sottoscritto in Analytics: <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">L'attributo verrà creato con qualsiasi tipo di attributo valido supportato da Analytics (per questa versione è limitato solo a <i>stringa</i> e <i>int</i>). </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">Se viene immesso un tipo di attributo non valido, verrà visualizzato un errore che indica che non è possibile effettuare la sottoscrizione ad Analytics. </li> 
      </ul> </p> <p>Se un attributo è <b>già</b> sottoscritto in Analytics: </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">Assicuratevi di immettere il tipo di attributo corretto per l'attributo già sottoscritto. </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">Se immetti il tipo errato per l'attributo, il suo comportamento dipenderà dalla gestione dei tipi di attributo da parte di Analytics. </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>Nome campo</b> </p> </td> 
      <td colname="col2">Nome della dimensione o della metrica da cui sono selezionati i valori degli attributi. <p>Nota: Il nome <i><b>del</b></i> campo in Attributi <i></i> CRS deve essere uguale a quello dei campi <b><i>di</i> output &gt; Nome <i></i></b> campo (popolato automaticamente in base all'attributo selezionato). Se Nome <i></i> campo non è valido, l'esportazione non verrà eseguita. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Right-click **[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**.
1. Inserire il **[!UICONTROL Report Suite ID]**.

   Aprite la nuova voce e immettete o verificate i valori nella sezione Suite *di* rapporti del file di esportazione:

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>Suite di rapporti</b> </td> 
      <td colname="col2">ID della suite di rapporti in <i>Reporting e analisi</i> che identifica le variabili Attributo <i></i> cliente da esportare. <p> <p>Nota: Sebbene <i>Reporting e analisi</i> consenta di aggiungere più suite di rapporti, Workbench dati 6.4 esporterà solo una singola suite di rapporti identificata in corrispondenza dell' <i>indice 0</i>. <p>Il valore della suite di rapporti immesso in questo campo è l'ID della suite di rapporti (e non il nome della suite di rapporti). </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Immettete il parametro del campo ECID.

   **Campo** ECID: Nome della dimensione nel profilo che rappresenta Adobe Experience Cloud ID. Questo campo è obbligatorio e qualsiasi valore di dimensione non valido immesso non verrà esportato.

1. (facoltativo) Completate il parametro Visitor ID Field.

   **Campo** ID visitatore: Se l&#39;utente desidera inviare un altro ID personalizzato per un visitatore nei propri dati, questo è il punto in cui immette il nome della dimensione che rappresenta l&#39;ID visitatore personalizzato. Questo campo è facoltativo e può essere lasciato vuoto.
