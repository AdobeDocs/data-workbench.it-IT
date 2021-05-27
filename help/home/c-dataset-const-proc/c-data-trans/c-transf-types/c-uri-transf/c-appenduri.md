---
description: La trasformazione AppendURI consente di aggiungere informazioni al valore predefinito proveniente dalle voci di registro utilizzate per creare il set di dati.
title: AppendURI
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
exl-id: 0d5901c0-bd13-4499-8e26-44839aeb7413
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 1%

---

# AppendURI{#appenduri}

La trasformazione AppendURI consente di aggiungere informazioni al valore predefinito proveniente dalle voci di registro utilizzate per creare il set di dati.

La trasformazione inserisce una coppia nome-valore alla fine del campo interno utilizzato per creare la dimensione URI. La coppia nome-valore viene creata utilizzando il parametro chiave stringa query come nome e il valore del parametro di input identificato come valore della coppia. Il comando [!DNL AppendURI] aggiunge eventuali valori appropriati ? e simboli &amp; necessari per separare le coppie nome-valore dallo stelo [!DNL URI] e da tutte le operazioni precedenti [!DNL AppendURI] che possono essere state applicate all’URI.

La trasformazione [!DNL AppendURI] funziona solo se definita nel file [!DNL Transformation.cfg] o in un file [!DNL Transformation Dataset Include].

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore specificato non è disponibile. |  |
| Ingresso | Nome del campo il cui valore viene aggiunto all’URI. |  |
| Chiave stringa di query | Nome da utilizzare nella creazione della coppia nome-valore da aggiungere. |  |

Considera un sito web costruito utilizzando un approccio tradizionale Model-View-Controller. In tali sistemi, è comune avere una singola pagina web come punto di accesso nel sistema. Per un sito di questo tipo, le visualizzazioni dei pattern di traffico nel sistema sarebbero molto poco interessanti e non fornirebbero informazioni sull’utilizzo dei visitatori e sul flusso di traffico. Ad esempio, considera un sito web che incanala tutte le richieste web attraverso un URI del seguente modulo:

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

La pagina ASP della visualizzazione modelli riceve tutto il traffico e determina le azioni in base al valore del campo id nella query. Per impostazione predefinita, la dimensione URI contiene una singola voce:

* [!DNL modelview.asp]

Questo comporterebbe una mappatura piuttosto poco interessante del traffico attraverso il sito, in quanto tutto il traffico viene incanalato attraverso un singolo URI. Per risolvere questo particolare scenario e fornire una visualizzazione più informativa sull&#39;architettura sottostante del sito web, [!DNL AppendURI] può essere utilizzato per spostare alcune coppie nome-valore univoche dal campo cs-uri-query alla dimensione URI utilizzata per le visualizzazioni. La trasformazione mostrata di seguito fornisce i dettagli di tale trasformazione:

![](assets/cfg_TransformationType_AppendURI.png)

In questo esempio, il sistema utilizza due pagine per gestire tutte le richieste: [!DNL modelview.asp] e [!DNL xmlmodelview.asp]. Una pagina viene utilizzata per il traffico del browser e l&#39;altra per le comunicazioni XML tra sistema. Il processo dell&#39;application server utilizza il nome id della query cs-uri per determinare quale azione intraprendere. Pertanto, puoi estrarre il valore dal campo id e aggiungerlo all’URI. Il risultato è una raccolta di URI con un intervallo di varianti che riflette il traffico dei visitatori attraverso il sito web. In questo caso, una condizione [!DNL String Match] determina le voci di registro a cui viene applicata la trasformazione ricercando il campo cs-uri-stem per le due pagine web di interesse e ignorando tutte le altre. L&#39;input (il valore della nostra coppia nome-valore) è il risultato di cs-uri-query(id), che è &quot;login&quot;. Come specificato dal parametro della chiave di stringa query, il nome aggiunto è &quot;id&quot;. Pertanto, per il valore cs-uri in entrata del nostro esempio, l’URI risultante utilizzato dalla dimensione [!DNL URI] è [!DNL /modelview.asp&id=login].
