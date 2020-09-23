---
description: Informazioni generali sui certificati digitali e sulle procedure per scaricarli e installarli.
solution: Analytics
title: Download e installazione dei certificati digitali
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 3%

---


# Download e installazione dei certificati digitali{#downloading-and-installing-the-digital-certificates}

Informazioni generali sui certificati digitali e sulle procedure per scaricarli e installarli.

* [Informazioni sui certificati digitali](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [Certificati bloccati dal nodo](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [Certificati correnti](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [Utilizzo di certificati digitali su computer senza accesso a Internet](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [Procedure di installazione dei certificati digitali](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## Informazioni sui certificati digitali {#section-e48a776ef39042759d1dfb3444996d8b}

 Adobe utilizza certificati digitali X.509 per identificare e autenticare i componenti client e server che costituiscono un&#39;implementazione.

Quando installate un componente server ( [!DNL Insight Server] o [!DNL Repeater]), dovete installare il certificato digitale emesso  Adobe per il componente. Se è necessario migrare l&#39;applicazione  Adobe in un altro computer, è necessario ottenere un nuovo certificato da  Adobe. Per farlo, contatta  Assistenza clienti di Adobe.

Il nome comune visualizzato in questo certificato identifica il server in base a un nome di dominio specificato (ad esempio, [!DNL vs001a.mycompany.com]). Quando un client del server si connette a questo server, il server presenta questo certificato come prova del fatto che si tratta del server richiesto dal client.

Allo stesso modo, quando installate un client server (ad esempio, [!DNL Insight] o [!DNL Report]), dovete installare il certificato digitale che autorizza un individuo denominato (ad esempio, Jane Smith) a utilizzare l&#39;applicazione client installata. Se è necessario migrare l&#39;applicazione  Adobe a un altro computer o a un altro utente denominato, è necessario ottenere un nuovo certificato da  Adobe. Per farlo, contatta  Assistenza clienti di Adobe.

L&#39;applicazione client presenta questo certificato digitale per ottenere l&#39;accesso a un componente server. Un amministratore del componente server può limitare l’accesso alle risorse del server in base al nome comune o ai valori delle unità organizzative visualizzati nel certificato del client.

I certificati digitali X.509 installati con applicazioni di Adobe  consentono anche ai componenti client e server di scambiare informazioni tramite Secure Sockets Layer (SSL). SSL assicura le trasmissioni via HTTP utilizzando un sistema di crittografia a chiave pubblica e privata. ’implementazione di SSL da parte del Adobe supporta le chiavi RSA a 1024 bit e utilizza un algoritmo di crittografia RC4 a 128 bit.

Oltre alla protezione, i certificati digitali installati funzionano anche come chiavi di licenza che consentono di eseguire il software di Adobe  installato. Per funzionare correttamente, un certificato digitale deve essere bloccato e corrente oppure l&#39;applicazione non deve avviarsi.

## Crittografia della stringa {#section-8abe6b2d95704d38a04137d5c4602f0b}

Per la cifratura delle password, vedere Cifratura [](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a) delle stringhe.

## Certificati bloccati dal nodo {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

Un certificato bloccato da un nodo è un certificato digitale registrato nel computer in cui è installato. Il blocco dei nodi associa in modo permanente un certificato a un identificatore di nodo specifico (un valore che identifica in modo univoco un particolare computer). Per bloccare il certificato in un nodo, il computer deve disporre dell&#39;accesso a Internet al server licenze di Adobe  o a un server proxy con accesso al server licenze.

Se si sta installando su un computer che non può accedere a Internet, è necessario ottenere e installare uno speciale certificato pre-bloccato come descritto in [Utilizzo di certificati digitali su computer senza accesso](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)a Internet.

Se si sta installando su un computer in grado di accedere a Internet, il certificato digitale viene bloccato automaticamente al primo avvio del prodotto del Adobe . Dopo il blocco dei nodi, il certificato non può essere utilizzato su nessun altro computer. Se è necessario migrare il prodotto  Adobe in un altro computer, è necessario ottenere un nuovo certificato sbloccato da  Adobe.

## Certificati correnti {#section-15aabaa8625c46edaa7436e1f3fc29c5}

Oltre a essere bloccati in un nodo, è necessario che sia presente un certificato digitale. Per restare aggiornati, il certificato deve essere convalidato regolarmente (generalmente ogni 30 giorni, ma può variare a seconda del contratto con  Adobe). Se il computer dispone di accesso a Internet, il processo di riconvalidazione è completamente trasparente. Il prodotto  Adobe si connette automaticamente al server licenze e, se necessario, riconvalida il certificato. Se il computer non dispone dell&#39;accesso a Internet, è necessario installare manualmente i certificati aggiornati come descritto nella sezione seguente.

## Utilizzo di certificati digitali su computer senza accesso a Internet {#section-809366329a7d4e198f95fe06c1f534fa}

Se state installando un computer che non può accedere a Internet, dovete richiedere un certificato pre-bloccato per l&#39;installazione di [!DNL Insight Server]. Un certificato pre-bloccato è un certificato digitale che  Adobe si blocca manualmente all&#39;identificatore del nodo del computer.

Per richiedere un certificato pre-bloccato, è necessario inviare l&#39;identificatore del nodo e il numero del certificato all&#39;Assistenza clienti  Adobe. Per ottenere l&#39;identificatore del nodo per il computer, contattare  Assistenza clienti di Adobe per richiedere l&#39;utility ID nodo  Adobe. È inoltre possibile ottenere l&#39;identificatore del nodo dall&#39;avviso che il software del Adobe  genera quando tenta di connettersi al server licenze e non può.

Quando ricevete il certificato pre-bloccato, installatelo come descritto nelle ultime due fasi delle procedure [di installazione dei certificati](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)digitali. Quando il certificato deve essere convalidato, è necessario scaricare un nuovo certificato convalidato dal server licenze e reinstallarlo nel computer.

## Procedure di installazione dei certificati digitali {#section-19f31676aad344a98e26e4fca1fad03b}

**Per scaricare e installare il certificato digitale**

1. Aprite il browser Web in [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >Il browser potrebbe richiedere la presentazione di un certificato digitale. In caso contrario, fate clic **[!UICONTROL Cancel]** per chiudere la finestra di dialogo.

1. Nella schermata di accesso, immettete **[!UICONTROL Account Name]** e il **[!UICONTROL Password]** contenuto ricevuto dal Adobe , quindi fate clic su **[!UICONTROL login]**.

1. Individuate il certificato emesso per il certificato, [!DNL Insight Server]quindi fate clic sull&#39;icona associata al certificato.

   >[!NOTE]
   >
   >Prendete nota del nome comune assegnato al certificato. Utilizzate questo nome in un passaggio successivo.

1. Quando viene richiesto di salvare il certificato, fate clic su **[!UICONTROL Save]**. Il nome del file corrisponde al nome comune associato al certificato.
1. Scaricate il file nella [!DNL Certificates] cartella nella directory in cui avete installato [!DNL Insight Server]. Questa cartella contiene già un file di certificato denominato [!DNL trust_ca_cert.pem]. Questo file di certificato deve essere sempre presente.

1. Rinominate il file di certificato scaricato in:

[!DNL server_cert.pem]

