---
description: Il file di indirizzo installato in Insight Server contiene quattro percorsi di rete predefiniti.
solution: Analytics
title: Il file degli indirizzi installato su Insight Server
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 1%

---


# Il file degli indirizzi installato su Insight Server{#the-address-file-installed-on-insight-server}

Il file di indirizzo installato in Insight Server contiene quattro percorsi di rete predefiniti.

La procedura descritta nella sezione successiva descrive come configurare questo file.

```
Locations = vector: 4 items  
  0 = NetworkLocation:  
    Addresses = vector: 1 items 
      0 = AddressDefinition:  
        Address = string:  
        Name = string:  
    Name = string:  
    Parent = string:  
  1 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight 
    Parent = string:  
  2 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight Server 
    Parent = string: 
  3 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Report Server 
    Parent = string:
```

* NetworkLocation 0 è un percorso di rete vuoto e senza nome che si modifica per associare il nome comune del proprio [!DNL Insight Server] al proprio indirizzo IP. Se il server ha più indirizzi IP, è possibile creare ulteriori NetworkLocations.
* NetworkLocation 1 è il percorso di [!DNL Insight] rete. Se non si imposta esplicitamente il parametro NetworkLocation, [!DNL Insight] risolve i nomi comuni attraverso questo percorso di rete.

* NetworkLocation 2 è il percorso di [!DNL Insight Server] rete. Quando [!DNL Insight Servers] operano in un cluster, utilizzano questo percorso di rete per risolvere i nomi comuni per le comunicazioni tra server.

* NetworkLocation 3 è il percorso di rete del [!DNL Report] server. Se non si imposta esplicitamente il parametro NetworkLocation, [!DNL Report] risolve i nomi comuni attraverso questo percorso di rete.

## Per configurare il file dell&#39;indirizzo {#section-10caab9854a244e39b09071946f7bd27}

La procedura seguente descrive come configurare il file dell&#39;indirizzo per definire un percorso di rete (o percorsi di rete) per l&#39;utente [!DNL Insight Server].

1. Andate alla [!DNL Addresses] cartella nella directory in cui avete installato [!DNL Insight Server] (ad esempio, [!DNL C:\Adobe\Server\Addresses)].

1. Individuare il [!DNL server.address] file e rinominarlo in modo che rifletta il nome comune del server. Ad esempio, se il nome comune fosse [!DNL server.mycompany.com], il file verrebbe rinominato [!DNL server.mycompany.com.address].

1. Aprite il file rinominato in un editor di testo come Blocco note.
1. Modificate NetworkLocation 0 per specificare il nome comune e l&#39;indirizzo IP dell&#39; [!DNL Insight Server] URL come mostrato di seguito. Se il server dispone di più indirizzi IP, utilizzare NetworkLocation 0 per specificare l&#39;indirizzo IP del server sulla rete locale non router (ad esempio, la posizione sulla rete interna).

   ```
   Locations = vector: 3 items 
   0 = NetworkLocation: 
     Addresses = vector: 1 items 
       0 = AddressDefinition: 
         Address = string: IPAddress 
         Name = string: CommonName 
     Name = string: NetworkLocationName 
     Parent = string: 
   ```

