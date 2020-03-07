---
description: Concettualmente, il file indirizzo ha lo stesso scopo del file ETC\HOSTS su un computer in rete.
solution: Insight
title: Posizioni di rete
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Posizioni di rete{#network-locations}

Concettualmente, il file indirizzo ha lo stesso scopo del file ETC\HOSTS su un computer in rete.

Tuttavia, a differenza del file HOSTS, che descrive una singola raccolta di nomi, il file di indirizzo contiene più raccolte di nomi denominate posizioni di rete.

Un percorso di rete è una raccolta denominata di definizioni di indirizzi. Ogni definizione di indirizzo nella raccolta associa un nome comune a un indirizzo IP.

Nel file dell&#39;indirizzo, un percorso di rete è definito in una struttura denominata NetworkLocation. Nell&#39;esempio seguente, NetworkLocation definisce un percorso di rete denominato &quot;Intranet MyCorporate&quot;. Contiene una definizione di indirizzo che mappa il nome comune [!DNL VS01.myCompany.com] all&#39;indirizzo IP &quot;10.2.1.70&quot;.

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

Come mostrato nell’esempio precedente, la struttura NetworkLocation è composta da tre parametri principali:

<table id="table_9142A0EFA15E4C37975E7ACE234F6FDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Indirizzi </td> 
   <td colname="col2"> Definisce zero o più AddressDefinitions. Ogni AddressDefintion associa un nome comune a un indirizzo IP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Assegna un nome a NetworkLocation. Il nome assegnato a un NetworkLocation deve essere univoco all’interno del file dell’indirizzo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elemento padre </td> 
   <td colname="col2"> <p>Specifica il nome di un altro NetworkLocation i cui membri sono inclusi in questo NetworkLocation. Questo parametro consente a NetworkLocation di estenderne un altro. </p> <p>È possibile impostare il parametro Parent su "DNS" per estendere un NetworkLocation al normale sistema DNS del client. </p> <p>Esempio: Elemento padre = stringa: DNS </p> <p>Quando il DNS è l'elemento padre, i client tentano di risolvere un nome comune utilizzando il sistema DNS del computer client quando non possono risolvere il nome tramite NetworkLocation. </p> </td> 
  </tr> 
 </tbody> 
</table>

