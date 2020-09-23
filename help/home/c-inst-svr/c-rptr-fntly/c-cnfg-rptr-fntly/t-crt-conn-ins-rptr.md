---
description: Se i firewall di rete non impediscono l’accesso al server di ripetizione dalle macchine Insight, è possibile creare una connessione tra il server di ripetizione e Insight in modo da poter gestire il server di ripetizione utilizzando Insight.
solution: Analytics
title: Creazione di una connessione tra Insight e il Repeater (Ripetitore)
uuid: dccce83a-8708-4763-a19a-64d905a9f624
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 4%

---


# Creazione di una connessione tra Insight e il Repeater (Ripetitore){#creating-a-connection-between-insight-and-repeater}

Se i firewall di rete non impediscono l’accesso al server di ripetizione dalle macchine Insight, è possibile creare una connessione tra il server di ripetizione e Insight in modo da poter gestire il server di ripetizione utilizzando Insight.

**Creazione di una connessione tra[!DNL Insight]e il server di ripetizione**

1. In [!DNL Insight], nella [!DNL Admin] scheda, fare clic sulla **[!UICONTROL Configure Connections to Servers]** miniatura per aprire l&#39;area di lavoro Configura connessioni ai server.
1. Nella [!DNL Insight.cfg] finestra fare clic con il pulsante destro del mouse **[!UICONTROL Servers]** e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Server]**.
1. Per il nuovo server, completate i seguenti parametri:

<table id="table_DD79587255134B5A888A0F57CF10E5B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questo parametro... </th> 
   <th colname="col2" class="entry"> Specifica... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2">(Facoltativo) Nome che si desidera utilizzare in <span class="keyword"> Insight</span> per rappresentare il server di ripetizione nell'interfaccia utente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo </td> 
   <td colname="col2"> <p>Il nome host o l'indirizzo IP numerico del server di ripetizione. </p> <p>Esempio: <span class="filepath"> Repeat ater.mycompany.com</span> o 192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificato client SSL </td> 
   <td colname="col2"> <p>Facoltativo, a meno che non disponiate di più certificati. Il nome del file che contiene il certificato digitale per questa copia di <span class="keyword"> Insight</span>. Questo è il file che avete scaricato durante l'installazione di <span class="keyword"> Insight</span>. </p> <p>Esempio: <span class="filepath"> Samantha Smith.pem</span></p> <p>Se lasciate vuoto questo parametro, <span class="keyword"> Insight</span> utilizza qualsiasi certificato presente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server SSL </p> <p>Nome comune </p> </td> 
   <td colname="col2">Nome comune assegnato al server di ripetizione. Il nome deve corrispondere al nome comune assegnato al server di ripetizione all'interno del certificato di licenza. Se si dispone dell'accesso al file del certificato del ripetitore (<span class="filepath"> Certificati\server_cert.pem</span>), è possibile trovare il nome comune aprendo il file con un editor di testo come Blocco note. Il nome comune è identificato nel campo NC contenuto nel certificato. </td> 
  </tr> 
 </tbody> 
</table>

1. Salvare il file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic su **[!UICONTROL Save]**. [!DNL Insight] tenterà di connettersi al server di ripetizione utilizzando le impostazioni specificate. Se è stabilita una connessione, nell&#39; [!DNL Servers Manager] interfaccia viene visualizzata un&#39;icona verde del server. Se non è possibile stabilire una connessione, viene visualizzata un&#39;icona rossa.

   Per ulteriori informazioni sull&#39; [!DNL Servers Manager] interfaccia, vedere la * [!DNL Insight] Guida utente*.

