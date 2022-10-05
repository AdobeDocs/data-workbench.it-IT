---
description: Informazioni concettuali sull’assegnazione di tag a terze parti e sulla prevenzione del blocco dei cookie tramite P3P.
title: Considerazioni P3P per l’assegnazione di tag pagina di terze parti
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
exl-id: 8eb521b6-802c-4d9f-a6b4-b1c4f694b8b8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# Considerazioni P3P per l’assegnazione di tag pagina di terze parti{#p-p-considerations-for-third-party-page-tagging}

{{eol}}

Informazioni concettuali sull’assegnazione di tag a terze parti e sulla prevenzione del blocco dei cookie tramite P3P.

## Informazioni sull’assegnazione tag pagina di terze parti {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

Nella maggior parte delle implementazioni, il cookie persistente Adobe viene visualizzato come cookie di prime parti. I cookie di prime parti sono definiti come quelli associati al dominio host.

Supponiamo che un utente visiti https://www.example.com/. Supponendo che un sensore sia installato e operativo sul server web che ospita il dominio, viene impostato un cookie persistente di Adobe che viene visualizzato come cookie di prime parti. È tuttavia possibile raccogliere i dati di misurazione da un sito di terze parti tramite l’utilizzo di oggetti incorporati, richiesti e caricati dal server in esecuzione [!DNL Sensor] anziché dal server di terze parti che ospita la pagina o il programma pubblicitario. Ad esempio, https://www.example2.com/ fornisce una pagina web con una richiesta di oggetto incorporato trasmessa da https://www.example.com/. La richiesta dell&#39;oggetto incorporato da https://www.example.com/ determina l&#39;impostazione di un cookie; tuttavia, in questo contesto, il browser web o l’agente utente visualizza il cookie come cookie di terze parti.

Nei browser web più recenti, come Internet Explorer 6 di Microsoft, le funzioni per la privacy filtrano i cookie in base ai criteri compatti inviati nell’intestazione di risposta HTTP dal server web. Nelle impostazioni IE6 predefinite, che la maggior parte degli utenti non cambia mai, i cookie di terze parti vengono bloccati quando hanno criteri compatti inesistenti o insoddisfacenti. La maggior parte dei siti che riscontrano problemi di blocco dei cookie dispone di cookie di terze parti sul proprio sito che non dispongono dei criteri compatti appropriati per essere inviati nell&#39;intestazione di risposta HTTP. Inoltre, alcuni problemi di blocco dei cookie si verificano quando un sito viene incorniciato da un altro sito. Ad esempio, un negozio online che fa parte di un portale di shopping online può essere visualizzato in una cornice fornita dal portale. Dal punto di vista del browser, il contenuto dell’archivio può apparire come contenuto di terze parti quando viene incorniciato dal portale. Tuttavia, se un visitatore accede direttamente al negozio online senza passare attraverso il portale, il contenuto sarà contenuto di prime parti. Pertanto, il negozio online trova che i loro cookie sono bloccati solo quando i visitatori arrivano attraverso il portale.

I sistemi di posta basati sul Web causano un problema simile. Se un visitatore di un sito web invia una pagina web a un amico che utilizza un sistema di posta elettronica basato sul web, il messaggio e-mail viene visualizzato come contenuto di terze parti nel browser dell’amico, in quanto è incorniciato dal sistema e-mail. Se sono presenti cookie associati alla pagina inviata tramite e-mail, IE6 li tratta come cookie di terze parti.

## Utilizzo di P3P per impedire il blocco dei cookie {#section-96831cad887649f295aec6931750e41a}

P3P fornisce un modo standard per i siti web di codificare le loro politiche sulla privacy in un formato XML leggibile dal computer. I browser web abilitati P3P e gli altri agenti utente P3P recuperano automaticamente le policy sulla privacy P3P, le analizzano e le confrontano con le preferenze di privacy di un utente.

Per evitare che IE6 blocchi i cookie sul tuo sito, devi verificare quanto segue:

1. A tutti i cookie impostati in un contesto di terze parti sono associate politiche compatte P3P.
1. Il criterio compatto appropriato viene inviato utilizzando un’intestazione di risposta HTTP personalizzata.
1. Tali politiche compatte sono considerate soddisfacenti da IE6.
1. Se i cookie di terze parti sono impostati da un&#39;altra azienda, potrebbe essere necessario chiedere loro di abilitare P3P e impostare le politiche compatte P3P. Anche qualsiasi host che imposti una policy P3P compatta deve avere una corrispondente policy P3P completa. Gli utenti possono modificare le impostazioni di IE6 in modo che i cookie siano bloccati anche in altre condizioni; tuttavia, il posizionamento di criteri compatti soddisfacenti sui cookie di terze parti impedisce la maggior parte dei cookie IE6.

Di seguito è riportato un esempio di intestazione P3P di questo tipo:

```
P3P: policyref=” https://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

In questo esempio, il file [!DNL p3p.xml] viene utilizzato per fare riferimento a un [!DNL policy.xml] file che risiedono nel server web che denota i tipi di informazioni raccolte dal sito web, i metodi di risoluzione delle controversie a cui la tua organizzazione aderisce, le modalità di utilizzo dei dati raccolti, i proprietari dei dati e altre informazioni standard relative alla privacy Internet. I tre codici di carattere che seguono &quot;CP&quot; sono i codici di policy compatti che emulano ciò che è indicato all&#39;interno del tuo [!DNL policy.xml] file.

Tutti i criteri compatti e i file XML delle policy devono essere personalizzati in base alla rispettiva organizzazione per la quale vengono distribuiti, specificando con precisione le proprie politiche interne sulla privacy in relazione alla raccolta dei dati sul sito web. È possibile trovare online una moltitudine di editor di criteri P3P insieme a informazioni più approfondite sull&#39;implementazione di un&#39;adeguata informativa sulla privacy all&#39;interno del sito web.

Per ulteriori informazioni su come Internet Explorer 6 gestisce le intestazioni P3P, visita:

[https://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](https://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