<table id="table_02C2A1630CCD40C4A51B314C3CB683F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questo valore... </th> 
   <th colname="col2" class="entry"> Specifica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>Indirizzo IP</i> </td> 
   <td colname="col2"> <p>L'indirizzo IP numerico del computer <span class="keyword"> Insight Server </span> . </p> <p>Esempio: 192 168 124 176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nome comune </i> </td> 
   <td colname="col2"> <p>Nome comune assegnato al certificato digitale per <span class="keyword"> Insight Server </span>. </p> <p>Esempio: <span class="filepath"> server.mycompany.com </span></p> <p>Nota: Assicuratevi di digitare questo nome esattamente come appare sul certificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nome percorso di rete </i> </td> 
   <td colname="col2"> <p>Il nome che si desidera assegnare alla raccolta di nomi comuni e indirizzi IP rappresentata da questo NetworkLocation. Il nome deve essere univoco nel file dell'indirizzo. </p> <p>Esempio: Intranet aziendale </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Se [!DNL Insight Server] hai altri indirizzi IP, crea un&#39;ulteriore NetworkLocation per ogni indirizzo. (Un modo semplice per farlo è fare una copia della NetworkLocation creata sopra e aggiornare l&#39;indirizzo IP nella copia.)

   È possibile aggiungere il nuovo NetworkLocation alla fine del file indirizzo o inserirlo tra le definizioni NetworkLocation esistenti. (La posizione di un NetworkLocation all&#39;interno del file dell&#39;indirizzo non è significativa; tuttavia, le [!DNL Insight], [!DNL Insight Server]e [!DNL Report] Server NetworkLocations si trovano generalmente alla fine del file.

   Dopo aver aggiunto i NetworkLocations necessari, effettuate le seguenti operazioni per rinumerare gli elementi nel file:

   1. Aggiornare il conteggio degli elementi per la struttura Locations in modo che corrisponda al numero totale di definizioni NetworkLocation nel file. Ad esempio, se il file contiene quattro definizioni NetworkLocation, la riga Locations sarà la seguente:

      ```
      Locations = vector: 4 items
      ```

   1. Aggiornare i numeri degli elementi NetworkLocation in modo che NetworkLocations sia numerato consecutivamente (a partire da 0).
   Per un esempio di file di indirizzo che definisce un indirizzo [!DNL Insight Server] con due indirizzi IP, consultare l&#39;esempio in questa sezione.

1. Nei percorsi di rete [!DNL Insight] e [!DNL Report] Server modificare il parametro Parent come illustrato di seguito per specificare il nome di NetworkLocation che [!DNL Insight] e [!DNL Report] utilizzare come percorsi di rete predefiniti. Per un esempio di come si presenterà il parametro Parent quando viene configurato, consultate l&#39;esempio in questa sezione.

   ```
   1 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight 
     Parent = string: ClientDefaultNetworkLocation 
   
   3 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Report Server 
     Parent = string: ClientDefaultNetworkLocation
   ```

   Se [!DNL Insight Server] si dispone di un indirizzo IP singolo e, di conseguenza, di un solo NetworkLocation, puntare il parametro Parent su tale NetworkLocation. Se [!DNL Insight Server] avete più indirizzi IP, indicate il parametro Parent a NetworkLocation che definisce l&#39;indirizzo a cui i vostri [!DNL Insight] e [!DNL Report] client si connettono più frequentemente.

1. Nel percorso di [!DNL Insight Server] rete, modificare il parametro Parent come mostrato di seguito per indicare NetworkLocation che il server utilizza per risolvere i nomi comuni di altri [!DNL Insight Servers] quando opera in un cluster. (Anche se questo percorso di rete non viene utilizzato a meno che un cluster non [!DNL Insight Server] operi, è buona norma, anche in una singola configurazione server, puntare il parametro Parent a un percorso di rete che identifichi l&#39;indirizzo IP interno del server.)

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

L&#39;esempio seguente mostra un file di indirizzo completato. Questo file definisce cinque percorsi di rete.

* Le voci 0 e 1 di NetworkLocation definiscono le posizioni di rete denominate &quot;MyCorporateIntranet&quot; e &quot;Internet&quot;. Queste posizioni di rete definiscono due indirizzi IP diversi per un server denominato [!DNL VS01.myCompany.com].
* NetworkLocation 2 è il percorso di [!DNL Insight] rete. Si tratta del percorso di rete predefinito utilizzato da [!DNL Insight]. In questo esempio, il percorso di [!DNL Insight] rete eredita le relative definizioni di indirizzi da NetworkLocation &quot;Internet&quot;.

* NetworkLocation 3 è il percorso di [!DNL Insight Server] rete. Questo è il percorso di rete predefinito [!DNL Insight Server] utilizzato quando comunica con altri server in un cluster. In questo esempio, il percorso di [!DNL Insight Server] rete eredita le relative definizioni di indirizzi dalla NetworkLocation intranet &quot;MyCorporate&quot;.

* NetworkLocation, elemento 4 è il percorso di rete del [!DNL Report] server. Si tratta del percorso di rete predefinito utilizzato da [!DNL Report]. In questo esempio, il percorso di rete del [!DNL Report] server eredita le definizioni di indirizzi da NetworkLocation &quot;Internet&quot;.

   ```
   Locations = vector: 5 items 
     0 = NetworkLocation:  
       Addresses = vector: 1 items 
         0 = AddressDefinition:  
           Address = string: 10.2.1.70 
           Name = string: VS01.myCompany.com 
       Name = string: MyCorporateIntranet 
       Parent = string:  
   
     1 = NetworkLocation:  
       Addresses = vector: 1 items 
         0 = AddressDefinition:  
           Address = string: 65.196.125.167 
           Name = string: VS01.myCompany.com 
       Name = string: Internet 
       Parent = string: 
   
     2 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight 
       Parent = string: Internet 
   
     3 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight Server 
       Parent = string: MyCorporateIntranet 
   
     4 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Report Server 
       Parent = string: Internet
   ```

