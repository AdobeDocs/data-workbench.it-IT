---
description: Le sovrapposizioni di pagina sono configurate solo nell’applicazione Sito, ma possono essere configurate per altre applicazioni.
title: Configurare una sovrapposizione pagina
uuid: c4c612ed-5154-4b20-96ab-24b74fba19a2
exl-id: 4e0dfce8-def2-49f3-93e8-41d82922fb88
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 1%

---

# Configurare una sovrapposizione pagina{#configure-a-page-overlay}

Le sovrapposizioni di pagina sono configurate solo nell’applicazione Sito, ma possono essere configurate per altre applicazioni.

Per informazioni sulla configurazione della sovrapposizione pagina per un’altra applicazione, contattare Adobe Consulting Services.

La visualizzazione sovrapposizione pagina è uno strumento per l’analisi dei collegamenti HTML. Quando si richiede una sovrapposizione per una pagina particolare, Data Workbench acquisisce un’istantanea della pagina effettiva come apparirebbe in un browser Web e analizza il codice HTML che rappresenta i collegamenti in base a un elenco di espressioni regolari definite dall’utente. Per ogni collegamento sulla pagina selezionata, il software tenta di trovare una corrispondenza di pattern di espressione regolare utilizzando l’elenco fino a quando non viene trovata la prima corrispondenza. In caso di corrispondenza, il collegamento viene evidenziato nella sovrapposizione pagina.

La sovrapposizione pagina mostra i dati solo quando aggiungi una legenda colore all’area di lavoro contenente la sovrapposizione pagina.

>[!NOTE]
>
>La configurazione della sovrapposizione pagina richiede un&#39;attenta configurazione e può dare risultati fuorvianti se i collegamenti sono mappati in modo inappropriato ai dati. Il lavoro necessario per configurare la sovrapposizione pagina per un sito specifico dipende dal modo in cui i collegamenti vengono presentati all’interno del codice HTML sulle pagine del sito.

La sovrapposizione pagina, per sua natura, suggerisce all&#39;utente il modello mentale che mostra &quot;dove le persone cliccano&quot;. Se i dati che supportano la visualizzazione non corrispondono a questo modello, il rischio di confusione è elevato.

In [!DNL Site], un collegamento rappresenta in genere un elemento dalla dimensione URI successivo o Collegamento successivo, ma puoi mappare un collegamento a qualsiasi dimensione utile per l’analisi. Per informazioni sulla configurazione della sovrapposizione pagina per altre dimensioni, contatta Adobe Consulting Services.

>[!NOTE]
>
>Si sconsiglia di utilizzare la dimensione Pagina per la sovrapposizione pagina. Gli utenti possono rinominare gli elementi delle dimensioni Pagina, modificando in tal modo la sintassi di collegamento su cui si basa la funzionalità di sovrapposizione pagina.

Per configurare la sovrapposizione pagina per [!DNL Site], devi modificare due file:

* **[!DNL Page Overlay.vw]:** Questo file è un file modello per la creazione di visualizzazioni di sovrapposizione pagina. Almeno un file modello deve essere presente nel profilo per il quale stai configurando la sovrapposizione pagina.
* **[!DNL Page Overlay Link Templates.cfg]:** Quando la visualizzazione sovrapposizione pagina carica una pagina, identifica automaticamente i collegamenti nella pagina e le relative destinazioni. Per collegare questi collegamenti agli elementi dei dati, devi definire un set di espressioni regolari in questo file.

   Puoi definire più espressioni regolari da abbinare agli elementi della dimensione. L’ordine in cui si definiscono le espressioni è importante. Quando si richiede una sovrapposizione per una pagina particolare, Data Workbench acquisisce un’istantanea della pagina effettiva come apparirebbe in un browser Web e analizza il codice HTML che rappresenta i collegamenti in base a un elenco di espressioni regolari definite dall’utente. Per ogni collegamento sulla pagina selezionata, il software tenta di trovare una corrispondenza di pattern di espressione regolare utilizzando l’elenco fino a quando non viene trovata la prima corrispondenza. La prima espressione che corrisponde a un elemento dimensione è quella utilizzata. Pertanto, è consigliabile elencare prima l’espressione regolare con il pattern di corrispondenza più specifico, seguito da espressioni meno specifiche. In caso di corrispondenza, il collegamento viene evidenziato nella visualizzazione sovrapposizione pagina.

