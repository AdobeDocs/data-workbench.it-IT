---
description: Controlla se il raccoglitore è in esecuzione utilizzando metodi diversi.
title: Conferma dell’esecuzione dell’agente di raccolta dati
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# Conferma dell’esecuzione dell’agente di raccolta dati{#confirming-that-the-data-collector-is-running}

Controlla se il raccoglitore è in esecuzione utilizzando metodi diversi.

**Frequenza consigliata:** ogni 5-10 minuti

* [Utilizza la funzionalità di test del sito nel trasmettitore.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Controlla  [!DNL Sensor] se sta impostando un cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Utilizzo del test del sito {#section-a5a697c3252e40f184c0b662926170f2}

Un modo per verificare che il raccoglitore sia in esecuzione è quello di abilitare la funzione Site Test nel trasmettitore. Quando abiliti Test del sito, il trasmettitore invia periodicamente (ogni 60 secondi) una richiesta di GET al server web sul quale il raccoglitore è in esecuzione. Se il test del sito non riceve una risposta dal server web, scrive un messaggio di errore in syslog e invia un messaggio di errore al [!DNL data workbench server] (scritto nel file del registro del sensore).

Se Site Test riceve una risposta dal server Web, cerca nel file di coda un pacchetto dal server Web. Se il pacchetto non viene visualizzato (indicando che il raccoglitore non era in esecuzione per l&#39;acquisizione dell&#39;evento), Site Test scrive un messaggio di errore in syslog e invia un messaggio di errore all&#39;Adobe (che viene scritto anche nel file del registro del sensore).

Nelle richieste inviate al server Web da Site Test, il valore User-Agent viene impostato su &quot;[!DNL Sensor] Test&quot;. Se non desideri che queste richieste vengano visualizzate nel set di dati, aggiungi l&#39;agente utente &quot;[!DNL Sensor] Test&quot; al file [!DNL Baseline Robots List.txt] o al file [!DNL Extended Robots List.txt] nella cartella [!DNL Lookups] del file [!DNL data workbench server].

**Per abilitare il test del sito nel trasmettitore**

1. Individua il file [!DNL txlogd.conf] sul computer in cui [!DNL Sensor] è in esecuzione e aprilo in un editor di testo.

1. Nel file [!DNL txlogd.conf], individua la riga &quot;SiteTest&quot; e configurala come mostrato di seguito. Se il file [!DNL txlogd.conf] non include la riga &quot;SiteTest&quot;, è sufficiente aggiungere la riga alla fine del file di configurazione.

   SiteTest http, *serverAddress*, *port*, *resource*

   dove *serverAddress* è il nome o l’indirizzo IP del server web, *port* è la porta di ascolto HTTP del server e *resource* è la risorsa specifica che si desidera richiedere durante il test del server tramite Test sito. Tieni presente che *resource* può includere una stringa di query.

   Esempio: SiteTest http,localhost,80,/index.jsp

   Per testare più server web, è sufficiente specificare più righe di SiteTest.

## Verifica di un cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Un altro modo per verificare che il raccoglitore sia in esecuzione su un server web consiste nel verificare se [!DNL Sensor] sta impostando un cookie nelle risposte che il server web sta restituendo ai client. Se il raccoglitore funziona, il server web restituisce un cookie &quot;v1st&quot;.

È possibile rinominare il cookie. Se lo hai fatto, devi cercare il nome specificato, non v1st.

Puoi eseguire questo controllo utilizzando uno script automatizzato o un agente di monitoraggio. Per uno script di esempio o per ulteriore assistenza su questa attività, contatta Adobe Consulting Services.
