---
description: Le sovrapposizioni di pagina sono configurate solo nell'applicazione Site, ma possono essere configurate per altre applicazioni.
solution: Analytics
title: Configurare una sovrapposizione pagina
topic: Data workbench
uuid: c4c612ed-5154-4b20-96ab-24b74fba19a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurare una sovrapposizione pagina{#configure-a-page-overlay}

Le sovrapposizioni di pagina sono configurate solo nell&#39;applicazione Site, ma possono essere configurate per altre applicazioni.

Per informazioni sulla configurazione della sovrapposizione di pagina per un’altra applicazione, contattate Adobe Consulting Services.

La visualizzazione delle sovrapposizioni di pagina è uno strumento per l’analisi dei collegamenti HTML. Quando si richiede una sovrapposizione per una particolare pagina, Workbench dati acquisisce un&#39;istantanea della pagina effettiva così come apparirebbe in un browser Web e analizza il codice HTML che rappresenta i collegamenti in base a un elenco di espressioni regolari definite dall&#39;utente. Per ogni collegamento sulla pagina selezionata, il software tenta di trovare una corrispondenza per un pattern di espressione regolare, utilizzando l&#39;elenco fino a trovare la prima corrispondenza. Se esiste una corrispondenza, il collegamento viene evidenziato nella sovrapposizione pagina.

La sovrapposizione pagina mostra i dati solo quando aggiungete una legenda colore all’area di lavoro contenente la sovrapposizione pagina.

>[!NOTE]
>
>La configurazione della sovrapposizione di pagina richiede un’attenta configurazione e può generare risultati fuorvianti se i collegamenti sono mappati in modo inappropriato ai dati. Il lavoro di configurazione della sovrapposizione di pagina per un sito specifico dipende dal modo in cui i collegamenti vengono presentati nel codice HTML sulle pagine del sito.

La sovrapposizione pagina, per sua natura, suggerisce all&#39;utente il modello mentale che mostra &quot;dove le persone fanno clic&quot;. Se i dati che supportano la visualizzazione non corrispondono a questo modello, il potenziale di confusione è elevato.

In [!DNL Site]un collegamento rappresenta in genere un elemento dalla dimensione URI successivo o Collegamento successivo, ma potete mappare un collegamento a qualsiasi dimensione che abbia senso per l&#39;analisi. Per informazioni sulla configurazione della sovrapposizione di pagina per altre dimensioni, contattate Adobe Consulting Services.

>[!NOTE]
>
>Si consiglia di non utilizzare la dimensione Pagina per la sovrapposizione pagina. Gli utenti possono rinominare gli elementi delle dimensioni Pagina, modificando in tal modo la sintassi di collegamento su cui si basa la funzionalità di sovrapposizione pagina.

Per configurare la sovrapposizione pagina per [!DNL Site], dovete modificare due file:

* **[!DNL Page Overlay.vw]:**Questo file è un file modello per la creazione di visualizzazioni di sovrapposizione pagina. Nel profilo per il quale state configurando la sovrapposizione pagina deve essere presente almeno un file modello.
* **[!DNL Page Overlay Link Templates.cfg]:**Quando la visualizzazione delle sovrapposizioni di pagina carica una pagina, identifica automaticamente i collegamenti nella pagina e le relative destinazioni. Per collegare questi collegamenti agli elementi nei dati, è necessario definire un set di espressioni regolari in questo file.

   È possibile definire più espressioni regolari da confrontare con gli elementi della dimensione. L&#39;ordine in cui vengono definite le espressioni è importante. Quando si richiede una sovrapposizione per una particolare pagina, Workbench dati acquisisce un&#39;istantanea della pagina effettiva così come apparirebbe in un browser Web e analizza il codice HTML che rappresenta i collegamenti in base a un elenco di espressioni regolari definite dall&#39;utente. Per ogni collegamento sulla pagina selezionata, il software tenta di trovare una corrispondenza per un pattern di espressione regolare, utilizzando l&#39;elenco fino a trovare la prima corrispondenza. La prima espressione che corrisponde a un elemento dimensione è quella utilizzata. Pertanto, è consigliabile elencare innanzitutto l&#39;espressione regolare con il pattern di corrispondenza più specifico, seguito da espressioni meno specifiche. Se esiste una corrispondenza, il collegamento viene evidenziato nella visualizzazione sovrapposizione pagina.

**Per configurare la sovrapposizione pagina per il sito**

1. I

   In [!DNL Profile Manager], accedete a **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.

   >[!NOTE]
   >
   >La directory Elemento dimensione contiene le voci del menu di scelta rapida che vengono visualizzate quando si fa clic con il pulsante destro del mouse su un elemento dimensione. Ad esempio, aprite una tabella URI, quindi selezionate un elemento URI. Fare clic con il pulsante destro del mouse sull&#39;URI e sulla sovrapposizione pagina.

1. Nella cartella URI, fare clic con il pulsante destro del mouse sul segno di spunta accanto al [!DNL Page Overlay.vw] file e fare clic **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Specificate il dominio (e l’altezza del browser, se necessario).

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
1. Per rendere disponibile questa modifica a tutti gli utenti del profilo di lavoro, nel [!DNL Profile Manager]pannello fare clic con il pulsante destro del mouse sul segno di spunta del [!DNL .vw] file nella [!DNL User] colonna e scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Potete creare file modello aggiuntivi per altri siti o sottodomini. Ogni modello creato viene visualizzato nel pannello [!DNL Page Overlay menu].

1. Nella cartella Contesto del [!DNL Profile Manager]file, fare clic con il pulsante destro del mouse sul segno di spunta accanto al [!DNL Page Overlay Link Templates.cfg] file e fare clic **[!UICONTROL Make Local]**.

   Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.

1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Fare clic con il pulsante destro del mouse **[!UICONTROL Link Templates]** e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.
1. Modificate i parametri per il vettore LinkRegex, a seconda delle necessità:

<table id="table_24DD4BB5009542F7BB1DA3318E2E6E2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questo parametro... </th> 
   <th colname="col2" class="entry"> Fornire queste informazioni... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dimensione </p> </td> 
   <td colname="col2"> <p>La dimensione (in genere la dimensione URI successivo) rappresentata dal collegamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Espressione </p> </td> 
   <td colname="col2"> <p>L'espressione regolare utilizzata per selezionare la parte pertinente del collegamento HTML per trovare l'elemento successivo dalla Dimensione. L'espressione regolare deve corrispondere esattamente e il pattern di output desiderato è raggruppato con parentesi. Per informazioni dettagliate sulle espressioni regolari, consultate la Guida alla configurazione del <i>set di dati</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pattern di output </p> </td> 
   <td colname="col2"> <p>Il pattern di output dell'espressione regolare utilizzato per estrarre l'elemento risultante del parametro Dimension. </p> </td> 
  </tr> 
 </tbody> 
</table>

Il seguente file di esempio mostra tre espressioni regolari:

![](assets/cfg_PageOverlayLinkTemplates_Example.png)

1. Per salvare il file, fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.
1. Per rendere disponibile questa modifica a tutti gli utenti del profilo di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta [!DNL Page Overlay Link Templates.cfg] nella [!DNL User] colonna e scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

