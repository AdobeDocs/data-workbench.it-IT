---
description: Istruzioni per configurare le comunicazioni per Insight Server o Repeater (Ripetitore).
title: Impostazioni di configurazione delle comunicazioni
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
exl-id: a35788d1-de36-4350-a107-eee392e44503
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 3%

---

# Impostazioni di configurazione delle comunicazioni{#communications-configuration-settings}

{{eol}}

Istruzioni per configurare le comunicazioni per Insight Server o Repeater (Ripetitore).

Completa i parametri nel file seguente:

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>Prima di modificare eventuali parametri non elencati in questa tabella, contatta l’Adobe.

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> File di controllo di accesso </td> 
   <td colname="col2"> <p>Posizione della <span class="filepath"> Access Control.cfg </span> file. La posizione predefinita è la <span class="filepath"> Controllo degli accessi </span> nella cartella <span class="keyword"> Insight Server </span> o <span class="wintitle"> Ripetitore </span> directory di installazione. </p> <p>Esempio: <code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Directory dei log di accesso </td> 
   <td colname="col2"> <p>Cartella a cui si desidera mappare i registri di controllo. </p> <p>Esempio: <code>Access Log Directory = string: Audit\\</code> </p> <p> <p>Nota: Puoi mappare i registri di controllo su un’altra unità locale (ad esempio: <span class="filepath"> stringa: P:\\Audit\\ </span>), ma non mappare i registri di controllo su un'unità di rete. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Accesso dettagliato </td> 
   <td colname="col2"> Questo parametro può essere impostato su true o false. Viene utilizzato per abilitare e disabilitare il filtro del registro di controllo. Per garantire che ogni richiesta venga registrata, imposta il parametro su True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Interfaccia IP </td> 
   <td colname="col2"> <p>Indirizzo IP da utilizzare quando sono disponibili due schede di rete per l'accesso a due reti diverse. </p> <p>Esempio: <code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta </td> 
   <td colname="col2"> <p>Porta non protetta (HTTP) su cui <span class="keyword"> Insight Server </span> o <span class="wintitle"> Ripetitore </span> ascolta. La porta predefinita è 80. L'immissione di un valore pari a 0 disattiva le connessioni non sicure. </p> <p>Esempio: <code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cipers SSL </td> 
   <td colname="col2"> Alcuni ambienti richiedono una maggiore sicurezza delle comunicazioni rispetto ad altri. Se desideri utilizzare una specifica suite di crittografia SSL, puoi specificarla con questo parametro. <p>Esempio: <code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta SSL </td> 
   <td colname="col2"> <p>Porta sicura (tramite SSL) su cui il <span class="keyword"> Insight Server </span> o <span class="wintitle"> Ripetitore </span> ascolta. La porta predefinita è 443. Se si immette un valore pari a 0, le connessioni protette vengono disattivate. </p> <p>Esempio: <span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> Intestazione per le impostazioni del server di registrazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome cliente </td> 
   <td colname="col2"> <p>Nome cliente da visualizzare per i clienti non specificati negli avvisi amministrativi, come nell'esempio seguente: </p> <p>"Nessun dato ricevuto dal sensore XYZ per il cliente 'Non specificato' in 15." </p> <p>Esempio: <code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>Utilizzando l’esempio precedente, gli avvisi amministrativi per i clienti non specificati ora vengono letti come segue: </p> <p>"Nessun dato ricevuto dal sensore XYZ per il cliente ‘CompanyAB’ in 15." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Percorso locale = stringa: Registri\\ </p> </td> 
   <td colname="col2"> <p>Cartella in cui si desidera memorizzare i file di registro. </p> <p>Esempio: </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>Per accedere a questa cartella dal <span class="wintitle"> Server Files Manager </span>, la posizione specificata in questo parametro deve corrispondere alla posizione specificata nel parametro Log Paths nel <span class="filepath"> Log Processing.cfg </span> file. Per ulteriori informazioni sulla modifica della directory Logs in <span class="filepath"> Log Processing.cfg </span> file, vedere il capitolo File di configurazione dell'elaborazione del registro <i>Guida alla configurazione del set di dati</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Percorso locale = stringa: Audit\\ </p> </td> 
   <td colname="col2"> <p>Cartella a cui si desidera mappare i registri di controllo. </p> <p>Esempio: </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>Nota:  <p>Puoi mappare i registri di controllo su un’altra unità locale (ad esempio: <span class="filepath"> stringa: P:\\Audit\\ </span>), ma non mappare i registri di controllo su un'unità di rete. </p> <p>Per accedere a questa cartella dal <span class="wintitle"> Server Files Manager </span>, la posizione specificata in questo parametro deve corrispondere alla posizione specificata nel parametro della directory dei log di accesso in questo file. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>Questo parametro si applica solo a <span class="keyword"> Insight Server </span>. </p> <p>Per ulteriori informazioni su come specificare il server di normalizzazione centralizzato per il <span class="keyword"> Insight Server </span> cluster, vedere il capitolo File di configurazione dell'elaborazione del registro <i>Guida alla configurazione del set di dati</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = stringa: /ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>Questo parametro si applica solo a <span class="keyword"> Insight Server </span>. </p> <p>Consente di visualizzare <span class="keyword"> Rapporto </span> nell’interfaccia di stato dettagliato per <span class="keyword"> Insight Server </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
