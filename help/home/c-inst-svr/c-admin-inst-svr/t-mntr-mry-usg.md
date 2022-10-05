---
description: Informazioni sulla valutazione e il monitoraggio del carico dello spazio degli indirizzi.
title: Monitoraggio dell’utilizzo della memoria
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
exl-id: b8c0b33b-dbec-4947-911b-11c8a83bbc9c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 2%

---

# Monitoraggio dell’utilizzo della memoria{#monitoring-memory-usage}

{{eol}}

Informazioni sulla valutazione e il monitoraggio del carico dello spazio degli indirizzi.

**Monitoraggio del caricamento dello spazio degli indirizzi**

**Frequenza consigliata:** Giornaliero

Il carico dello spazio degli indirizzi è una misura della frazione dello spazio degli indirizzi massimo configurato correttamente [!DNL Insight Server] utilizza . Anche se i parametri di configurazione vengono modificati per ridurre l&#39;utilizzo della memoria, di solito non diminuisce fino a quando il [!DNL Insight Server] il servizio viene riavviato.

Un margine di sicurezza è integrato nel valore massimo di caricamento Spazio indirizzo per tenere conto di incrementi imprevisti nell&#39;utilizzo dello spazio degli indirizzi. Non devi mai tagliare deliberatamente in questo margine di sicurezza. Esiste per le situazioni di emergenza e non per il supporto delle funzionalità aggiunte all&#39;applicazione Adobe.

>[!NOTE]
>
>Per rendere disponibile più spazio di indirizzo ed evitare errori di esaurimento della memoria, assicurarsi che il sistema operativo disponga dello switch /3GB abilitato e che l&#39;heap a bassa frammentazione sia in funzione.

Errori registrati nel [!DNL Insight Server] il registro dati dell&#39;evento può fornire un indizio che i problemi si sviluppano con il caricamento dello spazio degli indirizzi:

* Gli errori &quot;x byte block richiesto è troppo grande&quot; indicano che qualcosa può avere un impatto eccessivo sul caricamento dello spazio degli indirizzi, sulle prestazioni e sulla larghezza di banda della rete. Tali blocchi di grandi dimensioni possono contribuire notevolmente all&#39;utilizzo dello spazio di indirizzo, sia utilizzando molta memoria sia richiedendo blocchi contigui di ampio spazio di indirizzi.

   Per risolvere questo problema, è possibile ridurre la cardinalità delle dimensioni più grandi, che aumenta il carico di Spazio indirizzi. Se non è possibile ridurre la cardinalità delle dimensioni, è necessario tentare di mantenere il carico Spazio indirizzi sufficientemente piccolo da poter gestire un aumento imprevisto.
* Gli errori &quot;Superato budget memoria&quot; indicano che potrebbe essere necessario aumentare il limite di memoria della query. La memoria utilizzata dalle query è proporzionale alla cardinalità delle dimensioni e, in alcuni casi, alle lunghezze dei nomi degli elementi. Se si aumenta il limite di memoria della query, si aumenta il carico totale di spazio indirizzi e si riducono le dimensioni grandi.

>[!NOTE]
>
>Per impostazione predefinita, è consentito l’utilizzo di pagine di grandi dimensioni e la ricerca mappata alla memoria è disabilitata. In DWB 6.7 e versioni successive, questo può essere modificato nella configurazione del set di dati. Qualsiasi modifica richiede un riavvio del server.

**Valutazione del carico dello spazio degli indirizzi**

Per valutare con precisione il carico di spazio degli indirizzi per il sistema, Adobe consiglia di rielaborare il set di dati, eseguendo alcune query normali senza riavviare successivamente [!DNL Insight Server], quindi visualizzare il carico misurato dello spazio degli indirizzi seguendo questi passaggi.

Se [!DNL Insight Server] non è stato rielaborato e sottoposto a query in modo significativo dall&#39;ultimo riavvio, non è necessario trarre conclusioni dal caricamento Spazio indirizzi.

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.
1. Fai clic con il pulsante destro del mouse sull’icona [!DNL Insight Server] si desidera configurare e fare clic su **[!UICONTROL Detailed Status]**.
1. Nell’interfaccia di Stato dettagliato, fai clic su **[!UICONTROL Memory Status]** per visualizzarne il contenuto. Nel parametro di caricamento dello spazio degli indirizzi è possibile visualizzare il carico dello spazio degli indirizzi espresso come percentuale e una descrizione tra parentesi che indica lo stato.

   Nella tabella seguente sono riportati gli intervalli e lo stato del caricamento dello spazio degli indirizzi. Per ogni intervallo è elencata un’azione consigliata.

   | Caricamento dello spazio degli indirizzi (%) | Stato | Azione consigliata |
   |---|---|---|
   | 0-15 | magra e media | Nessuno. |
   | 15-33 | chiaro | Nessuno. |
   | 33-66 | moderato | Nessuno. |
   | 66-100 | pesante | Per evitare errori di esaurimento della memoria, non aggiungere funzionalità aggiuntive significative o tentare di elaborare più dati. |
   | 100-125 | compromesso in termini di affidabilità | Regola la configurazione del set di dati per ridurre il carico dello spazio degli indirizzi. |
   | uguale o superiore a 125 | imminente fallimento | Regola la configurazione del set di dati per ridurre il carico dello spazio degli indirizzi. È possibile che non venga visualizzato lo stato di errore imminente prima che si verifichi un errore. |

   Se viene visualizzato un carico di spazio degli indirizzi superiore al 100%, è necessario modificare la configurazione il prima possibile per ridurre l’utilizzo dello spazio degli indirizzi.
