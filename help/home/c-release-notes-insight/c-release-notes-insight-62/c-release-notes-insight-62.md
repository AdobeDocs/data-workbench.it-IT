---
description: Le note sulla versione di Data Workbench 6.2 includono nuove funzioni, requisiti per l’aggiornamento, correzioni di bug e problemi noti.
title: Note sulla versione di Data Workbench 6.2
uuid: 8631c936-d53b-493d-9f58-72f541c3ddce
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 2%

---


# Note sulla versione di Data Workbench 6.2{#data-workbench-release-notes}

Le note sulla versione di Data Workbench 6.2 includono nuove funzioni, requisiti per l’aggiornamento, correzioni di bug e problemi noti.

## Nuove funzionalità {#section-1225066ea8f44cf68e42e019d0bca816}

La Data Workbench 6.2 include le seguenti nuove funzioni:

| Funzioni | Descrizione |
|--- |--- |
| Alberi delle decisioni | Le strutture decisionali sono una visualizzazione di analisi predittiva utilizzata per valutare le caratteristiche e le relazioni dei visitatori. Il Generatore albero decisionale genera una visualizzazione struttura decisionale basata su uno specifico caso positivo e su un insieme di input. |
| Aggiornamento al filtro binario nella matrice di correlazione | Il filtro binario è stato aggiornato con nuove funzioni e richiede di rigenerare qualsiasi matrice di correlazione con un filtro binario integrato nelle versioni precedenti. |
| Mappa di densità | La mappa di densità è una visualizzazione che visualizza gli elementi come rettangoli ombreggiati all’interno di una mappa quadrata. |
| Profilo di attribuzione | Per analizzare rapidamente i valori di attribuzione (eventi per attribuire la responsabilità di una conversione o di una vendita di successo), Data Workbench fornisce un profilo di attribuzione basato su regole con funzioni che consentono all&#39;architetto di impostare i rapporti di attribuzione e all&#39;analista di eseguire i rapporti. |
| Report di analisi | I modelli di report standardizzano  rapporti di Adobe Analytics per gli utenti del workbench dati che utilizzano il profilo SC del Adobe . Tali rapporti sono identici a quelli utilizzati in Marketing Reports &amp; Analytics (ex SiteCatalyst). |
| Dispersioni 3D | Un grafico a dispersione 3D rappresenta gli elementi di una dimensione dati (come Giorni o Sito di riferimento) su una griglia tridimensionale in cui gli assi x, y e z rappresentano diverse metriche. |


## Data Workbench aggiornamenti interfaccia utente client{#data-workbench-client-ui-updates}

Data Workbench 6.2 include nuovi aggiornamenti dell&#39;interfaccia utente al pannello Segnalibri, nuove icone nella barra degli strumenti dell&#39;area di lavoro, la possibilità di trascinare l&#39;area di lavoro all&#39;interno di una schermata, nuovi tasti rapidi e aggiornamenti alla visualizzazione del grafico a torta.

## Nuove funzioni segnalibro {#section-e361b605441540ca8213c3fddb5e0718}

Ora è possibile contrassegnare aree di lavoro significative per spostarsi rapidamente tra le visualizzazioni e i rapporti utilizzati nel flusso di lavoro.

**Utilizzo dei segnalibri**

1. Segnalibro un&#39;area di lavoro facendo clic sull&#39;icona Segnalibro ![](assets/bookmark_icon.png) nell&#39;angolo superiore destro della barra degli strumenti.
1. Fare clic su **[!UICONTROL Add]** > **[!UICONTROL Bookmarks Panel]** nel riquadro a sinistra per aprire un elenco di segnalibri.

   ![](assets/bookmarks_panel.png)

1. Per aprire un’area di lavoro con segnalibro, fate clic sul nome di un’area di lavoro nella **[!UICONTROL Bookmark Panel]**.

   ![](assets/bookmarks_panel_left.png)

   Viene aperta l’area di lavoro selezionata. Quando si fa clic su un’altra area di lavoro con segnalibro, l’area di lavoro precedente viene chiusa e viene aperta la nuova area di lavoro selezionata, consentendo di spostarsi rapidamente nel flusso di lavoro.

**Per eliminare un segnalibro:**

* Nel pannello Segnalibri, fare clic con il pulsante destro del mouse e selezionare **Rimuovi`<bookmark title>`** per eliminare un segnalibro selezionato, oppure selezionare **[!UICONTROL Clear All Bookmarks]** per eliminare tutti i segnalibri.

* È inoltre possibile fare clic con il pulsante destro del mouse sull&#39;area di lavoro nella visualizzazione delle miniature all&#39;interno del piano di lavoro e selezionare **[!UICONTROL Clear Bookmark]**.

