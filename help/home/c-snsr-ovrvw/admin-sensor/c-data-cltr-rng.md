---
description: Verificare se il raccoglitore è in esecuzione utilizzando metodi diversi.
solution: Analytics
title: Conferma dell’esecuzione dell’agente di raccolta dati
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---


# Conferma dell’esecuzione dell’agente di raccolta dati{#confirming-that-the-data-collector-is-running}

Verificare se il raccoglitore è in esecuzione utilizzando metodi diversi.

**Frequenza consigliata:** Ogni 5-10 minuti

* [Utilizzate la funzionalità Site Test nel trasmettitore.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Verificare [!DNL Sensor] se si sta impostando un cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Utilizzo del test del sito {#section-a5a697c3252e40f184c0b662926170f2}

Un modo per verificare che il raccoglitore sia in esecuzione è attivare la funzione Site Test nel trasmettitore. Quando abilitate Site Test, il trasmettitore invia periodicamente (ogni 60 secondi) una richiesta di GET al server Web su cui è in esecuzione il raccoglitore. Se il test del sito non riceve una risposta dal server Web, scrive un messaggio di errore in syslog e invia un messaggio di errore al [!DNL data workbench server] (scritto nel file del registro del sensore).

Se Site Test riceve una risposta dal server Web, cerca nel file di coda un pacchetto dal server Web. Se il pacchetto non viene visualizzato (a indicare che il raccoglitore non era in esecuzione per l&#39;acquisizione dell&#39;evento), Site Test scrive un messaggio di errore in syslog e invia un messaggio di errore al Adobe  (anch&#39;esso scritto nel file del sensore-log).

Nelle richieste inviate dal test del sito al server Web, il test del sito imposta il valore dell&#39;agente utente su &quot; [!DNL Sensor] Test&quot;. Se non si desidera che tali richieste vengano visualizzate nel dataset, aggiungere l&#39;agente utente &quot; [!DNL Sensor] Test&quot; al [!DNL Baseline Robots List.txt] file o al [!DNL Extended Robots List.txt] file nella [!DNL Lookups] cartella [!DNL data workbench server].

**Per attivare il test del sito nel trasmettitore**

1. Individuate il [!DNL txlogd.conf] file sul computer in cui [!DNL Sensor] è in esecuzione e apritelo in un editor di testo.

1. Nel [!DNL txlogd.conf] file, individuate la riga &quot;SiteTest&quot; e configuratela come mostrato di seguito. Se il [!DNL txlogd.conf] file non include la riga &quot;SiteTest&quot;, è sufficiente aggiungere la riga alla fine del file di configurazione.

   SiteTest http, *serverAddress*, *port*, *resource*

   dove *serverAddress* è il nome o l&#39;indirizzo IP del server Web, *la porta* è la porta di ascolto HTTP del server e la *risorsa* è la risorsa specifica che si desidera richiedere Site Test al momento della verifica del server. La *risorsa* può includere una stringa di query.

   Esempio: SiteTest http,localhost,80,/index.jsp

   Per testare più server Web, è sufficiente specificare più righe SiteTest.

## Verifica di un cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Un altro modo per verificare che l&#39;agente di raccolta sia in esecuzione su un server Web consiste nel verificare se [!DNL Sensor] sta impostando un cookie nelle risposte che il server Web sta restituendo ai client. Se il raccoglitore funziona, il server Web restituisce un cookie &quot;v1st&quot;.

È possibile rinominare il cookie. Se lo avete fatto, dovete cercare il nome specificato, non v1st.

È possibile eseguire questo controllo utilizzando uno script automatizzato o un agente di monitoraggio. Per uno script di esempio o per ulteriore assistenza su questa attività, contattare  Adobe Consulting Services.
