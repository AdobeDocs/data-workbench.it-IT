---
description: Informazioni concettuali sui tag di terze parti e sulla prevenzione del blocco dei cookie con P3P.
solution: Analytics
title: Considerazioni P3P per l'assegnazione di tag a pagine di terze parti
topic: Data workbench
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Considerazioni P3P per l&#39;assegnazione di tag a pagine di terze parti{#p-p-considerations-for-third-party-page-tagging}

Informazioni concettuali sui tag di terze parti e sulla prevenzione del blocco dei cookie con P3P.

## Informazioni sui tag delle pagine di terze parti {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

Nella maggior parte delle implementazioni, il cookie persistente Adobe viene visualizzato come cookie di prime parti. I cookie di prime parti sono definiti come quelli associati al dominio host.

Supponete che un utente visiti http://www.example.com/. Presupponendo che un sensore sia installato e operativo sul server Web in cui risiede il dominio, viene impostato un cookie persistente Adobe che viene visualizzato come cookie di prime parti. È tuttavia possibile raccogliere i dati di misurazione da un sito di terze parti tramite l&#39;uso di oggetti incorporati, che vengono richiesti e caricati dal server in esecuzione [!DNL Sensor] invece che dal server di terze parti che ospita la pagina o il programma pubblicitario. Ad esempio, http://www.example2.com/ fornisce una pagina Web con una richiesta di oggetto incorporato trasmessa da http://www.example.com/. La richiesta dell&#39;oggetto incorporato da http://www.example.com/ determina l&#39;impostazione di un cookie; tuttavia, in questo contesto, il browser Web o l&#39;agente utente visualizza il cookie come cookie di terze parti.

Nei browser Web più recenti, come Internet Explorer 6 di Microsoft, le funzioni per la privacy filtra i cookie in base ai criteri compatti inviati nell’intestazione della risposta HTTP dal server Web. Nelle impostazioni IE6 predefinite, che la maggior parte degli utenti non cambia mai, i cookie di terze parti vengono bloccati quando hanno criteri compatti inesistenti o insoddisfacenti. La maggior parte dei siti che riscontrano problemi di blocco dei cookie dispone di cookie di terze parti sul proprio sito che non dispongono dei criteri compatti appropriati che vengono inviati nell’intestazione della risposta HTTP. Inoltre, alcuni problemi di blocco dei cookie si verificano quando un sito viene incorniciato da un altro sito. Ad esempio, un negozio online che fa parte di un portale di acquisti online potrebbe essere visualizzato in una cornice fornita dal portale. Dal punto di vista del browser, il contenuto dello store potrebbe apparire come contenuto di terze parti se incorniciato dal portale. Tuttavia, se un visitatore accede direttamente allo store online senza passare attraverso il portale, il contenuto sarà contenuto di prime parti. Così, il negozio online trova che i loro cookie sono bloccati solo quando i visitatori arrivano attraverso il portale.

I sistemi di posta basati sul Web causano un problema simile. Se un visitatore di un sito Web invia una e-mail a un amico che utilizza un sistema di posta elettronica basato sul Web, il messaggio e-mail viene visualizzato come contenuto di terze parti nel browser dell’amico, in quanto è incorniciato dal sistema e-mail. Se sono presenti cookie associati alla pagina inviata tramite e-mail, IE6 li tratta come cookie di terze parti.

## Utilizzo di P3P per impedire il blocco dei cookie {#section-96831cad887649f295aec6931750e41a}

P3P offre un metodo standard per i siti Web per codificare le proprie politiche sulla privacy in un formato XML leggibile dal computer. I browser Web P3P e gli altri agenti utente P3P recuperano automaticamente le policy sulla privacy P3P, le analizzano e le confrontano con le preferenze di privacy di un utente.

Per evitare che IE6 blocchi i cookie sul sito, dovete verificare quanto segue:

1. A tutti i cookie impostati in un contesto di terze parti sono associate politiche P3P compatte.
1. Il criterio compatto appropriato viene inviato utilizzando un&#39;intestazione di risposta HTTP personalizzata.
1. Tali politiche compatte sono considerate soddisfacenti da IE6.
1. Se i cookie di terze parti vengono impostati da un&#39;altra società, potrebbe essere necessario chiedere loro di abilitare P3P e impostare le politiche compatte P3P. Per ogni host che imposta una policy P3P compatta, è necessario che sia applicato anche un criterio P3P completo corrispondente. Gli utenti possono modificare le loro impostazioni IE6 in modo che i cookie siano bloccati anche in altre condizioni; tuttavia, il posizionamento di criteri compatti soddisfacenti sui cookie di terze parti impedisce la maggior parte dei cookie IE6 di blocco.

Esempio di intestazione P3P:

```
P3P: policyref=” http://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

In questo esempio, il file [!DNL p3p.xml] [!DNL policy.xml] viene utilizzato per fare riferimento a un file associato che risiede sul server Web e che indica i tipi di informazioni raccolte dal sito Web, i metodi di risoluzione delle controversie cui l&#39;organizzazione aderisce, le modalità di utilizzo dei dati raccolti, chi possiede i dati e altre informazioni standard relative alla privacy di Internet. I tre codici di carattere che seguono &quot;CP&quot; sono i codici di criteri compatti che emulano ciò che è dichiarato all&#39;interno del [!DNL policy.xml] file.

Tutti i file XML delle politiche compatte e dei criteri devono essere personalizzati in base alla rispettiva organizzazione per la quale vengono distribuiti, specificando con precisione le politiche di privacy interne relative alla raccolta dei dati del sito Web. È possibile trovare online numerosi editor di criteri P3P insieme a informazioni più dettagliate sull&#39;implementazione di un&#39;adeguata informativa sulla privacy all&#39;interno del sito Web.

Per ulteriori informazioni su come Internet Explorer 6 gestisce le intestazioni P3P, visitare:

[http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
