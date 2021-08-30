---
description: Identifica i requisiti minimi e le raccomandazioni per i componenti server Data Workbench (precedentemente [!DNL Insight]) prima di pianificare e implementare il sistema.
title: Requisiti di sistema del server
uuid: c4487c76-03b9-4755-893b-555d451b1e69
exl-id: 6dd78331-8370-400e-b580-9b9bad13e62c
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# Requisiti di sistema del server{#server-system-requirements}

Identifica i requisiti minimi e le raccomandazioni per i componenti del server Data Workbench prima di pianificare e implementare il sistema.

## Requisiti DPU{#dpu-requirements}

L’unità di elaborazione dati del server (DPU) è il componente principale di elaborazione dati di Data Workbench. Ascolta le connessioni di rete da Data Workbench, legge i dati di origine non elaborati dall&#39;unità File Server (FSU) e utilizza risorse di calcolo e storage sostanziali.

### Capacità concessa in licenza {#section-71850e13783443798b3df9eb22cc63dc}

Per informazioni sulla capacità della licenza, fare riferimento alla descrizione dei servizi nell’ *Adobe [!DNL Data Workbench (Insight)] Contratto di servizio*.

>[!NOTE]
>
>Per *MS System Center Endpoint Protection* nei server Windows 2012, questi eseguibili devono essere aggiunti ai ***Processi esclusi:*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]

>


### Requisiti e Recommendations di sistema DPU {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe fornisce consigli su una progettazione Data Workbench che soddisfa le tue esigenze aziendali. Tuttavia, le seguenti linee guida sono utili quando si selezionano il sistema operativo (OS) e l&#39;hardware, in quanto la natura ottimizzata del software DPU pone requisiti specifici sulla piattaforma OS/hardware.

Se un singolo set di dati è limitato dalla capacità o dalla velocità di una singola DPU, puoi cluster. Ad esempio, supponiamo di avere tre copie con licenza del software DPU che vengono utilizzate insieme per eseguire più rapidamente un set di dati più grande. Poiché i dati sono suddivisi in modo uniforme tra le macchine, la capacità concessa in licenza del set di dati viene moltiplicata per tre. Inoltre, la velocità di elaborazione per riga diventa tre volte più veloce di una singola DPU.

Per ottenere le migliori prestazioni dal tuo investimento DPU, Adobe consiglia i seguenti componenti ad alte prestazioni descritti nella tabella seguente:

