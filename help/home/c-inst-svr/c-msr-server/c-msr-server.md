---
description: Identificare requisiti minimi e raccomandazioni per i componenti del server Workbench dati (precedentemente [!DNL Insight]) prima di pianificare e implementare il sistema.
title: Requisiti di sistema del server
uuid: c4487c76-03b9-4755-893b-555d451b1e69
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Requisiti di sistema del server{#server-system-requirements}

Identificare requisiti minimi e raccomandazioni per i componenti del server Workbench dati prima di pianificare e implementare il sistema.

## Requisiti DPU{#dpu-requirements}

L&#39;unità di elaborazione dati del server (DPU) è il componente principale di elaborazione dati di Workbench dati. Ascolta le connessioni di rete da Workbench dati, legge i dati di origine non elaborati dall&#39;Unità File Server (FSU) e utilizza notevoli risorse di calcolo e archiviazione.

### Capacità concessa in licenza {#section-71850e13783443798b3df9eb22cc63dc}

Per informazioni sulla capacità della licenza, fare riferimento alla Descrizione dei servizi nel contratto *di[!DNL Data Workbench (Insight)]Adobe* Service.

>[!NOTE]
>
>Per *MS System Center Endpoint Protection* nei server Windows 2012, questi eseguibili devono essere aggiunti ai processi ***esclusi:*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]
>



### Raccomandazioni e requisiti del sistema DPU {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe fornisce consigli su una progettazione di Workbench dati che soddisfa le esigenze aziendali. Tuttavia, le seguenti linee guida sono utili per selezionare il sistema operativo (OS) e l&#39;hardware, perché la natura ottimizzata del software DPU colloca requisiti specifici sulla piattaforma OS/hardware.

Se un singolo set di dati è limitato dalla capacità o dalla velocità di un singolo DPU, è possibile cluster. Ad esempio, supponiamo di disporre di tre copie con licenza del software DPU che vengono utilizzate insieme per eseguire più rapidamente un set di dati più grande. Poiché i dati sono suddivisi in modo uniforme tra i computer, la capacità concessa in licenza del dataset viene moltiplicata per tre. Inoltre, la velocità di elaborazione per riga diventa tre volte più veloce di un singolo DPU.

