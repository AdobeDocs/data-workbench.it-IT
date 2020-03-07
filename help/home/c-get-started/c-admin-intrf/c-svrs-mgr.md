---
description: Lo strumento principale utilizzato dagli amministratori di sistema è Server Manager.
solution: Analytics
title: Server Manager
topic: Data workbench
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# Server Manager{#servers-manager}

Lo strumento principale utilizzato dagli amministratori di sistema è Server Manager.

È l&#39;interfaccia principale per determinare lo stato complessivo del sistema e per eseguire le funzioni di configurazione del sistema, gestione dei file e monitoraggio degli errori.

Server Manager visualizza un punto (nodo) colorato per ciascun server Workbench dati e per [!DNL Sensor] l&#39;installazione nel sistema e fornisce lo stato del sistema a colpo d&#39;occhio per ogni installazione. Visualizza inoltre un nodo per l&#39;installazione di Workbench dati.

I nodi verdi rappresentano connessioni attive, i nodi rossi rappresentano connessioni disattivate o altrimenti inaccessibili, mentre i nodi grigi rappresentano connessioni con stati non determinati.

![](assets/vis_SysStat_RedGreenDots.png)

Facendo clic con il pulsante destro del mouse su un nodo, vengono visualizzate le informazioni sul componente che si collega e viene fornito l’accesso a tutti i menu correlati.

Le tabelle seguenti descrivono le informazioni fornite quando si fa clic con il pulsante destro del mouse su un nodo per Workbench dati, il server Workbench dati (incluso un server Workbench dati master in un cluster) o [!DNL Sensor].

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Prodotto </p> </td> 
   <td colname="col2"> <p>Nome prodotto, versione e numero build. </p> <p>Esempio: Workbench dati 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indirizzo </p> </td> 
   <td colname="col2"> <p>Indirizzo IP del computer Workbench dati. </p> <p>Esempio: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configura </p> </td> 
   <td colname="col2"> <p>Un collegamento al file di configurazione del workbench <span class="keyword"> dati </span> . Fare clic su <span class="uicontrol"> Configura </span> &gt; <span class="uicontrol"> Insight.cfg </span> per visualizzare la finestra di configurazione Workbench dati. Eventuali modifiche apportate e salvate in questa finestra vengono riportate nel file <span class="filepath"> Insight.cfg </span> nella directory di installazione di Workbench dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prodotto </p> </td> 
   <td colname="col2"> <p>Nome prodotto, versione e numero build. </p> <p>Esempio: Server Workbench dati 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Nome comune del computer server Workbench dati. </p> <p>Esempio: <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indirizzo </p> </td> 
   <td colname="col2"> <p>Indirizzo IP o nome di dominio completo del server come configurato nel file Indirizzi del computer e nel parametro Posizione di rete nel file <span class="filepath"> Insight.cfg </span> . </p> <p>Esempio: 100.0.0.1 </p> <p>Per informazioni sul file Indirizzi, vedere la Guida all'installazione e all'amministrazione dei prodotti <i>server</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stato </p> </td> 
   <td colname="col2"> <p>Stato corrente del server Workbench dati. Questo campo viene visualizzato OK quando il server Workbench dati è in esecuzione normalmente. Se si è verificato un errore e il nodo del server Workbench dati è rosso, il campo visualizza l'errore (ad esempio, "403 Vibidden"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stato dettagliato </p> </td> 
   <td colname="col2"> <p>Collegamento all'interfaccia del server <span class="keyword"> Workbench dati </span> <span class="wintitle"> Stato dettagliato </span> , utile per la risoluzione di errori o altri problemi riscontrati con il server Workbench dati. </p> <p>Per ulteriori informazioni, consulta <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> L’interfaccia</a>Stato dettagliata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desktop remoto </p> </td> 
   <td colname="col2"> <p>Apre una <span class="wintitle"> sessione Desktop remoto </span> nel computer server Workbench dati. </p> <p>Per ulteriori informazioni, vedere <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> L'opzione Desktop remoto </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File server </p> </td> 
   <td colname="col2"> <p>Un collegamento a <span class="wintitle"> Server Files Manager </span>, che visualizza le directory e i file nella directory di installazione del server Workbench dati. </p> <p>Per ulteriori informazioni, vedere <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Gestione file server </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Monitor server </p> </td> 
   <td colname="col2"> <p>Un collegamento all'interfaccia <span class="wintitle"> Server Monitor </span> , utile per la risoluzione dei problemi o per il tracciamento dei parametri di prestazioni. </p> <p>Per ulteriori informazioni, vedere <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> L'interfaccia del monitor server </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server correlati </p> </td> 
   <td colname="col2"> <p>Solo per cluster di server Workbench dati. </p> <p>Un menu che elenca i nomi comuni dei computer elencati nel file *.address del server <span class="filepath"> Workbench dati principale </span> . Questo elenco in genere include tutti i server Workbench <span class="keyword"> dati di elaborazione </span> nel cluster. Questo menu viene visualizzato solo se Workbench dati dispone di una copia del file *.address del server <span class="filepath"> Workbench dati principale </span> . </p> <p>Quando fate clic su Server <span class="uicontrol"> correlati </span>, potete fare clic su: 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Server Monitor List </span>, che visualizza l'interfaccia <span class="wintitle"> Server Monitor </span> con i dettagli per tutti i server correlati </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">Il nome comune di un server Workbench dati, che visualizza un menu di scelta rapida che consente di aprire uno dei seguenti elementi per tale server: 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Stato dettagliato </span>. Consultate <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> L’Interfaccia Di Stato Dettagliata </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Desktop remoto </span>. Consultate <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> L'Opzione Desktop Remoto </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Server Files Manager </span>. Vedere <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Server Files Manager </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Server Monitor </span>. Vedete <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> L'Interfaccia Del Monitor Server </a>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_5BFA0AFE2D9A4337BF04343879DAD03B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Prodotto </p> </td> 
   <td colname="col2"> <p>Nome prodotto, versione e numero build. </p> <p>Esempio: Sensore 3.76; J3,67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> L' <span class="wintitle"> ID sensore </span> specificato nel file di configurazione <span class="wintitle"> Sensor </span> per questa installazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>Indirizzo IP del server Web o dell'applicazione su cui <span class="wintitle"> è installato Sensor </span> . </p> <p>Esempio: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>ID processo assegnato dal sistema operativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Se <span class="wintitle"> Sensor </span> e il server Workbench dati comunicano utilizzando SSL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo </p> </td> 
   <td colname="col2"> <p>Ora (HH:MM:SS) in cui l' <span class="wintitle"> </span> ultimo sensore ha stabilito una connessione con il server Workbench dati. </p> </td> 
  </tr> 
 </tbody> 
</table>
