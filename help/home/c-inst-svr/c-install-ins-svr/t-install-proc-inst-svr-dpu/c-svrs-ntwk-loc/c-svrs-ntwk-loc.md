---
description: I client di Insight Server (Report e Insight) utilizzano nomi comuni per fare riferimento a Insight Server.
title: Definizione del percorso di rete del server
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# Definizione del percorso di rete del server{#defining-the-server-s-network-location}

{{eol}}

I client di Insight Server (Report e Insight) utilizzano nomi comuni per fare riferimento a Insight Server.

Ad esempio, quando ci si connette [!DNL Insight] o [!DNL Report] a [!DNL Insight Server], identifica il server in base al suo nome comune (ad esempio, [!DNL Server.MyCompany.com]). Internamente, il client risolve il nome comune in un indirizzo IP numerico prima di inviare una richiesta al server.

Per risolvere i nomi comuni agli indirizzi IP, [!DNL Insight Server’s] i client utilizzano un file di ricerca locale denominato file indirizzo. Nel file degli indirizzi sono elencati i nomi comuni di [!DNL Insight Servers] installati nella tua organizzazione e identifica i loro indirizzi IP numerici. Un client riceve automaticamente una copia del file dell’indirizzo quando apre un profilo nel [!DNL Insight Server].

Quando un cliente invia una richiesta a un [!DNL Insight Server], tenta di risolvere il nome comune del server attraverso il file dell’indirizzo. Se il file dell&#39;indirizzo identifica un indirizzo IP per il server richiesto, il client indirizza la richiesta all&#39;indirizzo specificato. Se l’indirizzo non è definito (ad esempio, il file dell’indirizzo non definisce il nome comune del server), la richiesta non riesce. Facoltativamente, puoi configurare i client per risolvere gli indirizzi tramite il normale meccanismo DNS (Domain Naming Service) dell’ambiente operativo se un nome non è definito nel file degli indirizzi del client. Per istruzioni, vedi il parametro Parent nel [Tabella parametri di NetworkLocation](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) nella sezione seguente.
