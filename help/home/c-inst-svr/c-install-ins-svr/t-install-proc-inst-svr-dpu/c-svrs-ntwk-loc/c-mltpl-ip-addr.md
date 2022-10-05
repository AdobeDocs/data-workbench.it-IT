---
description: Se i client possono raggiungere Insight Server tramite più reti (ad esempio, tramite la Intranet aziendale e tramite Internet), il file dell’indirizzo deve definire un percorso di rete separato per ciascuno degli indirizzi IP del server.
title: Indirizzi IP multipli per Insight Server
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
exl-id: 71654a60-af82-45f2-826b-29ecc7127b0b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---

# Indirizzi IP multipli per Insight Server{#multiple-ip-addresses-for-an-insight-server}

{{eol}}

Se i client possono raggiungere Insight Server tramite più reti (ad esempio, tramite la Intranet aziendale e tramite Internet), il file dell’indirizzo deve definire un percorso di rete separato per ciascuno degli indirizzi IP del server.

Ad esempio, se server [!DNL VS01.myCompany.com] ha un indirizzo IP di 10.2.1.70 su una rete interna e un indirizzo IP di 65.196.125.167 su Internet, il file dell&#39;indirizzo includerebbe un percorso di rete per ciascuno degli indirizzi come illustrato nell&#39;esempio seguente:

```
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
```

Quando gli utenti si collegano a un [!DNL Insight Server], utilizzano il parametro NetworkLocation (nell’interfaccia utente del client) per specificare il percorso di rete attraverso il quale si desidera risolvere il nome comune del server. Ad esempio, dato un file di indirizzo con i due NetworkLocations mostrati sopra, un utente impostava il parametro NetworkLocation su &quot;MyCorporate Intranet&quot; per connettersi a [!DNL Insight Server] attraverso la rete interna e a &quot;Internet&quot; per connettersi al server tramite Internet.