Per ottenere le migliori prestazioni dal vostro investimento in DPU, Adobe consiglia i seguenti componenti ad alte prestazioni descritti nella tabella seguente:

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
   <td colname="col1"> <p>Versione </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td> 
   <td colname="col3"> <p>Microsoft Windows Server 2012 x64 </p> <p> Microsoft Windows Server 2016 x64 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CPU </p> </td> 
   <td colname="col2"> <p>Consultate le raccomandazioni. </p> </td> 
   <td colname="col3"> Si consigliano processori Intel o AMD a 4 core+ di ultima generazione. Per ottenere prestazioni ottimali, 8-core; per un compromesso tra velocità e costi, si raccomanda di effettuare 4 core. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>8 GB </p> </td> 
   <td colname="col3"> <p>12 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Archiviazione dati di lavoro </p> </td> 
   <td colname="col2"> <p>1 TB+ di storage temporaneo logico totale. </p> <p>Accesso a bassa latenza al sottosistema del disco </p> </td> 
   <td colname="col3"> <p>Per l'archiviazione temporanea, Adobe consiglia: </p> 
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283"> 
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4 a 8) * (750 GB o superiore) HDD SATA (3,5" mandrino) </li> 
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6-10) * (300 GB o superiore) dischi rigidi SATA (mandrino da 2,5") </li> 
    </ul> <p>Devono essere configurati in un array JBOD. In alternativa, quando la capacità del disco lordo supera i 2 TB, è possibile utilizzare un array di volumi RAID1 a 2 dischi. Ad esempio, configurare sei dischi come una coppia RAID 1 da 3* (2*750 GB). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Archiviazione dati di sistema </p> </td> 
   <td colname="col2"> <p>Inoltre, Adobe richiede uno storage ad alta disponibilità di dimensioni ridotte (20 GB) per il sistema operativo, il software DPU e altri software del sistema. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hardware cluster </p> </td> 
   <td colname="col2"> <p>Consultate le raccomandazioni. </p> </td> 
   <td colname="col3"> <p>Utilizzare un insieme omogeneo di server. In un cluster DPU, il server più lento riduce le prestazioni dell'intero dataset. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prestazioni rete cluster </td> 
   <td colname="col2"> Connessione Ethernet Gigabit commutata o successiva. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

### Sottosistemi a disco alternativi {#section-6f984eabe8074759aa9deaf17e3a68b7}

Quando si considerano i sottosistemi di dischi alternativi per lo storage temporaneo, prendere in considerazione i seguenti fattori e linee guida:

* Il DPU richiede un sistema a disco ad alte prestazioni, pertanto la configurazione di un sottosistema a disco inadeguato può causare dei problemi di prestazioni.
* Il software DPU esegue la striping dei dati orientati alle prestazioni su un set di dischi JBOD. Non utilizzare RAID per aumentare la velocità.
* Adobe consiglia che il DPU disponga di una larghezza di banda aggregata di oltre 400 MB/s per i dischi.
* Le dimensioni di lettura medie sono molto elevate (2 MB+). Per questo motivo, i dischi SAS da 15.000 o 10.000 rpm spesso eseguono prestazioni un po&#39; migliori (o peggiori) rispetto ai dischi SATA a costi e capacità elevati.
* Evitare di utilizzare un&#39;architettura SAN. L&#39;esperienza dimostra che il costo per ottenere una SAN da eseguire ai livelli richiesti è in genere eccessivo.
* Il sottosistema del disco locale viene utilizzato come spazio di memoria virtuale; nessun dato viene perso in modo permanente a causa di un guasto del disco rigido, pertanto è consigliabile evitare sistemi costosi, lenti e ad alta disponibilità.

### Considerazioni sulla velocità {#section-01330be232894e08a526d8d82b7c4eb2}

Adobe non è in grado di fornire una garanzia o una rappresentazione in merito alla velocità con cui i dati vengono elaborati da un workbench dati configurato, in quanto diversi fattori influiscono sulla velocità di elaborazione dei dati, compresi, tra l&#39;altro, i seguenti:

* Numero di righe di dati
* Numero di dimensioni (colonne) dei dati
* Numero e complessità dei passaggi di elaborazione personalizzati
* Utilizzo del clustering
* Velocità dell&#39;hardware

## Requisiti delle unità del file server{#file-server-unit-requirements}

L&#39;unità FSU (File Serving Unit) del server è il componente principale per l&#39;archiviazione e la gestione dei dati di Workbench dati. L&#39;FSU funge da file server per i dati di origine non elaborati al DPU e, se del caso, coordina il clustering delle DPU. Ogni FSU è autorizzato a fornire dati di origine fino a cinque (5) DPU.

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
   <td colname="col2"> <p>Questi requisiti sono gli stessi del DPU. Tuttavia, per l'FSU, Adobe consiglia di utilizzare i requisiti minimi invece di seguire le raccomandazioni. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sistema del disco </p> <p>L'FSU richiede uno storage ridondante e altamente disponibile per grandi volumi di dati. Adobe collaborerà con voi per determinare i vostri requisiti esatti. </p> </td> 
   <td colname="col1"> <p>Adobe consiglia: </p> 
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539"> 
     <li id="li_F98750D509D640C68885D53FC691ED43">(12 o più) * (750 GB o superiore) dischi rigidi SATA in una configurazione RAID 5/6. </li> 
     <li id="li_3F84F63F9541476987015C27FDE8251B">Connessione SAN ad alte prestazioni che supporta una larghezza di banda prolungata di 100 MB/s+. </li> 
    </ul> <p>Poiché l'FSU contiene i dati di origine non elaborati, qualsiasi perdita sarebbe irrecuperabile e Adobe suggerisce di eseguire regolarmente il backup di tali dati. </p> </td> 
   <td colname="col2"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prestazioni della rete </p> </td> 
   <td colname="col2"> <p>Adobe richiede connessioni Ethernet Gigabit commutabili tra FSU e DPU che collaborano. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
 </tbody> 
</table>

## Requisiti del sensore{#sensor-requirements}

Data Workbench Sensor raccoglie i dati degli eventi dai server Web, applicazioni e di raccolta dati da trasmettere a qualsiasi server. [!DNL Sensor’s] la strumentazione assicura una misurazione accurata e coerente degli eventi che si verificano nel canale Internet. [!DNL Sensor] supporta molte combinazioni di software server Web e sistema operativo.

### Consigli del sistema di sensori {#section-0a981c3a47b644c1a1a56974ba033b9c}

La tabella seguente descrive le raccomandazioni di sistema per [!DNL Sensor]:

<table id="table_A132E06D6B8146C1B199B82464EA0898"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funzioni  </th> 
   <th colname="col2" class="entry"> Consigliato </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Archiviazione su disco </p> </td> 
   <td colname="col2"> <p>512 MB minimo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>32 MB di RAM devono essere disponibili per <span class="wintitle"> Sensor </span> sul computer HTTP o su un altro server host. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prestazioni della rete </p> </td> 
   <td colname="col2"> <p>1 Mbps o una connessione di rete superiore a un server ripetitore o a un server workbench <span class="keyword"> dati </span>. <span class="wintitle"> Il sensore </span> consuma generalmente una larghezza di banda molto inferiore a 1 (1) Mbps. I consulenti Adobe potranno aiutarti a stimare la quantità effettiva di larghezza di banda che sarà necessaria su base regolare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Porte di rete e firewall </p> </td> 
   <td colname="col2"> <p> <span class="wintitle"> Il sensore </span> si connette al server del workbench <span class="keyword"> dati </span> utilizzando HTTPS (generalmente porta 443, anche se configurabile) o HTTP (in genere porta 80, anche se configurabile). </p> <p>La porta appropriata su qualsiasi firewall che si trova tra un <span class="wintitle"> sensore </span> e il server workbench dati di destinazione <span class="keyword"> o un server ripetitore deve essere aperta solo tra il computer </span> Sensor <span class="wintitle"> che ospita il sistema e il server </span> workbench dati <span class="keyword"> o il server ripetitore prima di avviare il processo di installazione </span> Sensor <span class="wintitle"> </span> . <span class="wintitle"> Sensor </span> crea una connessione HTTP o HTTP unidirezionale a un server workbench <span class="keyword"> dati </span> o a un server ripetitore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sistemi di gestione della rete </p> </td> 
   <td colname="col2"> <p>I sistemi di gestione della rete esistenti devono monitorare lo stato dell'hardware del computer sottostante (ad esempio, spazio su disco, servizio di rete) e la connettività di rete, nonché il registro eventi di Windows o il syslog UNIX. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sincronizzazione ora server </p> </td> 
   <td colname="col2"> <p>Assicurarsi che l'ora del sistema del computer sia sincronizzata in modo continuo su tutti i computer che ospitano un <span class="wintitle"> sensore </span>. Le applicazioni server Web e i computer monitorati da <span class="wintitle"> Sensor </span> devono avere tempi di sistema sincronizzati affinché i dati dell'evento raccolti da loro siano precisi. Fare riferimento alla documentazione del sistema operativo in uso per i passaggi necessari per sincronizzare gli orari del sistema su base continuativa con NTP o con altre funzionalità di sincronizzazione dell'ora. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilizzo nome DNS </p> </td> 
   <td colname="col2"> <p>Adobe consiglia ai <span class="wintitle"> sensori di </span> utilizzare un nome DNS (anziché un indirizzo IP) per risolvere l'indirizzo di rete di un server workbench <span class="keyword"> dati </span> o di un server ripetitore. Quando un <span class="wintitle"> sensore </span> utilizza un nome DNS, il file host DNS o locale del server Web host deve essere configurato per risolvere il nome del server workbench <span class="keyword"> dati </span> o del server ripetitore. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Software del server di supporto {#section-d6071706539f49d9a861d87b98e6f382}

Nella tabella seguente sono elencate le combinazioni più comuni che [!DNL Sensor] supportano:

<table id="table_99EA23BBC1A148B49643F4B5E4341C08"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Software Web Server </th> 
   <th colname="col2" class="entry"> Versione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Apache Server / IBM HTTP Server 2.2 </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 o versione successiva; RedHat Enterprise Linux 6.x o versione successiva; Sun Solaris 8.x o successivo; IBM AIX 5.1x o versione successiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apache Server 2.4 </p> </td> 
   <td colname="col2"> <p>RedHat Enterprise Linux 6.x o versione successiva </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Microsoft IIS </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 o versione successiva </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server applicazioni Java (Tomcat, JBoss, iPlanet, Weblogic) </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 o versione successiva; RedHat Enterprise Linux 6.x o versione successiva; Sun Solaris 8.x o successivo; IBM AIX 5.1x o versione successiva. </p> </td> 
  </tr> 
 </tbody> 
</table>

Per altre combinazioni di server e sistemi operativi, consulta Adobe sulla disponibilità. Non tutte le funzioni di [!DNL Sensor] sono disponibili con tutte le combinazioni di web/server applicazioni e sistema operativo. Per ulteriori informazioni su particolari [!DNL Sensor] release, contattate il supporto Adobe.

## Requisiti del server di report{#report-server-requirements}

Il server di report Workbench dati è il componente che consente l&#39;output di report pianificati. I rapporti che vengono generati possono essere sotto forma di immagini .PNG o fogli di calcolo .XLS inseriti in un file system o come e-mail. I requisiti hardware sono identici al client [Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html)dati.

Esistono i seguenti requisiti per [!DNL report server]:

* Accesso al file system per l&#39;output di dati (condivisione di rete o unità locale).
* Accesso al server SMTP configurato.
* Microsoft Excel 2003 o versione successiva installato sul [!DNL report] server. Per ulteriori informazioni, vedere [Considerazioni sull&#39;automazione di Office](http://support.microsoft.com/kb/257757) lato server.

## Gestione della rete{#network-management}

Adobe consiglia ai sistemi di gestione della rete esistenti di monitorare l&#39;hardware e la rete su cui si basa la piattaforma Workbench dati.

Inoltre, Adobe consiglia di monitorare i registri eventi di Windows degli FSU e DPU, scritti quando si verifica un errore.

>[!NOTE]
>
>Qualsiasi sistema di storage in rete che ospita file di registro deve fornire almeno 10 MB per DPU di larghezza di banda sostenuta.

## Disponibilità dei dati{#data-availability}

È una pratica normale e obbligatoria per un DPU server elaborare ed elaborare i dati in un dataset nuovo o aggiornato.

Ciò può verificarsi a causa di modifiche alla configurazione, modifiche all&#39;origine dati, modifiche hardware, configurazione non corretta, guasti hardware, guasti software, guasti elettrici e così via. Quando si verifica tale elaborazione o rielaborazione, tutti i dataset e i dati di sistema devono essere immediatamente disponibili per i componenti DPU e FSU. Il mancato rispetto di questo requisito può comportare tempi di inattività significativi e superflui del sistema.

## Problemi di rete DPU e FSU{#dpu-and-fsu-network-issues}

Considerazioni da tenere a mente quando si utilizzano le reti DPU e FSU.

* Per la distribuzione di file di registro in rete, qualsiasi sistema di storage in rete che ospita file di registro deve fornire almeno 10 MB per DPU di larghezza di banda sostenuta.
* DPU, FSU e Workbench dati comunicano tra loro in modo bidirezionale tramite HTTP o HTTPS sulla porta 80 o 443 (per impostazione predefinita; le porte possono essere configurate in alternativa).
* Workbench dati [!DNL Sensor(s)] deve essere in grado di connettersi (unidirezionale) ai server.
* Per consentire al DPU di inviare messaggi di avviso tramite SMTP, deve essere in grado di contattare il server SMTP configurato.
* Adobe consiglia di assegnare a FSU e DPU nomi di rete come FSU01.CLIENT.COM per evitare la riconfigurazione in caso di modifica dell&#39;indirizzo IP.