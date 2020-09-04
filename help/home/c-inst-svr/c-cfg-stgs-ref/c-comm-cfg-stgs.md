---
description: Istruzioni per configurare le comunicazioni per Insight Server o Ripetitore.
solution: Insight
title: Impostazioni di configurazione delle comunicazioni
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
translation-type: tm+mt
source-git-commit: 2ed16fa0d447426c4de863e502792bfb292765cc
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 3%

---


# Impostazioni di configurazione delle comunicazioni{#communications-configuration-settings}

Istruzioni per configurare le comunicazioni per Insight Server o Ripetitore.

Completa i parametri nel file seguente:

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>Prima di modificare i parametri non elencati in questa tabella, contattate  Adobe.

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
   <td colname="col2"> <p>Posizione del file <span class="filepath"> Access Control.cfg </span> . Il percorso predefinito è la <span class="filepath"> cartella Controllo </span> accesso all'interno della directory di installazione di <span class="keyword"> Insight Server </span> o <span class="wintitle"> Repeat </span> . </p> <p>Esempio: <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Directory registro di accesso </td> 
   <td colname="col2"> <p>Cartella a cui si desidera mappare i registri di controllo. </p> <p>Esempio: <filepath></filepath> </p> <p> <p>Nota:  È possibile mappare i registri di controllo su un'altra unità locale (ad esempio: <span class="filepath"> stringa: P:\\Audit\\ </span>), ma non mappare i registri di controllo su un'unità di rete. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Accesso dettagliato </td> 
   <td colname="col2"> Questo parametro può essere impostato su true o false. Viene utilizzato per abilitare e disabilitare il filtro del registro di controllo. Per garantire che ogni richiesta venga registrata, impostate il parametro su True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Interfaccia IP </td> 
   <td colname="col2"> <p>Indirizzo IP da utilizzare quando sono disponibili due schede di rete per l'accesso a due reti diverse. </p> <p>Esempio: I <filepath></filepath><i>&lt; <span class="filepath"> Indirizzo IP </span>&gt;</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta </td> 
   <td colname="col2"> <p>Porta non sicura (HTTP) sulla quale <span class="keyword"> Insight Server </span> o <span class="wintitle"> Ripetitore </span> ascolta. La porta predefinita è 80. Se si inserisce un valore pari a 0, le connessioni non sicure vengono disattivate. </p> <p>Esempio: <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cipher SSL </td> 
   <td colname="col2"> Alcuni ambienti richiedono una maggiore sicurezza delle comunicazioni rispetto ad altri. Se desiderate utilizzare una suite di crittografia SSL specifica, potete specificarla con questo parametro. <p>Esempio: <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta SSL </td> 
   <td colname="col2"> <p>Porta protetta (tramite SSL) su cui <span class="keyword"> Insight Server </span> o <span class="wintitle"> Ripetitore </span> ascolta. La porta predefinita è 443. Se si immette un valore pari a 0, vengono disattivate le connessioni protette. </p> <p>Esempio: <span class="filepath"></span> </p> <filepath></filepath> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> Intestazione per le impostazioni del server di registrazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome cliente </td> 
   <td colname="col2"> <p>Il nome del cliente verrà visualizzato per i clienti non specificati negli avvisi amministrativi, come nell'esempio seguente: </p> <p>"Nessun dato ricevuto dal sensore XYZ per il cliente 'Non specificato' in 15." </p> <p>Esempio: <code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>Utilizzando l'esempio precedente, gli avvisi amministrativi per i clienti non specificati ora leggeranno come segue: </p> <p>"Nessun dato ricevuto dal sensore XYZ per il cliente ‘CompanyAB’ in 15." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Percorso locale = stringa: Registri\\ </p> </td> 
   <td colname="col2"> <p>Cartella in cui si desidera archiviare i file di registro. </p> <p>Esempio: </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>Per poter accedere a questa cartella da <span class="wintitle"> Server Files Manager </span>, la posizione specificata in questo parametro deve corrispondere alla posizione specificata nel parametro Log Paths nel file <span class="filepath"> Log Processing.cfg </span> . Per ulteriori informazioni sulla modifica della directory Logs nel file <span class="filepath"> Log Processing.cfg </span> , vedere il capitolo File di configurazione dell'elaborazione del registro della Guida alla configurazione del set di <i>dati</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Percorso locale = stringa: Audit\ </p> </td> 
   <td colname="col2"> <p>Cartella a cui si desidera mappare i registri di controllo. </p> <p>Esempio: </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>Nota:  <p>È possibile mappare i registri di controllo su un'altra unità locale (ad esempio: <span class="filepath"> stringa: P:\\Audit\\ </span>), ma non mappare i registri di controllo su un'unità di rete. </p> <p>Per poter accedere a questa cartella da <span class="wintitle"> Server Files Manager </span>, la posizione specificata in questo parametro deve corrispondere alla posizione specificata nel parametro della directory di registro di accesso in questo file. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>Questo parametro si applica solo a <span class="keyword"> Insight Server </span>. </p> <p>Per ulteriori informazioni sulla specifica del server di normalizzazione centralizzato per il <span class="keyword"> cluster Insight Server, vedere il capitolo File di configurazione dell'elaborazione del registro della Guida alla configurazione del set di </span> dati <i></i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = stringa: /ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>Questo parametro si applica solo a <span class="keyword"> Insight Server </span>. </p> <p>Consente di visualizzare <span class="keyword"> lo stato del </span> report nell'interfaccia Stato dettagliato per <span class="keyword"> Insight Server </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
