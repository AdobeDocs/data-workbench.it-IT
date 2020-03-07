---
description: I client di Insight Server (Report e Insight) utilizzano nomi comuni per fare riferimento ai server Insight.
solution: Insight
title: Definizione del percorso di rete del server
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definizione del percorso di rete del server{#defining-the-server-s-network-location}

I client di Insight Server (Report e Insight) utilizzano nomi comuni per fare riferimento ai server Insight.

Ad esempio, quando ci si connette [!DNL Insight] o [!DNL Report] a un [!DNL Insight Server], si identifica il server in base al suo nome comune (ad esempio, [!DNL Server.MyCompany.com]). Internamente, il client risolve il nome comune a un indirizzo IP numerico prima di inviare una richiesta al server.

Per risolvere i nomi comuni agli indirizzi IP, [!DNL Insight Server’s] i client utilizzano un file di ricerca locale denominato file indirizzo. Il file dell&#39;indirizzo elenca i nomi comuni dei [!DNL Insight Servers] computer installati nell&#39;azienda e identifica i relativi indirizzi IP numerici. Un client riceve automaticamente una copia del file dell&#39;indirizzo quando apre un profilo sul [!DNL Insight Server].

Quando un client invia una richiesta a un [!DNL Insight Server], tenta di risolvere il nome comune del server attraverso il file dell&#39;indirizzo. Se il file dell&#39;indirizzo identifica un indirizzo IP per il server richiesto, il client indirizza la richiesta all&#39;indirizzo specificato. Se l&#39;indirizzo non è definito (ad esempio, il file dell&#39;indirizzo non definisce il nome comune del server), la richiesta non riesce. Facoltativamente, è possibile configurare i client per la risoluzione degli indirizzi tramite il normale meccanismo DNS (Domain Naming Service) dell&#39;ambiente operativo, se un nome non è definito nel file dell&#39;indirizzo del client. Per istruzioni, vedete il parametro Parent nella tabella [Parametri di](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) NetworkLocation nella sezione seguente.
