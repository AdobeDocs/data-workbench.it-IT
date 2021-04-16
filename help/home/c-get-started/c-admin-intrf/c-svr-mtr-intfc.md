---
description: L'interfaccia Server Monitor è utile per la risoluzione dei problemi o per il semplice tracciamento dei parametri di prestazioni dei computer server Data Workbench e dei computer Report che sono client dei computer server Data Workbench.
title: Interfaccia Server Monitor (Monitor del server)
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 1%

---

# Interfaccia Server Monitor (Monitor del server){#server-monitor-interface}

L&#39;interfaccia Server Monitor è utile per la risoluzione dei problemi o per il semplice tracciamento dei parametri di prestazioni dei computer server Data Workbench e dei computer Report che sono client dei computer server Data Workbench.

L&#39;interfaccia di Server Monitor visualizza un punto verde o un punto rosso nella parte superiore, a sinistra del nome del computer. Un punto verde indica che il computer funziona senza problemi. Un punto rosso indica che si sono verificati uno o più errori nel computer.

La parte inferiore dell&#39;interfaccia Server Monitor elenca lo stato di elaborazione di ciascuno dei profili disponibili e i dettagli sulle prestazioni del computer.

Per ulteriori informazioni su [!DNL Data Workbench servers], vedere la *Guida all&#39;installazione e all&#39;amministrazione dei prodotti server*. Per ulteriori informazioni su [!DNL Report], consulta la *Data Workbench guida ai rapporti*.

**Per aprire l&#39;interfaccia Server Monitor**

* In Server Manager fare clic con il pulsante destro del mouse sul nodo del server Data Workbench o del computer [!DNL Report]. t

Fare clic su **[!UICONTROL Server Monitor]** per visualizzare i dettagli relativi a un server oppure fare clic su **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** per visualizzare i dettagli relativi a un cluster di server correlati.

![](assets/vis_ServerMonitor.png)

L&#39;interfaccia [!DNL Server Monitor]viene aggiornata automaticamente ogni 10 secondi.

Nella tabella seguente sono elencate le attività che possono essere completate utilizzando l&#39;interfaccia [!DNL Server Monitor].

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per eseguire questa operazione.. </th> 
   <th colname="col2" class="entry"> Fai questo... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Per controllare lo stato di elaborazione del registro di un profilo </p> </td> 
   <td colname="col2"> <p>Visualizza il vettore Profilo <i>Profilo</i> Nome . Nell’esempio precedente, visualizzerai il vettore Esempio di profilo di profilo per vedere che il profilo ExampleProfile elabora su un server e che la sua elaborazione del registro è completa al 100%. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per determinare quanto tempo il computer impiega per rispondere alle richieste </p> </td> 
   <td colname="col2"> <p>Visualizza il campo della latenza del sondaggio. Se questo valore è superiore a 1000 ms, contatta il Servizio Supporto Tecnico Clienti Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per visualizzare una stima di quanto tempo potrebbe essere necessario per completare la trasformazione o eseguire query </p> </td> 
   <td colname="col2"> <p>Visualizzare il campo del tempo di sweep (hh:mm:ss), presente solo durante la trasformazione o la query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per determinare il numero corrente di connessioni di rete al computer </p> </td> 
   <td colname="col2"> <p>Visualizzare l'ultima riga delle informazioni relative a <span class="wintitle"> Server Monitor</span> del computer. Nell'esempio precedente, è possibile vedere che 2 connessioni di rete provengono attualmente da un computer. </p> </td> 
  </tr> 
 </tbody> 
</table>
