---
description: Istruzioni per l’utilizzo di certificati personalizzati.
title: Utilizzo di certificati personalizzati in Data Workbench
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
exl-id: f813d599-723f-4b5d-a0b5-f4d71c1b1a22
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---

# Utilizzo di certificati personalizzati in Data Workbench{#using-custom-certificates-in-data-workbench}

{{eol}}

Istruzioni per l’utilizzo di certificati personalizzati.

Un certificato utilizzato dal client o dal server di Data Workbench deve essere firmato da una CA attendibile (Certificate Authority). Data Workbench ai clienti di ricevere certificati firmati da Visual Sciences CA. Questi certificati sono considerati attendibili dal software Data Workbench, in quanto [!DNL trust_ca_cert.pem] (fornito insieme al software Insight e memorizzato nel **Certificati** directory sia dei server che dei client) contiene un *Certificato CA radice* per Visual Sciences CA. Questi certificati vengono utilizzati sia per la concessione di licenze del software che per l’autenticazione quando client e server comunicano tra loro utilizzando SSL. È possibile utilizzare solo i certificati rilasciati da Visual Sciences CA per le licenze, ma altri certificati possono essere utilizzati per la comunicazione e l’autenticazione. I certificati rilasciati da CA diverse da Visual Sciences sono indicati di seguito come *certificati personalizzati.*

**Nota importante:** Per server e client, il software Data Workbench utilizza i file di certificato installati nel client o nel server **Certificati** directory o certificati esplicitamente identificati nella relativa configurazione. Tuttavia, puoi anche utilizzare il [Archivio certificati di Windows](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) per i clienti.

Le istruzioni seguenti descrivono le procedure da seguire per utilizzare certificati personalizzati per la comunicazione tra client e server Data Workbench. Non tutti i dettagli sono un requisito difficile e possono essere utilizzate diverse variazioni nel processo. Tuttavia, le procedure seguenti sono state collaudate per funzionare.

## Configurazione di certificati client personalizzati {#section-2083fd41973e451fa404e7a4ae4da591}

1. Aggiungere il certificato della CA emittente al [!DNL trust_cert_ca.pem], che è installato nel **Certificati** directory del client e di ogni server in ogni cluster a cui si accede utilizzando questo certificato personalizzato.

1. Ottieni un certificato personalizzato per ogni server del cluster con le seguenti condizioni:

   1. Il certificato è formattato come [!DNL .pem] certificato.
   1. Il certificato contiene la sua chiave e non è crittografato (ovvero non ha una frase di password/pass).

      Un certificato contiene la relativa chiave con una delle seguenti righe:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Un modo per rimuovere la frase password da un [!DNL .pem] certificato:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Il certificato ha la NC, O, OU, ecc. come richiesto per questo client nei server [!DNL Access Control.cfg] file.
   1. Il certificato è stato rilasciato con un *scopo&#42;&#42;&#42;* di *client* o *server* **e** *client*).

      Per verificare che un certificato abbia un codice di scopo del server e/o del client, è possibile utilizzare i seguenti comandi:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Per i certificati server, entrambi i comandi devono restituire:

      ```
      custom_communications_cert.pem: OK
      ```

      Per un certificato client, è necessario solo il secondo comando per restituire [!DNL OK].

1. Posiziona il certificato nel **Certificati** directory.
1. In [!DNL Insight.cfg] in *serverInfo* per ogni cluster che desideri utilizzare questo certificato, assicurati che il *certificato client personalizzato* viene denominato, ad esempio:

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## Configurazione di certificati server personalizzati {#setting-up-custom-server-certificates}

Questa sezione presuppone che sia attivo un cluster in esecuzione, utilizzando i certificati rilasciati da Visual Sciences, e che la configurazione segua le pratiche comuni (ad esempio *Componenti per i server di elaborazione* la directory sul master viene sincronizzata con il *Componenti* directory di tutte le DPU).

1. Aggiungere il certificato della CA emittente al [!DNL trust_cert_ca.pem] che viene installato su ogni server del cluster e su ogni client che deve comunicare con questo cluster.
1. Ottieni un certificato personalizzato per ogni server del cluster con i seguenti requisiti:

   1. Il certificato personalizzato è formattato come [!DNL .pem] certificato.
   1. Il certificato contiene la sua chiave e non è crittografato (ovvero non ha una frase di password/pass).

      Un certificato contiene la relativa chiave se presenta una riga come:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Un modo per rimuovere la frase password da un [!DNL .pem] certificato:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Il certificato ha la stessa NC del certificato [!DNL server_cert.pem] attualmente installato sul server.
   1. Il certificato è stato rilasciato a fini di *server* e *client*.

      Per verificare che un certificato abbia un codice di scopo del server e/o del client, è possibile utilizzare i seguenti comandi:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Per i certificati server, entrambi i comandi devono restituire:

      ```
      custom_communications_cert.pem: OK
      ```

      Per un certificato client, è necessario solo il secondo comando per restituire [!DNL OK].

1. Installa il certificato personalizzato di ogni server nel **Certificati** directory del server come [!DNL custom_communications_cert.pem].

1. Utilizzando un editor di testo, aggiungi la seguente riga a **Communications.cfg** in entrambi i *Componenti* e *Componenti per i server di elaborazione* directory, direttamente sotto la prima riga ([!DNL component = CommServer]):

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Riavvia tutti i server.

**Informazioni sull’avviso di errore del certificato**

Quando il server o il client Insight cerca un **licenza** nel certificato **Certificati** cerca di convalidare tutti i certificati (tranne [!DNL trust_ca_cert.pem]), rispetto a una copia hardcoded del certificato Insight CA, che non riesce su alcun certificato personalizzato presente nella directory. Il server invia questo avviso:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Questo avviso può essere ignorato in tutta sicurezza.