**Per configurare la sovrapposizione pagina per il sito**

1. I

   In [!DNL Profile Manager], passa a **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.

   >[!NOTE]
   >
   >La directory Elemento Dimension contiene le voci del menu di scelta rapida visualizzate quando fate clic con il pulsante destro del mouse su un elemento di dimensione. Ad esempio, apri una tabella URI, quindi seleziona un elemento URI. Fai clic con il pulsante destro del mouse sull’URI e viene visualizzata la sovrapposizione pagina.

1. Nella cartella URI, fare clic con il pulsante destro del mouse sul segno di spunta accanto al file [!DNL Page Overlay.vw] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Specifica il dominio (e l’altezza del browser, se necessario).

   ```
   window = simpleBorderWindow: 
     client = scrollWindow: 
       client = PageOverlay: 
         URI Template = string: http://%Domain%%Element%
         URI Parameters = map: 
           Domain = string: domain name
           Element = ref: Element/Name
         Dim = ref: wdata/model/dim/URI
         Dim Element = ref: Element/Name
         Level = ref: wdata/model/dim/Page View
         Group = ref: wdata/model/dim/Session
         Browser Height = int: browser height
     pos = v3d: (518, 202, 0)
     size = v3d: (810, 610, 0)
     titleBar = editor: 
       size = v3d: (61, 19, 0)
       text = string: 
   ```

1. Salvate il file.
1. Per rendere questa modifica disponibile a tutti gli utenti del profilo di lavoro, nella sezione [!DNL Profile Manager] fare clic con il pulsante destro del mouse sul segno di spunta del file [!DNL .vw] nella colonna [!DNL User] e fare clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

   >[!NOTE]
   >
   >Puoi creare file modello aggiuntivi per altri siti o sottodomini. Ogni modello creato viene visualizzato in [!DNL Page Overlay menu].

1. Nella cartella Contesto di [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta accanto al file [!DNL Page Overlay Link Templates.cfg] e fai clic su **[!UICONTROL Make Local]**.

   Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].

1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Link Templates]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.
1. Modifica i parametri del vettore LinkRegex in base alle esigenze:

<table id="table_24DD4BB5009542F7BB1DA3318E2E6E2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questo parametro.. </th> 
   <th colname="col2" class="entry"> Fornisci queste informazioni.. </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dimensione </p> </td> 
   <td colname="col2"> <p>La dimensione (in genere la dimensione URI successivo) rappresentata dal collegamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Espressione </p> </td> 
   <td colname="col2"> <p>L’espressione regolare utilizzata per selezionare la parte pertinente del collegamento HTML per trovare l’elemento successivo dal Dimension. L'espressione regolare deve essere una corrispondenza esatta e il pattern di output desiderato è raggruppato con parentesi. Per informazioni dettagliate sulle espressioni regolari, consulta la <i>Guida alla configurazione del set di dati</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pattern di output </p> </td> 
   <td colname="col2"> <p>Il pattern di output dell’espressione regolare utilizzato per estrarre l’elemento risultante del parametro di Dimension. </p> </td> 
  </tr> 
 </tbody> 
</table>

Il file di esempio seguente mostra tre espressioni regolari:

![](assets/cfg_PageOverlayLinkTemplates_Example.png)

1. Per salvare il file, fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
1. Per rendere questa modifica disponibile a tutti gli utenti del profilo di lavoro, fai clic con il pulsante destro del mouse sul segno di spunta [!DNL Page Overlay Link Templates.cfg] nella colonna [!DNL User] e fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
