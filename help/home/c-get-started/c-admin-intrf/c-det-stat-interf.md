---
description: L'interfaccia Stato dettagliato è utile per risolvere eventuali errori o altri problemi relativi ai computer server Workbench dati.
solution: Analytics
title: Interfaccia di stato dettagliata
topic: Data workbench
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Interfaccia di stato dettagliata{#detailed-status-interface}

L&#39;interfaccia Stato dettagliato è utile per risolvere eventuali errori o altri problemi relativi ai computer server Workbench dati.

Sono inclusi eventuali [!DNL Transform] profili in esecuzione su tali computer o [!DNL Report] computer client del server Workbench dati. È possibile accedere [!DNL Master Server] e [!DNL Query Server Detailed Status] interfacce tramite il [!DNL Admin] menu. Per accedere all&#39; [!DNL Detailed Status] interfaccia per altri computer, fare clic con il [!DNL Servers Manager]pulsante destro del mouse sul nodo del server per il quale si desidera visualizzare lo stato e fare clic su **[!UICONTROL Detailed Status]**. Vedere [Server Manager](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

Per ulteriori informazioni sul server Workbench dati, vedere la Guida all&#39;installazione e all&#39;amministrazione dei prodotti *server*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>Per aggiornare le informazioni in un&#39; [!DNL Detailed Status] interfaccia, fare clic con il pulsante destro del mouse sull&#39; **[!UICONTROL Detailed Status]** intestazione e fare clic **[!UICONTROL Refresh]**.

Nella tabella seguente sono elencate le attività che è possibile completare utilizzando l&#39; [!DNL Detailed Status] interfaccia.

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per eseguire questa operazione... </th> 
   <th colname="col2" class="entry"> Fai questo... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare ciascun componente del computer e il relativo stato </p> </td> 
   <td colname="col2"> <p>Fate clic su Stato <span class="uicontrol"></span>componente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare la quantità di memoria utilizzata nel computer </p> </td> 
   <td colname="col2"> <p>Fate clic su <span class="uicontrol"> Stato</span> memoria &gt; <span class="uicontrol"> Caricamento</span>spazio indirizzo. </p> <p>Per ulteriori informazioni sul monitoraggio del carico dello spazio degli indirizzi, vedere la Guida all'installazione e all'amministrazione dei prodotti <i>server</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per determinare se il computer è configurato per utilizzare lo switch /3GB </p> </td> 
   <td colname="col2"> <p>Fate clic su <span class="uicontrol"> Stato</span> memoria &gt; <span class="uicontrol"> Spazio</span>indirizzi di processo. </p> <p>Se nel campo <span class="wintitle"> Totale</span> sono visualizzati più di 300000 KB, il computer è configurato per utilizzare lo switch /3GB. </p> <p>Per ulteriori informazioni sullo switch /3GB, vedere la Guida all'installazione e all'amministrazione dei prodotti <i>server</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per monitorare la quantità di spazio su disco e di memoria utilizzata per memorizzare ciascuna dimensione e per memorizzare i nomi dei relativi elementi </p> </td> 
   <td colname="col2"> <p>Fate clic su <span class="uicontrol"> Prestazioni</span> &gt; <span class="uicontrol"> Dimensioni</span> &gt; Utilizzo <span class="uicontrol"> del</span> disco &gt; <i>&lt;<span class="uicontrol"> nome</span>profilo&gt; </i><span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span> <i><span class="uicontrol"></span></i>o Prestazioni &gt; Dimensioni &gt; Dimensioni &gt; Uso memoria &gt; &lt;nome profilo&gt; &gt; Memoria. </p> <p>I campi Uso <span class="wintitle"></span> del disco forniscono il nome e la quantità di spazio su disco (in MB) necessari per memorizzare ciascuna dimensione. Numeri di utilizzo di dischi di grandi dimensioni possono influire negativamente sui tempi di query perché il server Workbench dati deve leggere tutti i dati per completare le query correlate. Abbassare l'utilizzo del disco per una dimensione può ridurre il tempo necessario per completare le relative query. </p> <p>I campi <span class="wintitle"> Utilizzo</span> memoria forniscono il numero di elementi in ogni dimensione e la quantità di memoria necessaria per memorizzare l'elenco dei nomi degli elementi. Un elevato numero di elementi può influire negativamente sulla quantità di memoria utilizzata durante una query, in quanto il server Workbench dati deve leggere ciascun elemento. La riduzione del numero di elementi in una dimensione può ridurre il tempo necessario per completare le query correlate. </p> <p>Esempio: <code>+&nbsp;Performance
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
   <td colname="col1"> <p>Per monitorare l'utilizzo della CPU per le fasi di elaborazione e trasformazione del registro </p> </td> 
   <td colname="col2"> <p>Fate clic su <span class="uicontrol"> Prestazioni</span> &gt; <span class="uicontrol"> Utilizzo</span> CPU &gt; <span class="uicontrol"> Elaborazione</span> log &gt; <i>&lt;<span class="uicontrol"> nome</span>profilo&gt;</i> <span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span><span class="uicontrol"></span>o prestazioni &gt; Uso CPU &gt; Uso CPU &gt; Trasformazione &gt; &lt;nome profilo&gt;. </p> <p>Ciascuno di questi insiemi di campi fornisce l'utilizzo della CPU (in secondi) per ciascuna delle fasi nell'elaborazione e nella trasformazione del registro. </p> <p>Esempio: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>Il tempo necessario per completare una query è in genere proporzionale alla dimensione totale di tutte le dimensioni. Dopo aver esaminato le dimensioni di ciascuna dimensione, è possibile valutare se una particolare dimensione sia sufficientemente utile e utilizzata con frequenza sufficiente a giustificare il costo di prestazioni della dimensione. In caso contrario, puoi eliminare la dimensione in Gestione <span class="wintitle"></span>profili. Consulta<a href="../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-prof-mgr.md"> Il Gestore</a>Del Profilo. </p> <p>Una dimensione il cui elenco di nomi di elementi è eccessivamente grande (ovvero superiore a 128 MB) può causare errori di "memoria insufficiente" anche se l'utilizzo totale dello spazio indirizzo non è vicino al limite. </p> <p>Inoltre, se si utilizza un cluster di server Workbench dati ma non si utilizza la normalizzazione centralizzata, una dimensione con un elenco di nomi di elementi di grandi dimensioni ha un impatto significativo sui budget di invio della memoria. Per ulteriori informazioni sulla normalizzazione centralizzata, consulta la Guida alla configurazione del <i>set di dati</i>. Se la quantità di memoria necessaria per memorizzare tutti gli elenchi di nomi di elementi combinati è superiore a 100 MB su tutti i server del cluster, è possibile che si verifichino errori "Invia budget di memoria superato" anche quando l'attività di query è leggera. Ad esempio, se disponete di un cluster a quattro server con oltre 25 MB su ciascun server utilizzato per memorizzare gli elenchi dei nomi degli elementi, potreste ricevere degli errori. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per monitorare il tempo trascorso nell'elaborazione dei log e nella trasformazione </p> </td> 
   <td colname="col2"> <p>Fate clic su <span class="uicontrol"> Prestazioni</span> &gt; <span class="uicontrol"> Utilizzo</span> CPU &gt; <span class="uicontrol"> Elaborazione</span> log &gt; <i>&lt;<span class="uicontrol"> nome</span>profilo&gt;</i> <span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span> <i><span class="uicontrol"></span></i>o prestazioni &gt; Uso CPU &gt; Uso CPU &gt; Trasformazione &gt; Interfaccia&lt;nome profilo&gt;&gt; . </p> <p>La revisione dei campi in queste sezioni consente di identificare filtri e trasformazioni che potrebbero avere un impatto negativo sulla quantità di tempo necessaria per l'elaborazione e la trasformazione del registro. Potrete quindi prendere decisioni di progettazione relative ai singoli filtri e trasformazioni con lunghi tempi di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per monitorare l'utilizzo dello spazio su disco e aumentare la velocità della query </p> </td> 
   <td colname="col2"> <p>Fare clic su <span class="uicontrol"> Prestazioni</span> &gt; <span class="uicontrol"> Campi</span> di elaborazione log &gt; <i>&lt;<span class="uicontrol"> nome</span>profilo&gt;</i>. </p> <p>Ogni elemento di questa sezione corrisponde a un parametro nel file <span class="filepath"> Log Processing.cfg</span> . La revisione di questi campi consente di verificare la quantità di memoria utilizzata da ogni parametro. Potete quindi prendere decisioni di progettazione per singoli elementi che sono piuttosto grandi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per determinare il tempo trascorso della precedente rielaborazione o trasformazione </p> </td> 
   <td colname="col2"> <p>Fate clic su <span class="uicontrol"> Stato</span> elaborazione &gt; <i>&lt;<span class="uicontrol"> nome</span>profilo&gt;</i> &gt; <span class="uicontrol"> Cronologia</span>modalità di elaborazione. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Real Time - Time (Tempo reale): il server Workbench dati era disponibile per le query. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Input veloce: questo tempo più il tempo di Unione veloce è il tempo totale necessario per l'elaborazione del dataset. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Unione veloce: tempo totale necessario per trasformare il dataset. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per diagnosticare i problemi "al momento" </p> </td> 
   <td colname="col2"> <p>Fai clic su <span class="uicontrol"> Stato</span> elaborazione &gt; <i>&lt;<span class="uicontrol"> nome</span>profilo&gt;</i> &gt; <span class="uicontrol"> A partire da ora</span> &gt; <span class="uicontrol"> Origini a partire</span>. </p> <p>La verifica del numero di volte per ciascuna origine può aiutarti a determinare quali fonti potrebbero avere un impatto negativo sul valore Complessivo A. È quindi possibile affrontare i problemi con quelle fonti particolari. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per stimare il tempo necessario per completare una query in esecuzione </p> </td> 
   <td colname="col2"> <p>Fate clic su <span class="uicontrol"> Motore</span>di esecuzione. </p> <p>La revisione del campo <span class="wintitle"> Data Sweep Time (Tempo</span> di sweep dati) fornisce una stima del tempo necessario per il completamento di una query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per elencare tutti i profili disponibili nel computer e i dettagli del relativo stato </p> </td> 
   <td colname="col2"> <p>Fate clic su <span class="uicontrol"> Profili</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare lo stato della replica </p> </td> 
   <td colname="col2"> <p>Fate clic su Stato <span class="uicontrol"></span>componente. </p> <p>Verificare lo stato del componente Replicate. Se Replica è in esecuzione, viene visualizzato OK. Se il componente Replica non è riuscito, viene visualizzato un messaggio di errore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare <span class="wintitle"> lo stato del server</span> di report per un <span class="keyword"> computer di report</span> che si connette al server Workbench dati </p> </td> 
   <td colname="col2"> <p>Fate clic su <span class="uicontrol"> Stato</span>del server di report. </p> <p>Questa sezione dell'interfaccia Stato <span class="wintitle"></span> dettagliato include una copia del file <span class="filepath"> Report Server.cfg</span> , informazioni sul numero di report in esecuzione (Sezione corrente) e informazioni sull'errore più recente (Ultimo errore). </p> <p>Per i passaggi necessari per modificare il file <span class="filepath"> Report Server.cfg</span> , vedere la Guida <i>al report</i>Workbench dati. </p> <p> <p>Nota: Se la sezione Stato <span class="wintitle"> del server di report non viene visualizzata nell'interfaccia Stato</span> <span class="wintitle"> dettagliato, potrebbe essere necessario configurare il server Workbench dati per visualizzare lo stato</span> del server di <span class="wintitle"></span>report. Per i passaggi, vedere la Guida <i>al rapporto Workbench</i>dati. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare le informazioni sull'utilizzo della memoria per Transform </p> </td> 
   <td colname="col2"> <p>Fate clic su <span class="uicontrol"> Stato</span> elaborazione &gt; <span class="uicontrol"> Trasforma</span>. </p> <p>Per ulteriori informazioni su Transform, vedere la Guida <i>all'installazione e all'amministrazione dei prodotti</i> server e la Guida alla configurazione dei <i>dataset</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per salvare l'interfaccia Stato <span class="wintitle"></span> dettagliato come file <span class="filepath"> *.cfg</span> che può essere aperto in un editor di testo come Notepad o distribuito ad altri </p> </td> 
   <td colname="col2"> <p>Fare clic con il pulsante destro del mouse sull’ <span class="uicontrol"> intestazione Stato</span> dettagliato e scegliere <span class="uicontrol"> Salva copia con nome</span>. </p> <p>Nota:  <p>Se si fa clic con il pulsante destro del mouse sull’ <span class="uicontrol"> intestazione Stato</span> dettagliato e si fa clic su <span class="uicontrol"> Salva</span> in nome <i></i>server/Stato/, l’interfaccia Stato <span class="wintitle"></span> dettagliato non funziona. Viene visualizzato il seguente messaggio di errore: </p> <p>Impossibile salvare /Status/. 403 Vietato </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare <span class="uicontrol"> le righe per la metrica Origine</span> registro </p> </td> 
   <td colname="col2"> <p>Se le righe per la metrica Origine registro devono essere riportate in Stato dettagliato, l'amministratore di Workbench dati deve definire l'ID origine registro e fornire un nome univoco in Elaborazione log.cfg del profilo personalizzato. </p> </td> 
  </tr> 
 </tbody> 
</table>

