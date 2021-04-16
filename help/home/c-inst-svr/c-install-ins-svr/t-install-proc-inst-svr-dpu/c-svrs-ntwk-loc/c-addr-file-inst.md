---
description: Il file di indirizzo installato in Insight Server contiene quattro posizioni di rete predefinite.
title: Il file degli indirizzi installato su Insight Server
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
exl-id: 12e9bfa2-99ac-4584-b761-38401d1bc3d1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 1%

---

# Il file degli indirizzi installato su Insight Server{#the-address-file-installed-on-insight-server}

Il file di indirizzo installato in Insight Server contiene quattro posizioni di rete predefinite.

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

* NetworkLocation 0 è un percorso di rete vuoto e senza nome che si modifica per associare il nome comune del [!DNL Insight Server] al relativo indirizzo IP. Se il server dispone di più indirizzi IP, è possibile creare ulteriori NetworkLocations.
* NetworkLocation 1 è il percorso di rete [!DNL Insight]. Se non si imposta esplicitamente il parametro NetworkLocation, [!DNL Insight] risolve i nomi comuni attraverso questo percorso di rete.

* NetworkLocation 2 è il percorso di rete [!DNL Insight Server]. Quando [!DNL Insight Servers] funziona in un cluster, utilizza questo percorso di rete per risolvere i nomi comuni per le comunicazioni tra server.

* NetworkLocation 3 è il percorso di rete [!DNL Report] del server. Se non si imposta esplicitamente il parametro NetworkLocation, [!DNL Report] risolve i nomi comuni attraverso questo percorso di rete.

## Per configurare il file degli indirizzi {#section-10caab9854a244e39b09071946f7bd27}

La procedura seguente descrive come configurare il file dell&#39;indirizzo per definire un percorso di rete (o percorsi di rete) per il [!DNL Insight Server].

1. Passa alla cartella [!DNL Addresses] nella directory in cui è stato installato [!DNL Insight Server] (ad esempio, [!DNL C:\Adobe\Server\Addresses)].

1. Individua il file [!DNL server.address] e rinomina il file in modo che rifletta il nome comune del server. Ad esempio, se il nome comune è [!DNL server.mycompany.com], è necessario rinominare il file [!DNL server.mycompany.com.address].

