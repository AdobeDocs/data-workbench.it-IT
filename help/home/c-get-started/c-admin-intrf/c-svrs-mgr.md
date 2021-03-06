---
description: Lo strumento principale utilizzato dagli amministratori di sistema è Server Manager.
title: Server Manager (Gestore dei server)
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
exl-id: e8b22d9f-3f1b-4a97-942a-85786bd3c547
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 2%

---

# Server Manager (Gestore dei server){#servers-manager}

Lo strumento principale utilizzato dagli amministratori di sistema è Server Manager.

È l&#39;interfaccia principale per determinare lo stato complessivo del sistema e per eseguire le funzioni di configurazione del sistema, gestione file e monitoraggio degli errori.

Server Manager visualizza un punto colorato (nodo) per ogni server di Data Workbench e [!DNL Sensor] installazione nel sistema e fornisce uno stato di sistema immediato per ogni installazione. Inoltre, visualizza un nodo per l&#39;installazione della Data Workbench.

I nodi verdi rappresentano le connessioni attive, i nodi rossi rappresentano le connessioni disattivate o altrimenti inaccessibili e i nodi grigi rappresentano le connessioni con stati indeterminati.

![](assets/vis_SysStat_RedGreenDots.png)

Facendo clic con il pulsante destro del mouse su un nodo è possibile visualizzare informazioni sul componente che si collega e accedere a tutti i menu correlati.

Le tabelle seguenti descrivono le informazioni fornite quando si fa clic con il pulsante destro del mouse su un nodo per Data Workbench, server di Data Workbench (incluso un server di Data Workbench principale in un cluster) o [!DNL Sensor].

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
   <td colname="col2"> <p>Nome del prodotto, versione e numero di build. </p> <p>Esempio: Data Workbench 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indirizzo </p> </td> 
   <td colname="col2"> <p>Indirizzo IP del computer Data Workbench. </p> <p>Esempio: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configura </p> </td> 
   <td colname="col2"> <p>Un collegamento al file di configurazione <span class="keyword"> della Data Workbench </span>. Fai clic su <span class="uicontrol"> Configura </span> &gt; <span class="uicontrol"> Insight.cfg </span> per visualizzare la finestra di configurazione della Data Workbench. Tutte le modifiche apportate e salvate in questa finestra vengono riportate nel file <span class="filepath"> Insight.cfg </span> nella directory di installazione di Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prodotto </p> </td> 
   <td colname="col2"> <p>Nome del prodotto, versione e numero di build. </p> <p>Esempio: Server Data Workbench 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Nome comune del computer del server di Data Workbench. </p> <p>Esempio: <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indirizzo </p> </td> 
   <td colname="col2"> <p>Indirizzo IP o nome di dominio completo del server configurato nel file Indirizzi del computer e nel parametro Posizione di rete nel file <span class="filepath"> Insight.cfg </span>. </p> <p>Esempio: 100.0.0.1 </p> <p>Per informazioni sul file Indirizzi, vedere la <i>Guida all'installazione e all'amministrazione dei prodotti server</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stato </p> </td> 
   <td colname="col2"> <p>Stato corrente del server di Data Workbench. Questo campo viene visualizzato OK quando il server Data Workbench è in esecuzione normale. Se si è verificato un errore e il nodo del server Data Workbench è rosso, il campo visualizza l’errore (ad esempio, "403 Forbidden"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stato dettagliato </p> </td> 
   <td colname="col2"> <p>Un collegamento all'interfaccia <span class="keyword"> Data Workbench server </span> <span class="wintitle"> Detailed Status </span> (Stato dettagliato), utile per la risoluzione di errori o altri problemi con il server Data Workbench. </p> <p>Per ulteriori informazioni, vedere <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Interfaccia di stato dettagliata</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desktop remoto </p> </td> 
   <td colname="col2"> <p>Apre una sessione <span class="wintitle"> Desktop remoto </span> al computer server Data Workbench. </p> <p>Per ulteriori informazioni, vedere <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Opzione Desktop remoto </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File server </p> </td> 
   <td colname="col2"> <p>Un collegamento al <span class="wintitle"> Server Files Manager </span>, che visualizza le directory e i file nella directory di installazione del server Data Workbench. </p> <p>Per ulteriori informazioni, vedere <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Server Files Manager </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Monitor server </p> </td> 
   <td colname="col2"> <p>Un collegamento all'interfaccia <span class="wintitle"> Server Monitor </span>, utile per la risoluzione dei problemi o per il tracciamento dei parametri delle prestazioni. </p> <p>Per ulteriori informazioni, vedere <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Interfaccia del monitor server </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server correlati </p> </td> 
   <td colname="col2"> <p>Solo per i cluster di server Data Workbench. </p> <p>Menu in cui sono elencati i nomi comuni dei computer elencati nel file *.address </span> del server di Data Workbench <span class="filepath">. Questo elenco di solito include tutti i server di Data Workbench <span class="keyword"> di elaborazione </span> nel cluster. Questo menu viene visualizzato solo se la Data Workbench dispone di una copia del file *.address </span> del server di Data Workbench principale <span class="filepath">. </span></span></p> <p>Quando fai clic su <span class="uicontrol"> Server correlati </span>, puoi fare clic su: 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Server Monitor List  </span>, che visualizza l' <span class="wintitle"> interfaccia  </span> Server Monitor in cui sono elencati i dettagli per tutti i server correlati </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">Il nome comune di qualsiasi server Data Workbench, che visualizza un menu di scelta rapida che consente di aprire uno dei seguenti elementi per quel particolare server: 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Stato dettagliato  </span>. Vedere <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Interfaccia di stato dettagliata </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Desktop remoto  </span>. Vedere <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Opzione Desktop remoto </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Server Files Manager (Gestore dei file del server)  </span>. Vedere <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Server Files Manager </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Server Monitor  </span>. Vedere <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Interfaccia del monitor server </a>. </li> 
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
   <td colname="col2"> <p>Nome del prodotto, versione e numero di build. </p> <p>Esempio: sensore 3.76; J3,67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> L'ID <span class="wintitle"> sensore </span> specificato nel file di configurazione <span class="wintitle"> Sensor </span> per questa installazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>Indirizzo IP del server web o dell'applicazione in cui è installato <span class="wintitle"> Sensor </span> . </p> <p>Esempio: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>ID del processo assegnato dal sistema operativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Se il sensore <span class="wintitle"> </span> e il server di Data Workbench comunicano utilizzando SSL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo </p> </td> 
   <td colname="col2"> <p>Ora (HH:MM:SS) in cui il <span class="wintitle"> Sensor </span> ha stabilito l'ultima connessione con il server Data Workbench. </p> </td> 
  </tr> 
 </tbody> 
</table>
