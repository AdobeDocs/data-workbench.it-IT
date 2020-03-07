---
description: Adobe utilizza i certificati digitali X.509 per identificare e autenticare i componenti client e server che costituiscono un'implementazione.
solution: Analytics
title: Informazioni sui certificati digitali
topic: Data workbench
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informazioni sui certificati digitali{#understanding-digital-certificates}

Adobe utilizza i certificati digitali X.509 per identificare e autenticare i componenti client e server che costituiscono un&#39;implementazione.

Al momento dell&#39;installazione [!DNL Report Server], è necessario installare il certificato digitale che autorizza un individuo denominato (ad esempio, Jane Smith) a utilizzare l&#39;applicazione client installata.

>[!NOTE]
>
>Per effettuare la migrazione [!DNL Report Server] a un altro computer o a un altro utente denominato, è necessario ottenere un nuovo certificato da Adobe. Per farlo, contatta l’Assistenza clienti Adobe.

[!DNL Report Server] presenta questo certificato digitale per ottenere l’accesso a un componente server. Un amministratore del componente server può limitare l’accesso alle risorse del server in base al nome comune o ai valori delle unità organizzative visualizzati nel certificato del client.

I certificati digitali X.509 installati con le applicazioni Adobe consentono inoltre ai componenti client e server di scambiarsi informazioni tramite SSL (Secure Sockets Layer). SSL assicura le trasmissioni via HTTP utilizzando un sistema di crittografia a chiave pubblica e privata. L’implementazione di SSL da parte di Adobe supporta le chiavi RSA a 1024 bit e utilizza un algoritmo di cifratura RC4 a 128 bit.

Oltre alla protezione, il certificato digitale installato funziona anche come chiave di licenza che consente di eseguire l&#39;installazione [!DNL Report Server]. Per funzionare correttamente, un certificato digitale deve essere bloccato e corrente oppure l&#39;applicazione non verrà avviata.

## Certificati bloccati dal nodo {#section-3338f1558e7844888dced8f395888744}

Un certificato bloccato da un nodo è un certificato digitale registrato nel computer in cui è installato. Il blocco dei nodi associa in modo permanente un certificato a un identificatore di nodo specifico (un valore che identifica in modo univoco un particolare computer). Per bloccare il certificato in un nodo, il computer deve disporre dell&#39;accesso a Internet al server delle licenze Adobe o a un server proxy con accesso al server delle licenze.

Se si sta installando su un computer che non può accedere a Internet, è necessario ottenere e installare uno speciale certificato pre-bloccato come descritto in [Utilizzo di certificati digitali su computer senza accesso](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) a Internet in questa pagina.

Se si sta installando su un computer in grado di accedere a Internet, il certificato digitale viene bloccato automaticamente al primo avvio [!DNL Report Server]. Dopo il blocco dei nodi, il certificato non può essere utilizzato su nessun altro computer. Per effettuare la migrazione [!DNL Report Server] a un altro computer, è necessario ottenere un nuovo certificato sbloccato da Adobe.

## Certificati correnti {#section-b4053ab714514dfb97ea7f61bbb8da1e}

Oltre a essere bloccati in un nodo, è necessario che sia presente un certificato digitale. Per restare aggiornati, il certificato deve essere convalidato regolarmente (generalmente ogni 30 giorni, ma può variare a seconda del contratto con Adobe). Se il computer dispone di accesso a Internet, il processo di riconvalidazione è completamente trasparente. [!DNL Report Server] si connette automaticamente al server licenze e, se necessario, riconvalida il certificato. Se il computer non dispone dell&#39;accesso a Internet, è necessario installare manualmente i certificati aggiornati come descritto nella sezione seguente.

## Utilizzo di certificati digitali su computer senza accesso a Internet {#section-18cce05e2204407bb2b6b75deab9197d}

Se state installando un computer che non può accedere a Internet, dovete richiedere un certificato pre-bloccato per l&#39;installazione di [!DNL Report Server]. Un certificato pre-bloccato è un certificato digitale che Adobe blocca manualmente all&#39;identificatore del nodo del computer.

Per richiedere un certificato pre-bloccato, è necessario inviare l&#39;identificatore del nodo e il numero del certificato all&#39;Assistenza clienti Adobe. Per ottenere l&#39;identificatore del nodo del computer, contattate l&#39;Assistenza clienti Adobe per richiedere l&#39; [!DNL Node Identifier] utility Adobe. È inoltre possibile ottenere l’identificatore del nodo dall’avviso che [!DNL Report Server] si verifica quando tenta di connettersi al server licenze e non può. Quando ricevete il certificato pre-bloccato, installatelo come descritto nelle ultime due fasi delle procedure [di installazione dei certificati](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d)digitali.

Se il certificato deve essere nuovamente convalidato, è necessario scaricare un nuovo certificato convalidato dal server licenze e reinstallarlo nel computer (a meno che il contratto con Adobe non preveda diversamente).
