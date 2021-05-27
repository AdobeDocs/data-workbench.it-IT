---
description: L'interfaccia di Stato dettagliata è utile per la risoluzione di errori o altri problemi relativi ai computer del server Data Workbench.
title: Interfaccia di stato dettagliata
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
exl-id: 6a460ebd-fb8f-4486-9849-dad2ff745cb5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 0%

---

# Interfaccia di stato dettagliata{#detailed-status-interface}

L&#39;interfaccia di Stato dettagliata è utile per la risoluzione di errori o altri problemi relativi ai computer del server Data Workbench.

Ciò include tutti i profili [!DNL Transform] in esecuzione su tali computer o [!DNL Report] computer che sono client del server Data Workbench. È possibile accedere alle interfacce [!DNL Master Server] e [!DNL Query Server Detailed Status] tramite il menu [!DNL Admin]. Per accedere all&#39;interfaccia [!DNL Detailed Status] di altri computer, fare clic con il pulsante destro del mouse sul nodo del server per il quale si desidera visualizzare lo stato e fare clic su **[!UICONTROL Detailed Status]**. [!DNL Servers Manager] Vedere [Server Manager](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

Per ulteriori informazioni sul server Data Workbench, vedere la *Guida all&#39;installazione e all&#39;amministrazione dei prodotti server*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>Per aggiornare le informazioni in un&#39;interfaccia [!DNL Detailed Status], fai clic con il pulsante destro del mouse sull&#39;intestazione **[!UICONTROL Detailed Status]** e fai clic su **[!UICONTROL Refresh]**.

