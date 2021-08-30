---
description: La funzione di esportazione CRS (Customer Record Service) consente di esportare i dati di Data Workbench nei servizi core Adobe Analytics per l’integrazione con altre funzionalità di Analytics, inclusa Reports & Analytics.
title: Esportazione nei servizi core di Analytics
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
exl-id: 573085e8-2260-4872-be90-a84ad61145bb
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 2%

---

# Esportazione nei servizi core di Analytics{#exporting-to-analytics-core-services}

La funzione di esportazione CRS (Customer Record Service) consente di esportare i dati di Data Workbench nei servizi core Adobe Analytics per l’integrazione con altre funzionalità di Analytics, inclusa Reports &amp; Analytics.

>[!NOTE]
>
>Affinché la funzione di esportazione CRS funzioni, l’ID di Analytics di un visitatore deve essere basato sul servizio Experience Cloud ID (ECID). Anche se ECID può essere popolato in Data Workbench per un visitatore, se il cliente è nel periodo di tolleranza o se il cookie del visitatore non è stato sostituito con ECID, l&#39;esportazione CRS non funzionerà per quel visitatore. Per ulteriori informazioni, consulta [Identificazione dei visitatori](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html) e [Periodo di tolleranza per il servizio ID](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html).

Da una **Tabella dettagli** (fai clic con il pulsante destro del mouse **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]** in un’area di lavoro), puoi impostare i valori degli attributi e le variabili necessarie per l’integrazione con Reports &amp; Analytics (utilizzando Adobe Pipeline Services).

1. **Fare clic con il pulsante destro del mouse sull&#39;intestazione della tabella e scegliere Nuovo servizio record cliente.**

   ![](assets/6_4_CRS.png)

1. **Denomina il file di esportazione e salva.**

   Viene aperta la finestra di modifica del file di esportazione.

1. **** **OpenQuery > Configurazione CRS**.
1. **Fai clic con il pulsante destro del mouse su Attributi CRS > Aggiungi nuovo.**
1. **** ***EnterCRS*** **Attributesparameters**.

   Apri la nuova voce e inserisci o verifica i valori nella sezione *Attributi CRS* del file di esportazione:

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>Nome attributo</b> </p> </td> 
      <td colname="col2">Nome della variabile <i>Attributi del cliente</i> visualizzata in <i>Reports &amp; Analytics</i>. </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>Tipo di attributo</b> </td> 
      <td colname="col2"> <p>Questo parametro accetta i valori di (<i>int</i>, <i>string</i>). </p> <p>Nota: Se un attributo è <b>non</b> iscritto ad in Analytics: <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">L’attributo verrà creato con qualsiasi tipo di attributo valido supportato da Analytics (per questa versione è limitato a solo <i>string</i> e <i>int</i>). </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">Se immetti un tipo di attributo non valido, riceverai un errore che segnala un errore di sottoscrizione ad Analytics. </li> 
      </ul> </p> <p>Se un attributo è <b>già</b> iscritto ad in Analytics: </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">Assicurati di inserire il tipo di attributo corretto per l'attributo già sottoscritto. </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">Se immetti il tipo errato per l'attributo, il suo comportamento dipenderà dalla gestione dei tipi di attributi da parte di Analytics. </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>Nome campo</b> </p> </td> 
      <td colname="col2">Nome della dimensione o della metrica da cui sono selezionati i valori dell’attributo. <p>Nota: Il <i><b>Nome campo</b></i> in <i>Attributi CRS</i> deve essere lo stesso del <b><i>Campi di output</i> &gt; <i>Nome campo</i></b> (popolato automaticamente in base all'attributo selezionato). Se il <i>Nome campo</i> non è valido, l'esportazione non verrà eseguita. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**.
1. Inserisci il **[!UICONTROL Report Suite ID]**.

   Apri la nuova voce e immetti o verifica i valori nella sezione *Suite di rapporti* del file di esportazione:

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>Suite di rapporti</b> </td> 
      <td colname="col2">ID della suite di rapporti in <i>Reports &amp; Analytics</i> che identifica le variabili <i>Customer Attribute</i> in fase di esportazione. <p> <p>Nota: Anche se <i>Reports &amp; Analytics</i> consente di aggiungere a più suite di rapporti, Data Workbench 6.4 esporterà solo una singola suite di rapporti identificata in <i>index 0</i>. <p>Il valore della suite di rapporti inserito in questo campo è l’ID della suite di rapporti (e non il nome della suite di rapporti). </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Immetti il parametro del campo ECID.

   **Campo** ECID: Nome della dimensione nel profilo che rappresenta Adobe Experience Cloud ID. Si tratta di un campo obbligatorio. Eventuali valori di dimensione non validi immessi non verranno esportati.

1. (facoltativo) completa il parametro del campo ID visitatore .

   **Campo** ID visitatore: Se l’utente desidera inviare qualsiasi altro ID personalizzato per un visitatore nei propri dati, questo è il punto in cui immette il nome della dimensione che rappresenta l’ID visitatore personalizzato. Questo è un campo facoltativo e può essere lasciato vuoto.
