---
description: La trasformazione AppendURI consente di aggiungere informazioni al valore predefinito che proviene dalle voci di registro utilizzate per creare il dataset.
solution: Analytics
title: AppendURI
topic: Data workbench
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# AppendURI{#appenduri}

La trasformazione AppendURI consente di aggiungere informazioni al valore predefinito che proviene dalle voci di registro utilizzate per creare il dataset.

La trasformazione posiziona una coppia nome-valore alla fine del campo interno utilizzato per creare la dimensione URI. La coppia nome-valore viene creata utilizzando il parametro chiave stringa query come nome e valore del parametro Input identificato come valore della coppia. Il [!DNL AppendURI] comando aggiunge gli elementi appropriati ? e simboli &amp; necessari per separare le coppie nome-valore dal [!DNL URI] gambo e da qualsiasi [!DNL AppendURI] operazione precedente eventualmente applicata all’URI.

La [!DNL AppendURI] trasformazione funziona solo se definita nel [!DNL Transformation.cfg] file o in un [!DNL Transformation Dataset Include] file.

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Condizioni in cui viene applicata la trasformazione. |  |
| impostazione predefinita | Il valore predefinito da utilizzare se la condizione è soddisfatta e il valore immesso non è disponibile. |  |
| Ingresso | Nome del campo il cui valore viene aggiunto all’URI. |  |
| Chiave stringa query | Nome da utilizzare per la creazione della coppia nome-valore da aggiungere. |  |

Prendete in considerazione un sito Web creato con un approccio tradizionale Model-View-Controller. In tali sistemi, è comune avere una sola pagina Web come punto di accesso nel sistema. Per un sito di questo tipo, le visualizzazioni dei pattern di traffico nel sistema sarebbero molto poco interessanti e non fornirebbero informazioni sull&#39;utilizzo e il flusso di traffico dei visitatori. Ad esempio, si consideri un sito Web che funge da funnel per tutte le richieste Web attraverso un URI del seguente modulo:

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

La pagina ASP della visualizzazione modelli riceve tutto il traffico e determina le azioni in base al valore del campo id nella query. Per impostazione predefinita, la dimensione URI contiene una singola voce:

* [!DNL modelview.asp]

Ciò comporterebbe una mappatura piuttosto poco interessante del traffico attraverso il sito, in quanto tutto il traffico viene instradato attraverso un singolo URI. Per risolvere questo particolare scenario e fornire una visualizzazione più informativa sull&#39;architettura sottostante del sito Web, [!DNL AppendURI] è possibile utilizzare per spostare alcune coppie nome-valore univoche dal campo cs-uri-query alla dimensione URI utilizzata per le visualizzazioni. La trasformazione mostrata di seguito fornisce i dettagli di tale trasformazione:

![](assets/cfg_TransformationType_AppendURI.png)

In questo esempio, il sistema utilizza due pagine per gestire tutte le richieste: [!DNL modelview.asp] e [!DNL xmlmodelview.asp]. Una pagina viene utilizzata per il traffico del browser e l&#39;altra per le comunicazioni XML tra sistemi. Il processo del server applicazioni utilizza il nome id della query cs-uri per determinare quale azione intraprendere. Pertanto, potete estrarre il valore dal campo id e aggiungerlo all’URI. Il risultato è un insieme di URI con un intervallo di varianti che riflette il traffico dei visitatori attraverso il sito Web. In questo caso, una [!DNL String Match] condizione determina le voci di registro a cui viene applicata la trasformazione eseguendo ricerche nel campo cs-uri-stem per le due pagine Web di interesse e ignorando tutte le altre. L&#39;input (il valore della nostra coppia nome-valore) è il risultato di cs-uri-query(id), che è &quot;login&quot;. Come specificato dal parametro della chiave della stringa di query, il nome aggiunto è &quot;id&quot;. Pertanto, per il valore cs-uri in entrata del nostro esempio, l&#39;URI risultante utilizzato dalla [!DNL URI] dimensione è [!DNL /modelview.asp&id=login].