Nella tabella seguente sono elencate le attività che possono essere completate utilizzando l&#39;interfaccia [!DNL Detailed Status].

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per eseguire questa operazione.. </th> 
   <th colname="col2" class="entry"> Fai questo... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Visualizzazione di ciascun componente del computer e del relativo stato corrente </p> </td> 
   <td colname="col2"> <p>Fare clic su <span class="uicontrol"> Stato componente</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare la quantità di memoria utilizzata nel computer </p> </td> 
   <td colname="col2"> <p>Fare clic su <span class="uicontrol"> Stato memoria</span> &gt; <span class="uicontrol"> Caricamento spazio indirizzo</span>. </p> <p>Per ulteriori informazioni sul monitoraggio del carico dello spazio degli indirizzi, vedere la <i>Guida all'installazione e all'amministrazione dei prodotti server</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per determinare se il computer è configurato per utilizzare lo switch /3GB </p> </td> 
   <td colname="col2"> <p>Fare clic su <span class="uicontrol"> Stato memoria</span> &gt; <span class="uicontrol"> Spazio indirizzi di processo</span>. </p> <p>Se il campo <span class="wintitle"> Totale</span> visualizza più di 300000 KB, il computer è configurato per utilizzare lo switch /3GB. </p> <p>Per ulteriori informazioni sullo switch /3GB, vedere la <i>Guida all'installazione e all'amministrazione dei prodotti server</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per monitorare la quantità di spazio su disco e di memoria utilizzati per memorizzare ciascuna dimensione e quella utilizzata per memorizzare i nomi dei relativi elementi </p> </td> 
   <td colname="col2"> <p>Fare clic su <span class="uicontrol"> Prestazioni</span> &gt; <span class="uicontrol"> Dimension</span> &gt; <span class="uicontrol"> Utilizzo disco</span> &gt; <i>&lt;<span class="uicontrol"> nome profilo</span>&gt; </i> o <span class="uicontrol"> Prestazioni</span> &gt; <span class="uicontrol"> Dimension</span>/ &gt; <span class="uicontrol"> Utilizzo della memoria</span> &gt; <i>&lt;<span class="uicontrol"> nome profilo</span>&gt;</i>. </p> <p>I campi <span class="wintitle"> Utilizzo disco</span> forniscono il nome e la quantità di spazio su disco (in MB) necessari per memorizzare ciascuna dimensione. I numeri di utilizzo di dischi di grandi dimensioni possono influire negativamente sui tempi di query perché il server di Data Workbench deve leggere tutti i dati per completare le query correlate. Abbassare l'utilizzo del disco per una dimensione può ridurre il tempo necessario per completare le query correlate. </p> <p>I campi <span class="wintitle"> Utilizzo memoria</span> forniscono il numero di elementi in ogni dimensione e la quantità di memoria necessaria per memorizzare l’elenco dei nomi degli elementi. Un numero elevato di elementi può influire negativamente sulla quantità di memoria utilizzata durante una query, perché il server di Data Workbench deve leggere attraverso ogni elemento. La riduzione del numero di elementi in una dimensione può ridurre il tempo necessario per completare le query correlate. </p> <p>Esempio: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Dimensions&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Disk&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;1.386&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Memory&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;21&nbsp;elements,&nbsp;0.001&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per monitorare l’utilizzo della CPU per le fasi di Log Processing e Transformation </p> </td> 
   <td colname="col2"> <p>Fare clic su <span class="uicontrol"> Prestazioni</span> &gt; <span class="uicontrol"> Utilizzo CPU</span> &gt; <span class="uicontrol"> Elaborazione log</span> &gt; <i>&lt;<span class="uicontrol"> nome profilo</span>&gt;</i> o <span class="uicontrol"> Prestazioni</span> &gt; <span class="uicontrol"> Utilizzo CPU</span> &gt; <span class="uicontrol"> Trasformazione</span> &gt; &lt;<span class="uicontrol"> nome profilo</span>&gt;. </p> <p>Ognuno di questi set di campi fornisce l’utilizzo della CPU (in secondi) per ciascuna delle fasi nell’elaborazione e nella trasformazione del registro. </p> <p>Esempio:  <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>Il tempo necessario per completare una query è in genere proporzionale alla dimensione totale di tutte le dimensioni. Dopo aver esaminato le dimensioni di ciascuna dimensione, puoi valutare se una particolare dimensione è sufficientemente utile e utilizzata con frequenza sufficiente a giustificare il costo di prestazioni della dimensione. In caso contrario, puoi eliminare la dimensione nel <span class="wintitle"> Profile Manager</span>.<p>Una dimensione il cui elenco di nomi di elementi è eccessivamente grande (ovvero superiore a 128 MB) può causare errori di "memoria esaurita" anche se l’utilizzo totale dello spazio degli indirizzi non è vicino al limite. </p> <p>Inoltre, se utilizzi un cluster di server Data Workbench ma non utilizzi la normalizzazione centralizzata, una dimensione con un elenco di nomi di elementi di grandi dimensioni ha un impatto significativo sui budget di invio della memoria. Per ulteriori informazioni sulla normalizzazione centralizzata, consulta la <i>Guida alla configurazione del set di dati</i>. Se la quantità di memoria necessaria per memorizzare tutti gli elenchi di nomi di elementi combinati è superiore a 100 MB su tutti i server del cluster, si potrebbero ricevere errori "Invia budget di memoria superato" anche quando l'attività di query è leggera. Ad esempio, se disponi di un cluster a quattro server con più di 25 MB su ogni server utilizzato per memorizzare gli elenchi dei nomi degli elementi, potresti ricevere errori. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per monitorare il tempo trascorso nell’elaborazione e nella trasformazione del registro </p> </td> 
   <td colname="col2"> <p>Fare clic su <span class="uicontrol"> Prestazioni</span> &gt; <span class="uicontrol"> Utilizzo CPU</span> &gt; <span class="uicontrol"> Elaborazione log</span> &gt; <i>&lt;<span class="uicontrol"> nome profilo</span>&gt;</i> o <span class="uicontrol"> Prestazioni</span> &gt; <span class="uicontrol"> Utilizzo CPU</span> &gt; <span class="uicontrol"> Trasformazione</span> &gt; <i>&lt;<span class="uicontrol"> nome profilo</span>&gt;</i>. </p> <p>La revisione dei campi in queste sezioni ti consente di identificare i filtri e le trasformazioni che possono influenzare negativamente il tempo necessario per l’elaborazione e la trasformazione del registro. Puoi quindi prendere decisioni di progettazione relative ai singoli filtri e trasformazioni con tempi di elaborazione lunghi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per monitorare l'utilizzo dello spazio su disco e aumentare la velocità della query </p> </td> 
   <td colname="col2"> <p>Fai clic su <span class="uicontrol"> Prestazioni</span> &gt; <span class="uicontrol"> Campi di elaborazione del registro</span> &gt; <i>&lt;<span class="uicontrol"> nome profilo</span></i>. </p> <p>Ogni voce in questa sezione corrisponde a un parametro nel file <span class="filepath"> Log Processing.cfg</span> . La revisione di questi campi consente di vedere la quantità di memoria utilizzata da ogni parametro. Puoi quindi prendere decisioni di progettazione riguardo a singoli elementi che sono piuttosto grandi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per determinare il tempo trascorso della trasformazione o del ritrattamento precedente </p> </td> 
   <td colname="col2"> <p>Fai clic su <span class="uicontrol"> Stato elaborazione</span> &gt; <i>&lt;<span class="uicontrol"> nome profilo</span>&gt;</i> &gt; <span class="uicontrol"> Cronologia modalità elaborazione</span>. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Tempo reale: tempo in cui il server Data Workbench era disponibile per l’esecuzione di query. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Fast Input - Questo tempo più il tempo di Fast Merge è il tempo totale necessario per l'elaborazione del set di dati. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Fast Merge: tempo totale necessario per la trasformazione del set di dati. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per diagnosticare i problemi "al momento" </p> </td> 
   <td colname="col2"> <p>Fai clic su <span class="uicontrol"> Stato elaborazione</span> &gt; <i>&lt;<span class="uicontrol"> nome profilo</span>&gt;</i> &gt; <span class="uicontrol"> A partire da ora</span> &gt; <span class="uicontrol"> Origini a partire da</span>. </p> <p>La revisione del numero di volte per ogni origine può essere utile per determinare quali origini possono influenzare negativamente il valore di A complessivo. Puoi quindi affrontare i problemi con quelle particolari fonti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per stimare il tempo necessario al completamento di una query in esecuzione </p> </td> 
   <td colname="col2"> <p>Fare clic su <span class="uicontrol"> Execution Engine</span>. </p> <p>La revisione del campo <span class="wintitle"> Data Sweep Time</span> fornisce una stima del tempo necessario al completamento di una query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per elencare tutti i profili disponibili nel computer e i dettagli sul loro stato </p> </td> 
   <td colname="col2"> <p>Fare clic su <span class="uicontrol"> Profiles</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare lo stato della replica </p> </td> 
   <td colname="col2"> <p>Fare clic su <span class="uicontrol"> Stato componente</span>. </p> <p>Controlla lo stato del componente Replicare. Se la replica è in esecuzione, viene visualizzato OK. Se il componente Replica non è riuscito, viene visualizzato un messaggio di errore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare lo stato <span class="wintitle"> Report Server</span> per un computer <span class="keyword"> Report</span> che si connette al server Data Workbench </p> </td> 
   <td colname="col2"> <p>Fare clic su <span class="uicontrol"> Stato server di rapporto</span>. </p> <p>Questa sezione dell'interfaccia <span class="wintitle"> Detailed Status</span> include una copia del file <span class="filepath"> Report Server.cfg</span>, informazioni sul numero di rapporti in esecuzione (Sezione corrente) e informazioni sull'errore più recente (Ultimo errore). </p> <p>Per i passaggi da eseguire per modificare il file <span class="filepath"> Report Server.cfg</span>, vedere la <i>Data Workbench guida ai rapporti</i>. </p> <p> <p>Nota: Se la sezione <span class="wintitle"> Stato del server di rapporto</span> non viene visualizzata nell'interfaccia <span class="wintitle"> Stato dettagliato</span>, potrebbe essere necessario configurare il server di Data Workbench per visualizzare <span class="wintitle"> Stato del server di rapporto</span>. Per i passaggi, vedere la <i>Data Workbench guida ai rapporti</i>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare le informazioni sull'utilizzo della memoria per Transform </p> </td> 
   <td colname="col2"> <p>Fare clic su <span class="uicontrol"> Stato elaborazione</span> &gt; <span class="uicontrol"> Trasforma</span>. </p> <p>Per ulteriori informazioni su Transform, vedere la <i>Guida all'installazione e all'amministrazione dei prodotti server</i> e la <i>Guida alla configurazione dei set di dati</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per salvare l'interfaccia <span class="wintitle"> Detailed Status</span> come file <span class="filepath"> *.cfg</span> che può essere aperto in un editor di testo come Blocco note o distribuito ad altri </p> </td> 
   <td colname="col2"> <p>Fai clic con il pulsante destro del mouse sull'intestazione <span class="uicontrol"> Stato dettagliato</span> e fai clic su <span class="uicontrol"> Salva copia come</span>. </p> <p>Nota:  <p>Fare clic con il pulsante destro del mouse sull'intestazione <span class="uicontrol"> Stato dettagliato</span> e fare clic su <span class="uicontrol"> Salva</span> su <i>nome server</i>/Stato/ non funziona nell'interfaccia <span class="wintitle"> Stato dettagliato</span>. Viene visualizzato il seguente messaggio di errore: </p> <p>Impossibile salvare /Status/. 403 Vietato </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare la metrica <span class="uicontrol"> Righe per origine registro</span> </p> </td> 
   <td colname="col2"> <p>Se le righe per metrica Origine registro devono essere riportate in Stato dettagliato, l’amministratore della Data Workbench deve definire l’"ID origine registro" e fornire un nome univoco nel file Log Processing.cfg del profilo personalizzato. </p> </td> 
  </tr> 
 </tbody> 
</table>
