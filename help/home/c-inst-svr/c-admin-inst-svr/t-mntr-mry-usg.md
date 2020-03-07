---
description: Informazioni sulla valutazione e il monitoraggio del carico dello spazio indirizzo.
solution: Insight
title: Monitoraggio dell'utilizzo della memoria
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Monitoraggio dell&#39;utilizzo della memoria{#monitoring-memory-usage}

Informazioni sulla valutazione e il monitoraggio del carico dello spazio indirizzo.

**Monitoraggio del carico dello spazio degli indirizzi**

**Frequenza consigliata:** Giornaliero

Il carico spazio indirizzo è una misura della frazione della quantità massima di spazio indirizzo utilizzata da un [!DNL Insight Server] utente configurato correttamente. Anche se i parametri di configurazione vengono modificati per ridurre l&#39;utilizzo della memoria, in genere non diminuisce finché il [!DNL Insight Server] servizio non viene riavviato.

Un margine di sicurezza è integrato nel limite massimo di carico spazio indirizzo per tenere conto di incrementi imprevisti nell&#39;utilizzo dello spazio indirizzo. Non si dovrebbe mai tagliare deliberatamente in questo margine di sicurezza. Esiste per le situazioni di emergenza e non per il supporto delle funzionalità aggiunte all’applicazione Adobe.

>[!NOTE]
>
>Per rendere disponibile più spazio di indirizzo ed evitare errori di esaurimento della memoria, assicurarsi che il sistema operativo in uso disponga dello switch /3GB abilitato e che sia in funzione un Heap con frammentazione bassa.

Gli errori registrati nel registro dei dati dell&#39; [!DNL Insight Server] evento possono fornire un indizio che i problemi si stanno sviluppando con il caricamento dello spazio indirizzi:

* Gli errori di tipo &quot;Il blocco di byte X richiesto è troppo grande&quot; indicano che un elemento potrebbe avere un impatto eccessivo sul carico, le prestazioni e la larghezza di banda dello spazio indirizzi. Tali blocchi di grandi dimensioni possono contribuire notevolmente all&#39;utilizzo dello spazio, sia utilizzando molta memoria sia richiedendo grandi blocchi contigui di spazio indirizzi.

   Per risolvere questo problema, è possibile ridurre la cardinalità delle dimensioni maggiori, che aumenta il carico Spazio indirizzi. Se non è possibile ridurre la cardinalità delle dimensioni, è necessario tentare di mantenere il carico Spazio indirizzi sufficientemente piccolo in modo da poter gestire un aumento imprevisto.
* Gli errori &quot;Superato budget memoria&quot; indicano che potrebbe essere necessario aumentare il limite di memoria della query. La memoria utilizzata dalle query è proporzionale alla centralità della dimensione e, in alcuni casi, alla lunghezza dei nomi degli elementi. Se si aumenta il limite di memoria della query, si aumenta il carico totale dello spazio indirizzi e si riducono le dimensioni grandi.

>[!NOTE]
>
>Per impostazione predefinita, l&#39;utilizzo di pagine grandi è consentito e la ricerca mappata sulla memoria è disabilitata. In DWB 6.7 e versioni successive, questo può essere modificato nella configurazione del dataset. Eventuali modifiche richiedono il riavvio del server.

**Per valutare il carico dello spazio di indirizzi**

Per valutare con precisione il carico dello spazio indirizzi per il sistema in uso, Adobe consiglia di rielaborare il set di dati, eseguire alcune normali query senza riavviare in seguito [!DNL Insight Server]e quindi visualizzare il carico dello spazio indirizzi misurato seguendo questi passaggi.

Se un oggetto [!DNL Insight Server] non è stato rielaborato e interrogato in modo significativo dall&#39;ultimo riavvio, non è necessario trarre conclusioni dal carico Spazio indirizzi.

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.
1. Fare clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] file da configurare e fare clic su **[!UICONTROL Detailed Status]**.
1. Nell’interfaccia Stato dettagliato, fate clic **[!UICONTROL Memory Status]** per visualizzarne il contenuto. Nel parametro Caricamento spazio indirizzo potete vedere il carico spazio indirizzo espresso come percentuale e una descrizione parentetica che indica lo stato.

   Nella tabella seguente sono riportati gli intervalli e lo stato per il caricamento dello spazio indirizzi. Per ogni intervallo è elencata un&#39;azione consigliata.

   | Caricamento spazio indirizzo (%) | Stato | Azione consigliata |
   |---|---|---|
   | 0-15 | magro e medio | Nessuno. |
   | 15-33 | light | Nessuno. |
   | 33-66 | moderato | Nessuno. |
   | 66-100 | pesante | Per evitare problemi di esaurimento della memoria, non aggiungere ulteriori funzionalità o tentare di elaborare più dati. |
   | 100-125 | affidabilità compromessa | Regolate la configurazione del set di dati per ridurre il carico di spazio indirizzo. |
   | 125 o superiore | fallimento imminente | Regolate la configurazione del set di dati per ridurre il carico di spazio indirizzo. Potrebbe non essere possibile visualizzare lo stato di errore imminente prima che si verifichi un errore. |

   Se viene visualizzato un carico spazio indirizzi superiore al 100%, è necessario modificare la configurazione il prima possibile per ridurre l&#39;utilizzo dello spazio indirizzi.

