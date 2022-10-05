---
description: Informazioni generali sui certificati digitali e sulle procedure per scaricarli e installarli.
title: Download e installazione dei certificati digitali
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
exl-id: 8aae9b63-7df0-4725-9833-711246bbe746
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 100%

---

# Download e installazione dei certificati digitali{#downloading-and-installing-the-digital-certificates}

{{eol}}

Informazioni generali sui certificati digitali e sulle procedure per scaricarli e installarli.

* [Informazioni sui certificati digitali](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [Certificati bloccati sul nodo](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [Certificati correnti](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [Utilizzo di certificati digitali su computer senza accesso a Internet](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [Procedure di installazione dei certificati digitali](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## Informazioni sui certificati digitali {#section-e48a776ef39042759d1dfb3444996d8b}

 Adobe utilizza certificati digitali X.509 per identificare e autenticare i componenti client e server che costituiscono un’implementazione.

Quando installi un componente server ([!DNL Insight Server] o [!DNL Repeater]), devi installare il certificato digitale rilasciato da Adobe per il componente. Se hai bisogno di migrare l’applicazione Adobe in un altro computer, devi ottenere un nuovo certificato da Adobe. Per farlo, contatta l’Assistenza clienti di Adobe.

Il nome comune visualizzato in questo certificato identifica il server in base a un nome di dominio specificato (ad esempio, [!DNL vs001a.mycompany.com]). Quando un client server si connette a questo server, il server presenta questo certificato come prova del fatto che si tratta effettivamente del server richiesto dal client.

Allo stesso modo, quando installi un client server (ad esempio, [!DNL Insight] o [!DNL Report]), devi installare il certificato digitale che autorizza un individuo con nome (ad esempio, Jane Smith) a utilizzare l’applicazione client installata. Se hai bisogno di migrare l’applicazione Adobe in un altro computer o a un altro utente con nome, devi ottenere un nuovo certificato da Adobe. Per farlo, contatta l’Assistenza clienti di Adobe.

L’applicazione client presenta questo certificato digitale per ottenere l’accesso a un componente server. Un amministratore del componente server può limitare l’accesso alle risorse del server in base al nome comune o ai valori delle unità organizzative visualizzati nel certificato del client.

I certificati digitali X.509 installati con applicazioni Adobe consentono inoltre ai componenti client e server di scambiare informazioni tramite Secure Sockets Layer (SSL). SSL protegge le trasmissioni via HTTP utilizzando un sistema di crittografia a chiave pubblica e privata. L’implementazione di SSL da parte di Adobe supporta le chiavi RSA a 1024 bit e utilizza un algoritmo di crittografia RC4 a 128 bit.

Oltre a fornire protezione, i certificati digitali installati funzionano anche come chiavi di licenza che ti consentono di eseguire il software di Adobe installato. Per funzionare correttamente, un certificato digitale deve essere bloccato sul nodo e corrente, altrimenti l’applicazione non si avvia.

## Crittografia della stringa {#section-8abe6b2d95704d38a04137d5c4602f0b}

Per la cifratura delle password, consulta [Crittografia della stringa](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a).

## Certificati bloccati sul nodo {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

Un certificato bloccato sul nodo è un certificato digitale associato al computer in cui è installato. Il blocco sul nodo associa in modo permanente un certificato a un identificatore di nodo specifico (un valore che identifica in modo univoco un singolo computer). Per bloccare il certificato sul nodo, il computer deve poter accedere tramite Internet al server licenze di Adobe o a un server proxy con accesso al server licenze.

Se stai effettuando l’installazione su un computer che non ha accesso a Internet, devi ottenere e installare uno speciale certificato pre-bloccato come descritto in [Utilizzo di certificati digitali su computer senza accesso a Internet](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa).

Se stai effettuando l’installazione su un computer con accesso a Internet, il certificato digitale viene bloccato automaticamente al primo avvio del prodotto Adobe. Dopo il blocco sul nodo, il certificato non può essere utilizzato su nessun altro computer. Se hai bisogno migrare il prodotto Adobe in un altro computer, devi ottenere un nuovo certificato sbloccato da Adobe.

## Certificati correnti {#section-15aabaa8625c46edaa7436e1f3fc29c5}

Oltre a essere bloccato sul nodo, un certificato digitale deve essere corrente. Per restare corrente, il certificato deve essere convalidato regolarmente (generalmente ogni 30 giorni, ma può variare a seconda del contratto con Adobe). Se il computer dispone di accesso a Internet, il processo di riconvalida è assolutamente semplice. Il prodotto Adobe si connette automaticamente al server licenze e, se necessario, riconvalida il certificato. Se il computer non dispone dell’accesso a Internet, è necessario installare manualmente i certificati aggiornati come descritto nella sezione seguente.

## Utilizzo di certificati digitali su computer senza accesso a Internet {#section-809366329a7d4e198f95fe06c1f534fa}

Se stai effettuando l’installazione su un computer che non ha accesso a Internet, devi richiedere un certificato pre-bloccato per l’installazione di [!DNL Insight Server]. Un certificato pre-bloccato è un certificato digitale che Adobe blocca manualmente sull’identificatore del nodo del computer.

Per richiedere un certificato pre-bloccato, è necessario inviare l’identificatore del nodo e il numero del certificato all’Assistenza clienti di Adobe. Per ottenere l’identificatore del nodo del computer, contatta l’Assistenza clienti di Adobe per richiedere l’utility Adobe Node Identifier. È inoltre possibile ottenere l’identificatore del nodo dall’avviso che il software Adobe genera quando tenta di connettersi al server licenze senza riuscirci.

Quando ricevi il certificato pre-bloccato, installalo come descritto negli ultimi due passaggi delle [Procedure di installazione dei certificati digitali](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b). Quando è necessario riconvalidare il certificato, devi scaricare un nuovo certificato convalidato dal server licenze e reinstallarlo nel computer.

## Procedure di installazione dei certificati digitali {#section-19f31676aad344a98e26e4fca1fad03b}

**Per scaricare e installare il certificato digitale**

1. Apri il browser Web all’indirizzo [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >Il browser potrebbe richiedere la presentazione di un certificato digitale. Se ciò accade, fai clic su **[!UICONTROL Cancel]** per chiudere la finestra di dialogo.

1. Nella schermata di accesso, immetti **[!UICONTROL Account Name]** e **[!UICONTROL Password]** ricevuti da Adobe, quindi fai clic su **[!UICONTROL login]**.

1. Individua il certificato rilasciato per [!DNL Insight Server], quindi fai clic sull’icona associata a quel certificato.

   >[!NOTE]
   >
   >Prendi nota del nome comune assegnato al certificato. Utilizzerai questo nome in un passaggio successivo.

1. Quando viene richiesto di salvare il certificato, fai clic su **[!UICONTROL Save]**. Nota che il nome del file corrisponde al nome comune associato al certificato.
1. Scarica il file nella cartella [!DNL Certificates] nella directory in cui hai installato [!DNL Insight Server]. Questa cartella contiene già un file di certificato denominato [!DNL trust_ca_cert.pem]. Questo file di certificato deve essere sempre presente.

1. Rinomina il file di certificato scaricato in:

[!DNL server_cert.pem]