1. Apri il file rinominato in un editor di testo come Blocco note.
1. Modifica NetworkLocation 0 per specificare il nome comune e l&#39;indirizzo IP del [!DNL Insight Server] come mostrato di seguito. Se il server dispone di più indirizzi IP, utilizzare NetworkLocation 0 per specificare l’indirizzo IP del server sulla rete locale non router (ad esempio, la posizione sulla rete interna).

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
   <th colname="col1" class="entry"> Per questo valore.. </th> 
   <th colname="col2" class="entry"> Specifica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>Indirizzo IP</i> </td> 
   <td colname="col2"> <p>L'indirizzo IP numerico del computer <span class="keyword"> Insight Server </span>. </p> <p>Esempio: 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nome comune  </i> </td> 
   <td colname="col2"> <p>Nome comune assegnato al certificato digitale per <span class="keyword"> Insight Server </span>. </p> <p>Esempio: <span class="filepath"> server.mycompany.com </span></p> <p>Nota: Assicurati di digitare questo nome esattamente come appare sul certificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nome percorso di rete  </i> </td> 
   <td colname="col2"> <p>Nome che si desidera assegnare alla raccolta di nomi comuni e indirizzi IP rappresentati da questo NetworkLocation. Il nome deve essere univoco all'interno del file dell'indirizzo. </p> <p>Esempio: Intranet aziendale </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Se il tuo [!DNL Insight Server] dispone di indirizzi IP aggiuntivi, crea un percorso di rete aggiuntivo per ogni indirizzo. (Un modo semplice per farlo è creare una copia della NetworkLocation creata in precedenza e aggiornare l&#39;indirizzo IP nella copia.)

   È possibile aggiungere il nuovo NetworkLocation alla fine del file dell&#39;indirizzo o inserirlo tra le definizioni esistenti di NetworkLocation. (La posizione di un NetworkLocation all&#39;interno del file dell&#39;indirizzo non è significativa; tuttavia, le [!DNL Insight], [!DNL Insight Server] e [!DNL Report] NetworkLocations del server si trovano in genere alla fine del file.)

   Dopo aver aggiunto le NetworkLocations necessarie, procedi come segue per rinumerare gli elementi nel file:

   1. Aggiornare il conteggio degli elementi per la struttura Locations in modo che corrisponda al numero totale di definizioni NetworkLocation nel file. Ad esempio, se il file contiene quattro definizioni di NetworkLocation, la riga Posizioni sarà simile alla seguente:

      ```
      Locations = vector: 4 items
      ```

   1. Aggiornare i numeri degli elementi NetworkLocation in modo che NetworkLocations sia numerato consecutivamente (a partire da 0).
   Per un esempio di file di indirizzo che definisce un [!DNL Insight Server] con due indirizzi IP, consulta l’esempio in questa sezione.

1. Nelle posizioni di rete [!DNL Insight] e [!DNL Report] Server, modificare il parametro Parent come mostrato di seguito per specificare il nome di NetworkLocation che [!DNL Insight] e [!DNL Report] utilizzano come posizioni di rete predefinite. (Per un esempio dell&#39;aspetto del parametro Parent quando è configurato, consulta l&#39;esempio in questa sezione.)

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

   Se il tuo [!DNL Insight Server] ha un singolo indirizzo IP e, di conseguenza, dispone di un solo NetworkLocation, puntare il parametro Parent a tale NetworkLocation. Se il [!DNL Insight Server] dispone di più indirizzi IP, puntare il parametro Parent a NetworkLocation che definisce l&#39;indirizzo a cui i client [!DNL Insight] e [!DNL Report] si connettono più frequentemente.

1. Nel percorso di rete [!DNL Insight Server], modificare il parametro Parent come mostrato di seguito per puntare a NetworkLocation che il server utilizza per risolvere i nomi comuni di altri [!DNL Insight Servers] quando opera in un cluster. (Anche se questo percorso di rete non viene utilizzato a meno che un [!DNL Insight Server] non funzioni in un cluster, è buona prassi, anche in una singola configurazione del server, puntare il parametro Parent a un percorso di rete che identifichi l&#39;indirizzo IP interno del server.)

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

L’esempio seguente mostra un file di indirizzo completato. Questo file definisce cinque posizioni di rete.

* Le voci 0 e 1 di NetworkLocation definiscono le posizioni di rete denominate &quot;MyCorporateIntranet&quot; e &quot;Internet&quot;. Queste posizioni di rete definiscono due indirizzi IP diversi per un server denominato [!DNL VS01.myCompany.com].
* NetworkLocation item 2 è il percorso di rete [!DNL Insight]. Si tratta del percorso di rete predefinito utilizzato da [!DNL Insight]. In questo esempio, il percorso di rete [!DNL Insight] eredita le definizioni degli indirizzi da NetworkLocation &quot;Internet&quot;.

* NetworkLocation item 3 è il percorso di rete [!DNL Insight Server]. Questo è il percorso di rete predefinito utilizzato da [!DNL Insight Server] quando comunica con altri server in un cluster. In questo esempio, il percorso di rete [!DNL Insight Server] eredita le definizioni degli indirizzi dal NetworkLocation &quot;Intranet aziendale&quot;.

* NetworkLocation item 4 è il percorso di rete [!DNL Report] del server. Si tratta del percorso di rete predefinito utilizzato da [!DNL Report]. In questo esempio, il percorso di rete [!DNL Report] del server eredita le definizioni degli indirizzi da NetworkLocation &quot;Internet&quot;.

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