<table id="table_DA0A60CFBA7D4EF98B5ED5A3D8D6777B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Obbligatorio </th> 
   <th colname="col3" class="entry"> Consigliato </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sistema operativo </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td> 
   <td colname="col3"> <p>Microsoft Windows Server 2012 x64 </p> <p> Microsoft Windows Server 2016 x64 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CPU </p> </td> 
   <td colname="col2"> <p>Consulta le raccomandazioni. </p> </td> 
   <td colname="col3"> Si consiglia di utilizzare processori Intel o AMD a 4 core+ di ultima generazione. Per prestazioni ottimali, 8 core; per un compromesso tra velocità e costi, si raccomanda l'uso di 4 core. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>8 GB </p> </td> 
   <td colname="col3"> <p>12 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Archiviazione dati di lavoro </p> </td> 
   <td colname="col2"> <p>1 TB+ di storage temporaneo logico totale. </p> <p>Accesso a bassa latenza al sottosistema del disco </p> </td> 
   <td colname="col3"> <p>Per l'archiviazione temporanea, l'Adobe raccomanda: </p> 
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283"> 
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(da 4 a 8) * (750 GB o superiore) dischi rigidi SATA (mandrino da 3,5") </li> 
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(da 6 a 10) * (300 GB o superiore) dischi rigidi SATA (mandrino da 2,5") </li> 
    </ul> <p>Questi devono essere configurati in un array JBOD. In alternativa, quando la capacità del disco lordo supera i 2 TB, è possibile utilizzare un array di volumi RAID1 a 2 dischi. Ad esempio, configurare sei dischi come una coppia RAID 1 da 3*(2*750 GB). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Archiviazione dati di sistema </p> </td> 
   <td colname="col2"> <p>Inoltre, l'Adobe richiede uno storage ad alta disponibilità di dimensioni modeste (20 GB) per il sistema operativo, il software DPU e altri software di sistema. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hardware di clustering </p> </td> 
   <td colname="col2"> <p>Consulta le raccomandazioni. </p> </td> 
   <td colname="col3"> <p>Utilizzare un insieme omogeneo di server. In un cluster DPU, il server più lento riduce le prestazioni dell'intero set di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prestazioni di rete del clustering </td> 
   <td colname="col2"> Connessione Ethernet Gigabit commutata o successiva. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

### Sottosistemi a disco alternativi {#section-6f984eabe8074759aa9deaf17e3a68b7}

Quando si considerano i sottosistemi di dischi alternativi per lo storage temporaneo, tenere conto dei fattori e delle linee guida seguenti:

* La DPU richiede un sistema a disco ad alte prestazioni, pertanto la configurazione di un sottosistema a disco inadeguato può causare problemi di prestazioni.
* Il software DPU esegue il proprio striping dati orientato alle prestazioni su un set di dischi JBOD. Non utilizzare RAID per aumentare la velocità.
* L&#39;Adobe consiglia che la DPU abbia una larghezza di banda sostenuta aggregata di oltre 400 MB/s sui dischi.
* Le dimensioni medie di lettura sono molto elevate (2 MB+). Per questo motivo, i dischi SAS da 15.000 o 10.000 offrono spesso prestazioni un po&#39; migliori (o peggiori) dei dischi SATA a costi e capacità elevati.
* Evitare di utilizzare un&#39;architettura SAN. L&#39;esperienza dimostra che il costo per ottenere una SAN da eseguire ai livelli richiesti è in genere estremo.
* Il sottosistema del disco locale viene utilizzato come spazio di memoria virtuale: nessun dato viene perso in modo permanente in caso di guasto all&#39;unità disco rigido, pertanto è consigliabile evitare sistemi costosi, più lenti e ad alta disponibilità.

### Considerazioni sulla velocità {#section-01330be232894e08a526d8d82b7c4eb2}

L&#39;Adobe non può fornire una garanzia o una rappresentazione della velocità di elaborazione dei dati da parte di una Data Workbench configurata, in quanto diversi fattori influiscono sulla velocità di elaborazione dei dati, compresi, tra l&#39;altro, i seguenti elementi:

* Numero di righe di dati
* Numero di dimensioni (colonne) dei dati
* Numero e complessità dei passaggi di elaborazione personalizzati
* Utilizzo del clustering
* Velocità dell&#39;hardware

## Requisiti delle unità del file server{#file-server-unit-requirements}

L&#39;unità FSU (File Serving Unit) del server è il componente principale di archiviazione e gestione dei dati della Data Workbench. La FSU agisce come file server per i dati di origine non elaborati alla DPU e, se del caso, coordina il clustering delle DPU. Ogni FSU è autorizzata a fornire dati di origine fino a cinque (5) DPU.

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componenti FSU </th> 
   <th colname="col2" class="entry"> Consigli </th> 
   <th colname="col3" class="entry"> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sistema operativo, CPU, RAM </p> </td> 
   <td colname="col2"> <p>Questi requisiti sono gli stessi della DPU. Tuttavia, per la FSU, l'Adobe raccomanda di utilizzare i requisiti minimi anziché seguire le raccomandazioni. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sistema a disco </p> <p>La FSU richiede uno storage ridondante e altamente disponibile per grandi volumi di dati. Adobe collaborerà con te per determinare i tuoi requisiti esatti. </p> </td> 
   <td colname="col1"> <p>L’Adobe raccomanda: </p> 
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539"> 
     <li id="li_F98750D509D640C68885D53FC691ED43">(12 o più) * (750 GB o superiore) dischi rigidi SATA in una configurazione RAID 5/6. </li> 
     <li id="li_3F84F63F9541476987015C27FDE8251B">Connessione SAN ad alte prestazioni che supporta una larghezza di banda prolungata di 100 MB/s+. </li> 
    </ul> <p>Poiché la FSU detiene i dati di origine non elaborati, qualsiasi perdita sarebbe irrecuperabile e l'Adobe suggerisce di effettuare regolarmente il backup di tali dati. </p> </td> 
   <td colname="col2"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prestazioni di rete </p> </td> 
   <td colname="col2"> <p>L'Adobe richiede connessioni Ethernet Gigabit commutate tra FSU e DPU che lavorano insieme. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
 </tbody> 
</table>

## Requisiti del sensore{#sensor-requirements}

Data Workbench Sensor raccoglie i dati degli eventi dai server web, applicativi e di raccolta dati per la trasmissione a qualsiasi server. [!DNL Sensor’s] La strumentazione assicura una misurazione accurata e coerente degli eventi che si verificano nel canale Internet. [!DNL Sensor] supporta molte combinazioni di software server web e sistema operativo.

### Recommendations del sistema di sensori {#section-0a981c3a47b644c1a1a56974ba033b9c}

La tabella seguente descrive le raccomandazioni di sistema per [!DNL Sensor]:

<table id="table_A132E06D6B8146C1B199B82464EA0898"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funzioni </th> 
   <th colname="col2" class="entry"> Consigliato </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Archiviazione su disco </p> </td> 
   <td colname="col2"> <p>minimo 512 MB. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>32 MB di RAM devono essere disponibili per <span class="wintitle"> Sensor </span> su HTTP o su un altro computer server che è il proprio host. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prestazioni di rete </p> </td> 
   <td colname="col2"> <p>1 Mbps o una connessione di rete superiore a un server Repeater o a <span class="keyword"> server di Data Workbench </span>. <span class="wintitle"> Il sensore  </span> consuma generalmente una larghezza di banda molto inferiore a 1 Mbps. I tuoi consulenti di Adobe ti aiuteranno a stimare la quantità effettiva di larghezza di banda che sarebbe necessaria su base regolare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Porte di rete e firewall </p> </td> 
   <td colname="col2"> <p> <span class="wintitle"> Il sensore  </span> si connette al server di  <span class="keyword"> Data Workbench  </span> utilizzando HTTPS (generalmente porta 443, anche se configurabile) o HTTP (in genere porta 80, anche se configurabile). </p> <p>La porta appropriata su qualsiasi firewall presente tra un <span class="wintitle"> Sensor </span> e il server di Data Workbench <span class="keyword"> di destinazione </span> o un server Repeater deve essere aperta solo tra il rispettivo <span class="wintitle"> Sensor </span> e il <span class="keyword"> server di Data Workbench </span> o server Repeater prima di avviare l’ <span class="wintitle"> Sensor </span> processo. <span class="wintitle"> Sensor  </span> effettua una connessione unidirezionale HTTPS o HTTP a un server  <span class="keyword"> di Data Workbench  </span> o a un server ripetitore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sistemi di gestione della rete </p> </td> 
   <td colname="col2"> <p>I sistemi di gestione di rete esistenti devono monitorare lo stato dell'hardware del computer sottostante (ad esempio, spazio su disco, servizio di rete) e la connettività di rete, nonché il registro eventi di Windows o il registro di sistema UNIX. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sincronizzazione dell'ora del server </p> </td> 
   <td colname="col2"> <p>Assicurati che l'ora del sistema del computer sia continuamente sincronizzata su ogni computer che ospita un <span class="wintitle"> sensore </span>. Le applicazioni server Web e i computer monitorati da <span class="wintitle"> Sensor </span> devono disporre di tempi di sistema sincronizzati affinché i dati dell'evento raccolti da tali applicazioni siano accurati. Consulta la documentazione del tuo sistema operativo per conoscere i passaggi necessari per sincronizzare gli orari del sistema su base continuativa con NTP o altre funzionalità di sincronizzazione dei tempi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilizzo del nome DNS </p> </td> 
   <td colname="col2"> <p>L’Adobe consiglia a <span class="wintitle"> Sensor </span> di utilizzare un nome DNS (anziché un indirizzo IP) per risolvere l’indirizzo di rete di un server di Data Workbench <span class="keyword"> o server ripetitore </span>. Quando un <span class="wintitle"> Sensor </span> utilizza un nome DNS, è necessario configurare il file host DNS o locali del server web host per risolvere il nome del server <span class="keyword"> di Data Workbench </span> o del server di ripetizione. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Software del server di supporto {#section-d6071706539f49d9a861d87b98e6f382}

Nella tabella seguente sono elencate le combinazioni più comuni supportate da [!DNL Sensor]:

<table id="table_99EA23BBC1A148B49643F4B5E4341C08"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Software Web Server </th> 
   <th colname="col2" class="entry"> Sistema operativo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Apache Server / IBM HTTP Server 2.2 </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 o versione successiva; RedHat Enterprise Linux 6.x o successivo; Sun Solaris 8.x o successivo; IBM AIX 5.1x o versione successiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apache Server 2.4 </p> </td> 
   <td colname="col2"> <p>RedHat Enterprise Linux 6.x o successivo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Microsoft IIS </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 o versione successiva </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server applicativi Java (Tomcat, JBoss, iPlanet, Weblogic) </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 o versione successiva; RedHat Enterprise Linux 6.x o successivo; Sun Solaris 8.x o successivo; IBM AIX 5.1x o versione successiva. </p> </td> 
  </tr> 
 </tbody> 
</table>

Per altre combinazioni di server e sistemi operativi, consultare l&#39;Adobe relativo alla disponibilità. Non tutte le funzioni di [!DNL Sensor] sono disponibili con tutte le combinazioni di server web/applicazioni e sistema operativo. Per ulteriori informazioni su particolari versioni di [!DNL Sensor], contatta il supporto Adobe.

## Requisiti del server di rapporto{#report-server-requirements}

Il server di rapporto di Data Workbench è il componente che consente l’output di rapporti pianificati. I rapporti che vengono generati possono essere sotto forma di immagini .PNG o fogli di calcolo .XLS inseriti in un file system o come e-mail. I relativi requisiti hardware sono identici a [Data Workbench Client](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=it).

Per [!DNL report server] esistono i seguenti requisiti:

* Accesso al file system per l&#39;output dei dati (condivisione di rete o unità locale).
* Accesso al server SMTP configurato.
* Microsoft Excel 2003 o versione successiva installato sul server [!DNL report]. Per ulteriori informazioni, vedere [Considerazioni sull&#39;automazione lato server di Office](http://support.microsoft.com/kb/257757).

## Gestione della rete{#network-management}

L&#39;Adobe consiglia ai sistemi di gestione della rete esistenti di monitorare l&#39;hardware e la rete su cui si basa la piattaforma Data Workbench.

Inoltre, Adobe consiglia di monitorare i registri eventi di Windows delle FSU e delle DPU, che vengono scritti quando si verifica un errore.

>[!NOTE]
>
>Qualsiasi sistema di storage in rete che ospita file di log deve fornire almeno 10 MB per DPU di larghezza di banda sostenuta.

## Disponibilità dei dati{#data-availability}

È una pratica normale e obbligatoria per una DPU del server elaborare e rielaborare i dati in set di dati nuovi o aggiornati.

Ciò può verificarsi a causa di modifiche alla configurazione, modifiche all’origine dati, modifiche hardware, configurazione non appropriata, guasti hardware, guasti software, interruzioni di corrente e così via. Quando si verifica tale elaborazione o rielaborazione, tutti i set di dati e i dati di sistema devono essere immediatamente disponibili per i componenti DPU e FSU. Il mancato rispetto di questo requisito può comportare tempi di inattività significativi e non necessari del sistema.

## Problemi di rete DPU e FSU{#dpu-and-fsu-network-issues}

Considerazioni da tenere a mente quando si lavora con reti DPU e FSU.

* Per la distribuzione dei file di log in rete, qualsiasi sistema di storage in rete che ospita file di log deve fornire almeno 10 MB per DPU di larghezza di banda sostenuta.
* DPU, FSU e Data Workbench intercomunicano in modo bidirezionale tramite HTTP o HTTPS sulla porta 80 o 443 (per impostazione predefinita; le porte possono essere configurate in alternativa).
* La Data Workbench [!DNL Sensor(s)] deve essere in grado di connettersi (unidirezionale) ai server.
* Per consentire al DPU di inviare messaggi di avviso tramite SMTP, deve essere in grado di contattare il server SMTP configurato.
* L&#39;Adobe consiglia di assegnare alle FSU e alle DPU nomi di rete come FSU01.CLIENT.COM per evitare la riconfigurazione in caso di modifica dell&#39;indirizzo IP.