>[!IMPORTANT]
>
>* È possibile salvare 25 segnalibri.
>* Se aggiungete un segnalibro e quindi spostate la posizione dell&#39;area di lavoro, il segnalibro non sarà valido e deve essere eliminato dal pannello Segnalibri e reimpostato.

>



## Nuove icone in Workspace {#section-c108bbd1661249e79c146727ff3d2470}

Data Workbench 6.2 ora sostituisce il testo nell’area di lavoro con delle icone. Puoi comunque passare il mouse sopra e visualizzare il messaggio della descrizione comandi che identifica l’icona, incluso **[!UICONTROL File]**, **[!UICONTROL Add]** e **[!UICONTROL Export]**.

![](assets/new_icons.png)

È stata aggiunta una nuova **[!UICONTROL Help]** icona per accedere alla documentazione e ad altri centri di conoscenza, con i seguenti collegamenti:

<table id="table_64BBC67B1BB44B1197FF7E5E7B067696"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Collegamenti alla documentazione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Reports &amp; Analytics per il marketing </td> 
   <td colname="col2">Aprite la pagina dell'aiuto <span class="uicontrol"> Adobe Reporting e analisi</span> di marketing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Idea Exchange </td> 
   <td colname="col2">Aprite l' <span class="uicontrol"> accesso</span>a Idea Exchange. Questo portale online consente agli utenti di fornire modifiche aggiornate e idee di miglioramento al workbench dati. Queste idee incentrate sui clienti possono essere poi votate da tutti gli utenti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aiuto </td> 
   <td colname="col2">Aprite la documentazione <span class="uicontrol"> di</span>Data Workbench. <p>È inoltre possibile premere <span class="uicontrol"> &lt;F1&gt;</span> per aprire la guida all'interno di un'area di lavoro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informazioni </td> 
   <td colname="col2">Apri per identificare la versione <span class="uicontrol"></span> client del workbench dati. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>È inoltre possibile premere `<F1>` per aprire la documentazione da un’area di lavoro.

## Trascinamento delle visualizzazioni dell’area di lavoro {#section-9129c340c21d45a3864c923884cd4382}

Se un’area di lavoro è più grande dello schermo visibile, potete spostare la visualizzazione per visualizzare tutti gli elementi all’interno dell’area di lavoro. Puoi fare clic sullo sfondo (all’esterno delle visualizzazioni e delle tabelle) e trascinare lo schermo per spostare l’area di visualizzazione all’interno dell’area di lavoro. Quando si trascina la vista all’interno della cornice dell’area di lavoro, il cursore assume la forma di un’icona a forma di mano.

![](assets/drag_workspace.png)

## Tasti rapidi per modificare le visualizzazioni dell&#39;area di lavoro {#section-d8322f72423f437aa2e34f2188b1341c}

I nuovi tasti di scelta rapida consentono di ridimensionare e riadattare le aree di lavoro tra le visualizzazioni a finestra e a pagina intera.

