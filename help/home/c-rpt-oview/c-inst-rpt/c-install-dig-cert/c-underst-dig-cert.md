---
description: ' Adobe utilizza certificati digitali X.509 per identificare e autenticare i componenti client e server che costituiscono un’implementazione.'
title: Informazioni sui certificati digitali
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
exl-id: 967e9d5b-7972-497e-8902-8db0eb304f27
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 54%

---

# Informazioni sui certificati digitali{#understanding-digital-certificates}

 Adobe utilizza certificati digitali X.509 per identificare e autenticare i componenti client e server che costituiscono un’implementazione.

Quando installi [!DNL Report Server], devi installare il certificato digitale che autorizza un individuo con nome (ad esempio, Jane Smith) a utilizzare l’applicazione client installata.

>[!NOTE]
>
>Se devi eseguire la migrazione di [!DNL Report Server] a un altro computer o a un altro utente con nome, devi ottenere un nuovo certificato da Adobe. Per farlo, contatta l’Assistenza clienti di Adobe.

[!DNL Report Server] presenta questo certificato digitale per ottenere l’accesso a un componente server. Un amministratore del componente server può limitare l’accesso alle risorse del server in base al nome comune o ai valori delle unità organizzative visualizzati nel certificato del client.

I certificati digitali X.509 installati con applicazioni Adobe consentono inoltre ai componenti client e server di scambiare informazioni tramite Secure Sockets Layer (SSL). SSL protegge le trasmissioni via HTTP utilizzando un sistema di crittografia a chiave pubblica e privata. L’implementazione di SSL da parte di Adobe supporta le chiavi RSA a 1024 bit e utilizza un algoritmo di crittografia RC4 a 128 bit.

Oltre alla protezione, il certificato digitale installato funziona anche come chiave di licenza che consente di eseguire il [!DNL Report Server] installato. Per funzionare correttamente, un certificato digitale deve essere bloccato sul nodo e corrente, altrimenti l&#39;applicazione non verrà avviata.

## Certificati bloccati sul nodo {#section-3338f1558e7844888dced8f395888744}

Un certificato bloccato sul nodo è un certificato digitale associato al computer in cui è installato. Il blocco sul nodo associa in modo permanente un certificato a un identificatore di nodo specifico (un valore che identifica in modo univoco un singolo computer). Per bloccare il certificato sul nodo, il computer deve poter accedere tramite Internet al server licenze di Adobe o a un server proxy con accesso al server licenze.

Se stai effettuando l’installazione su un computer che non ha accesso a Internet, devi ottenere e installare in questa pagina uno speciale certificato pre-bloccato come descritto in [Utilizzo di certificati digitali su computer senza accesso a Internet](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d).

Se stai effettuando l’installazione su un computer che può accedere a Internet, il certificato digitale viene bloccato automaticamente al primo avvio di [!DNL Report Server]. Dopo il blocco sul nodo, il certificato non può essere utilizzato su nessun altro computer. Se devi eseguire la migrazione di [!DNL Report Server] a un altro computer, devi ottenere un nuovo certificato sbloccato da Adobe.

## Certificati correnti {#section-b4053ab714514dfb97ea7f61bbb8da1e}

Oltre a essere bloccato sul nodo, un certificato digitale deve essere corrente. Per restare corrente, il certificato deve essere convalidato regolarmente (generalmente ogni 30 giorni, ma può variare a seconda del contratto con l’Adobe). Se il computer dispone di accesso a Internet, il processo di riconvalida è assolutamente semplice. [!DNL Report Server] si connette automaticamente al server licenze e, se necessario, riconvalida il certificato. Se il computer non dispone dell’accesso a Internet, è necessario installare manualmente i certificati aggiornati come descritto nella sezione seguente.

## Utilizzo di certificati digitali su computer senza accesso a Internet {#section-18cce05e2204407bb2b6b75deab9197d}

Se stai effettuando l’installazione su un computer che non ha accesso a Internet, devi richiedere un certificato pre-bloccato per l’installazione di [!DNL Report Server]. Un certificato pre-bloccato è un certificato digitale che Adobe blocca manualmente sull’identificatore del nodo del computer.

Per richiedere un certificato pre-bloccato, è necessario inviare l’identificatore del nodo e il numero del certificato all’Assistenza clienti di Adobe. Per ottenere l&#39;identificatore del nodo del computer, contatta l&#39;Assistenza clienti Adobe per richiedere l&#39;utility Adobe [!DNL Node Identifier]. È inoltre possibile ottenere l’identificatore del nodo dall’avviso che [!DNL Report Server] genera quando tenta di connettersi al server licenze e non può. Quando ricevi il certificato pre-bloccato, installalo come descritto negli ultimi due passaggi delle [Procedure di installazione dei certificati digitali](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d).

Quando è necessario riconvalidare il certificato, è necessario scaricare un nuovo certificato convalidato dal server licenze e reinstallarlo nel computer (a meno che il consenso con gli stati di Adobe non sia diversamente).
