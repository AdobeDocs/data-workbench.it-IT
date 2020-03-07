---
description: L'interfaccia Monitor server è utile per risolvere o semplicemente per monitorare i parametri di prestazioni dei computer server Workbench dati e dei computer Report che sono client dei computer server Workbench dati.
solution: Analytics
title: Interfaccia Monitor server
topic: Data workbench
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Interfaccia Monitor server{#server-monitor-interface}

L&#39;interfaccia Monitor server è utile per risolvere o semplicemente per monitorare i parametri di prestazioni dei computer server Workbench dati e dei computer Report che sono client dei computer server Workbench dati.

L&#39;interfaccia Monitor server visualizza un punto verde o un punto rosso nella parte superiore, a sinistra del nome del computer. Un punto verde indica che il computer funziona senza problemi. Un punto rosso indica che si sono verificati uno o più errori nel computer.

Nella parte inferiore dell&#39;interfaccia Monitor server sono elencati lo stato di elaborazione di ciascuno dei profili disponibili e i dettagli sulle prestazioni del computer.

Per ulteriori informazioni su [!DNL Data Workbench servers]questo argomento, vedere la Guida all&#39;installazione e all&#39;amministrazione dei prodotti *server*. Per ulteriori informazioni su [!DNL Report]questo argomento, vedere la Guida *al rapporto di Workbench* dati.

**Per aprire l&#39;interfaccia Monitor server**

* In Server Manager fare clic con il pulsante destro del mouse sul nodo del server o del [!DNL Report] computer Workbench dati. t

Fate clic **[!UICONTROL Server Monitor]** per visualizzare i dettagli su un server oppure fate clic su **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** per visualizzare i dettagli su un cluster di server correlati.

![](assets/vis_ServerMonitor.png)

L&#39; [!DNL Server Monitor]interfaccia si aggiorna automaticamente ogni 10 secondi.

Nella tabella seguente sono elencate le attività che è possibile completare utilizzando l&#39; [!DNL Server Monitor] interfaccia.

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per eseguire questa operazione... </th> 
   <th colname="col2" class="entry"> Fai questo... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Per verificare lo stato di elaborazione del registro di un profilo </p> </td> 
   <td colname="col2"> <p>Visualizzate il vettore Nome <i>profilo</i> . Nell'esempio precedente, si visualizzerebbe il vettore Profile EsempioProfile per verificare che il profilo SampleProfile elabora su un server e che l'elaborazione del registro è completa al 100%. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per determinare quanto tempo il computer impiega per rispondere alle richieste </p> </td> 
   <td colname="col2"> <p>Visualizzare il campo di latenza del sondaggio. Se questo valore è superiore a 1000 ms, contattate il servizio di supporto Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare una stima del tempo necessario per completare la trasformazione o per eseguire query </p> </td> 
   <td colname="col2"> <p>Visualizzare il campo del tempo di sweep (hh:mm:ss), presente solo durante la trasformazione o l’esecuzione di query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per determinare il numero corrente di connessioni di rete al computer </p> </td> 
   <td colname="col2"> <p>Visualizzare l'ultima riga delle informazioni sul <span class="wintitle"> Server Monitor</span> del computer. Nell'esempio precedente, sono presenti 2 connessioni di rete provenienti da un computer. </p> </td> 
  </tr> 
 </tbody> 
</table>

