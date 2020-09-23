---
description: Se i client possono raggiungere un server Insight attraverso più reti (ad esempio, attraverso la Intranet aziendale e tramite Internet), il file dell'indirizzo deve definire un percorso di rete separato per ciascuno degli indirizzi IP del server.
solution: Analytics
title: Indirizzi IP multipli per Insight Server
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---


# Indirizzi IP multipli per Insight Server{#multiple-ip-addresses-for-an-insight-server}

Se i client possono raggiungere un server Insight attraverso più reti (ad esempio, attraverso la Intranet aziendale e tramite Internet), il file dell&#39;indirizzo deve definire un percorso di rete separato per ciascuno degli indirizzi IP del server.

Ad esempio, se il server [!DNL VS01.myCompany.com] ha un indirizzo IP pari a 10.2.1.70 su una rete interna e un indirizzo IP pari a 65.196.125.167 su Internet, il file dell&#39;indirizzo includerà un percorso di rete per ciascuno degli indirizzi, come illustrato nell&#39;esempio seguente:

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

Quando gli utenti si connettono a un [!DNL Insight Server], utilizzano il parametro NetworkLocation (nell&#39;interfaccia utente del client) per specificare il percorso di rete attraverso il quale desiderano risolvere il nome comune del server. Ad esempio, dato un file di indirizzo con le due NetworkLocations indicate sopra, un utente imposta il parametro NetworkLocation su &quot;MyCorporate Intranet&quot; per connettersi [!DNL Insight Server] attraverso la rete interna e su &quot;Internet&quot; per connettersi al server tramite Internet.