<table id="table_A01C514C99F043338D183A6839E03DEA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Comandi </th> 
   <th colname="col2" class="entry"> Tasti rapidi </th> 
   <th colname="col3" class="entry"> Comandi di menu combinati </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Visualizzazione</b>a schermo intero. Workspace riempie lo schermo e si riallinea alle nuove dimensioni. </td> 
   <td colname="col2"><b>Ctrl +</b> <p>Ctrl + (sulla tastiera) </p> <p><i>o</i> </p> <p>Ctrl + Maiusc + (sulla tastiera) </p> </td> 
   <td colname="col3"> 
    <ul id="ul_C7C731B894D946D9916F50806F015857"> 
     <li id="li_452B4C119B1A40038A408CFFC53653A9">File &gt; Dimensioni pagina &gt; Riempi schermo <p><i>seguita da</i> </p> </li> 
     <li id="li_DE9B8B31B9F24A6AA68A1D0DB886B501">File &gt; Riadatta area di lavoro </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Vista</b>finestra. Workspace viene visualizzato in una vista finestra standard e si rifà alle nuove dimensioni. </td> 
   <td colname="col2"><b>Ctrl+Z</b> <p>Ctrl - </p> </td> 
   <td colname="col3"> 
    <ul id="ul_3474B9EFD69343C09BC84E485D896C28"> 
     <li id="li_820BAED76FF24A5785E6D89C5C692DD5">File &gt; Dimensioni pagina &gt; Standard <p><i>seguita da</i> </p> </li> 
     <li id="li_337789F282CE4C2C990C67B115782454">File &gt; Riadatta area di lavoro </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Correzioni di bug {#section-8704a9ac358246cd81233dd0982d534f}

* È stato aggiornato il file di ricerca del sito visivo per risolvere le modifiche al termine di ricerca della query apportate dal motore di ricerca.
* È stato corretto un messaggio di errore non accurato, &quot;Impossibile importare l&#39;area di lavoro&quot;, durante l&#39;importazione di un&#39;area di lavoro nella workstation client anche se l&#39;importazione ha avuto esito positivo.
* L&#39;errore di connessione della workstation che visualizza il messaggio &quot;412 Configuration Conflict&quot; (Conflitto di configurazione 412) ora viene sostituito con un messaggio descrittivo che identifica l&#39;azione del sistema.
* È ora possibile eseguire il comando &quot;post&quot; nel server di report.
* Sono stati corretti degli errori di interfaccia utente nell&#39;interfaccia client per il cinese semplificato.
*  Adobe Analytics ha aggiornato il feed di dati che consente l&#39;Data Workbench per sfruttare i profili e le audience che si integrano con l&#39;Adobe Experience Cloud. Tutti gli utenti delle Date Workbench dovevano preparare il proprio ambiente per questa transizione entro il 21 aprile 2014.

   Profili e pubblico è stato introdotto per fornire una visualizzazione completa dei clienti in  Adobe Analytics. Questo nuovo servizio è disponibile all&#39;interno dell&#39;Adobe Experience Cloud per fornire ulteriore valore tra gli strumenti di analisi, in modo da iniziare a stabilire le basi per queste funzionalità in Analytics. Il nuovo identificatore visitatore  Experience Cloud verrà aggiunto al feed di dati, insieme ad altri miglioramenti e miglioramenti per adattarsi al nuovo feed di dati e all’identificatore visitatore globale.
* Durante l’importazione di un’area di lavoro, viene visualizzato un messaggio di errore anche se l’importazione è avvenuta correttamente.

## Requisiti per l&#39;aggiornamento {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* Il profilo Attribuzione è configurato per gli utenti che hanno implementato il profilo SC del Adobe  per utilizzare il feed di dati di Analytics (SC/Insight). Per impostazione predefinita, gli eventi Marketing e Conversion vengono utilizzati come interazioni predefinite valutate nei modelli basati su regole.
* Per gli utenti del profilo SC del Adobe  aggiornamento alla Data Workbench 6.2, se non si utilizzano le configurazioni predefinite, verificare che il [!DNL x-bot_id] valore nel [!DNL SC Fields.cfg] file sia decodificato correttamente e che il [!DNL x-bot_id] campo sia elencato correttamente nel [!DNL Decoding Instructions.cfg] file e nei [!DNL Exclude Hit.cfg] file. Questo problema si verifica solo se il file di configurazione è stato modificato dalla configurazione predefinita.

* Se avete eliminato i campi inutilizzati nel **[!UICONTROL Dataset]** > **[!UICONTROL Log Processing]** > **[!DNL SC Fields.cfg]** file per il profilo SC del Adobe , dovrete aggiornarli per contenere i valori dei campi aggiornati utilizzati per il profilo Attribuzione.

## Problemi noti {#section-dbb307639835493a83409f5f461932b8}

* Quando la visualizzazione della mappa di dispersione 3D include i callout, lo zoom può visualizzare i grafici al di fuori del bordo della visualizzazione.

   Soluzione: Effettua prima uno zoom con il grafico a dispersione 3D, quindi aggiungi i callout alla visualizzazione.
* Trascinando la metrica dal pannello Finder alla legenda metrica all’esterno della colonna metrica, la legenda metrica viene eliminata dall’area di lavoro.

   Soluzione: Gli utenti che desiderano trascinare le metriche nella legenda metrica devono essere inseriti nella prima colonna (colonna delle metriche).
* Le opzioni Stampa area di lavoro tramite barra laterale ed Entrambe non includeranno le informazioni sul copyright nella pagina stampata.
* L&#39;utilizzo di Workstation in una sessione desktop remota si arresterà in modo anomalo durante la ridenominazione delle aree di lavoro.
* (Nella versione cinese semplificata) Gli output effettivi dei rapporti sono validi nel server di report, ma le righe oggetto e i nomi dei file allegati dell&#39;e-mail sono illeggibili.
* (Nella versione in cinese semplificato) Quando si utilizza il ritorno a capo automatico nella visualizzazione Foglio di lavoro, le parole localizzate non vengono racchiuse correttamente e alla stringa vengono aggiunti caratteri spazzatura.
* (Nella versione cinese semplificata) Impossibile avviare Insight.exe se la directory di installazione è denominata con caratteri non inglesi.

   Soluzione: Mantenete i nomi predefiniti o rinominate utilizzando solo i caratteri inglesi nel percorso della cartella per avviare i file eseguibili.

