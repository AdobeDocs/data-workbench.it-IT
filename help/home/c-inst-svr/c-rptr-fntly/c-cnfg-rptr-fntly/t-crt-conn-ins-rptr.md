---
description: Se i firewall di rete non impediscono l’accesso al server di ripetizione da Insight machine, è possibile creare una connessione tra il server di ripetizione e Insight in modo da poter gestire il server di ripetizione utilizzando Insight.
title: Creazione di una connessione tra Insight e il Repeater (Ripetitore)
uuid: dccce83a-8708-4763-a19a-64d905a9f624
exl-id: 81e81db5-0517-41d4-a958-d08cd3975096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 4%

---

# Creazione di una connessione tra Insight e il Repeater (Ripetitore){#creating-a-connection-between-insight-and-repeater}

{{eol}}

Se i firewall di rete non impediscono l’accesso al server di ripetizione da Insight machine, è possibile creare una connessione tra il server di ripetizione e Insight in modo da poter gestire il server di ripetizione utilizzando Insight.

**Per creare una connessione tra [!DNL Insight] e il server di ripetizione**

1. In [!DNL Insight], sul [!DNL Admin] fai clic sulla scheda **[!UICONTROL Configure Connections to Servers]** per aprire l&#39;area di lavoro Configura connessioni ai server.
1. In [!DNL Insight.cfg] finestra, clic con il pulsante destro del mouse **[!UICONTROL Servers]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Server]**.
1. Per il nuovo server, completa i seguenti parametri:

<table id="table_DD79587255134B5A888A0F57CF10E5B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questo parametro.. </th> 
   <th colname="col2" class="entry"> Specifica... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2">(Facoltativo) Nome desiderato <span class="keyword"> Insight</span> da utilizzare per rappresentare il server di ripetizione nell’interfaccia utente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo </td> 
   <td colname="col2"> <p>Nome host o indirizzo IP numerico del server ripetitore. </p> <p>Esempio: <span class="filepath"> Repeater.mycompany.com</span> o 192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificato client SSL </td> 
   <td colname="col2"> <p>Facoltativo, a meno che non si disponga di più certificati. Nome del file contenente il certificato digitale per questa copia di <span class="keyword"> Insight</span>. (Questo è il file scaricato durante l'installazione <span class="keyword"> Insight</span>.) </p> <p>Esempio: <span class="filepath"> Samantha Smith.pem</span></p> <p>Se questo parametro viene lasciato vuoto, <span class="keyword"> Insight</span> utilizza qualsiasi certificato presente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server SSL </p> <p>Nome comune </p> </td> 
   <td colname="col2">Nome comune assegnato al server di ripetizione. Questo nome deve corrispondere al nome comune assegnato al server di ripetizione all’interno del certificato di licenza. Se hai accesso al file del certificato del ripetitore (<span class="filepath"> Certificati\server_cert.pem</span>), è possibile trovare il nome comune aprendo il file con un editor di testo come Blocco note. Il nome comune è indicato nel campo NC del certificato. </td> 
  </tr> 
 </tbody> 
</table>

1. Salva il file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic su **[!UICONTROL Save]**. [!DNL Insight] tenterà di connettersi al server ripetitore utilizzando le impostazioni specificate. Se viene stabilita una connessione, viene visualizzata un&#39;icona verde del server nella [!DNL Servers Manager] interfaccia. Se non è possibile stabilire una connessione, viene visualizzata un’icona rossa.

   Per ulteriori informazioni sulla [!DNL Servers Manager] interfaccia, vedi * [!DNL Insight] Guida utente*.
